# Running costs

FatLeon charges no platform fee and no maintenance fee. The license is a one-time purchase. AWS bills the account the store runs in. At the lowest usage, that AWS bill is usually under $10 a month. That is a typical low-traffic figure for one quiet production deployment, not a cap FatLeon guarantees. Set next to an always-on EC2 `t3.small` in US East (N. Virginia):

| | FatLeon, one quiet deployment | EC2 `t3.small`, always on |
|---|---|---|
| A quiet month | Usually under $10 for the application stack | About $15.18 for compute, before disk and data transfer |
| An idle hour | Stored data, plus a few short scheduled jobs | That hour is billed |
| Ceiling | Rises with visits and orders | 2 vCPUs and 2 GiB |
| The machine | No application server to keep running | You size, patch, and watch that instance |

Rates change. Check [EC2 On-Demand pricing](https://aws.amazon.com/ec2/pricing/on-demand/) for the region where you would run a server.

The figure is the application stack below. A domain, a mailbox, and payment processing are separate bills. A second branch or a sandbox left running is a second stack on the same account, and it is not inside the figure either.

How the store is wired is in the [architecture](architecture.md). What to register before the first deploy is in the [prerequisites](prerequisites.md).

## The application stack

A deployment creates these services. A quiet store does not keep an application server on for the month. You pay for data you keep, for builds you start, and for work that runs when a request or a schedule arrives.

| Service | What it does | What moves the bill |
|---|---|---|
| Amplify Hosting | Serves the Next.js storefront and admin, and builds the app on each push | Build minutes, stored build output, data transferred to browsers, and, because this app renders on the server, request count and request duration |
| AWS AppSync | Catalog, cart, and content reads | API requests. They follow visits |
| Amazon DynamoDB | Catalog, carts, orders, and content | Storage of the records you keep, plus reads and writes. Orders add writes |
| Amazon Cognito | One user pool for customers, admins, and affiliates | Monthly active users |
| AWS Lambda | Checkout, payment settlement, returns, admin writes, and outbound mail | Invocations and the time they run. Scheduled jobs also run when nobody is shopping: unpaid checkouts expire every five minutes, inbound mail is polled on that same interval, visitor stats run daily, and an API key is renewed monthly |
| Amazon S3 and Amazon CloudFront | Product and banner files. CloudFront publishes the `admin-pictures/` prefix only | Storage of those files, and delivery when a browser loads them |
| AWS KMS | One customer-managed key so Cognito can hand mail to Lambda | The key itself, every month the deployment exists, including a month that sends no mail |

Those schedules are short invocations. They are part of the same stack. They do not add a host that bills for every idle hour.

The KMS key has automatic rotation turned on. On the [KMS pricing](https://aws.amazon.com/kms/pricing/) page, the key has a monthly charge, and the first rotation and the second rotation each add another monthly charge. Further rotations do not raise it again.

Lambda also writes request logs. Those logs are on the same AWS bill. A function that logs heavily on every run can cost more in logs than in compute. Monitoring stays with you.

## What a quiet month leaves out

These are easy to read as part of the store, and they are billed on their own.

| Charge | Who bills it | When it shows up |
|---|---|---|
| Domain registration | Route 53, or the registrar you already use | Yearly. A Route 53 registration fee is not refundable. The steps are in the [prerequisites](prerequisites.md) |
| Route 53 hosted zone | AWS | Monthly, when DNS for the name lives in Route 53 |
| Email | Amazon SES, or the SMTP provider you enter in the admin | SES bills for messages you send. A new SES account starts in the sandbox. Google Workspace, Zoho Mail, Twilio SendGrid, and Mailgun bill on their own plans. The admin stores SMTP credentials. It does not include a mailbox |
| Stripe or PayPal | That provider | A fee on payments they process. Separate from the FatLeon license and from AWS |
| Amplify Web Application Firewall | AWS | About $15 per Amplify app per month, plus the firewall's own charges, if you turn it on. The published price applies even where the rest of Amplify Hosting is inside a free tier. Leave it off unless you have decided to run it |

## What raises the AWS bill

The under-$10 figure is one branch, rarely built, with little traffic.

Amplify deploys the backend for each branch it builds, so a second connected branch is another API, database, user pool, and set of functions. The [local sandbox](https://docs.fatleon.com/local-development/local-sandbox) is the same kind of extra stack. Delete it when you are done, or the account bill includes both.

Build minutes add up faster than a quiet storefront. The [Amplify pricing](https://aws.amazon.com/amplify/pricing/) page prices a standard build at $0.01 per minute outside the free tier, and its own example of 600 build minutes in a month is $6 before any traffic. A store that is pushed many times a day spends the month on builds. A store that is built twice and then left alone spends it on storage and the occasional request.

Traffic moves the hosting lines that scale with use: data transferred out, server-rendered request count, and request duration. Catalog storage in DynamoDB and files in S3 grow with what you keep, whether or not anyone visits.

## Free tier and credits

A new AWS account can include credits or a free tier that make the first months lower than the rates above. The Amplify pricing page lists monthly allowances for build minutes, stored data, data transfer, server-rendered requests, and request duration. Those are AWS account terms. They expire, and they are not part of the FatLeon license. The under-$10 figure does not depend on them still being in force. Current terms are on the [AWS Free Tier](https://aws.amazon.com/free/) page.

## Rates to check

Prices differ by region. The EC2 comparison above is US East (N. Virginia). The store's bill is the region you deploy to.

- [Amazon EC2 On-Demand pricing](https://aws.amazon.com/ec2/pricing/on-demand/)
- [AWS Amplify pricing](https://aws.amazon.com/amplify/pricing/)
- [AWS AppSync pricing](https://aws.amazon.com/appsync/pricing/)
- [Amazon DynamoDB pricing](https://aws.amazon.com/dynamodb/pricing/)
- [Amazon Cognito pricing](https://aws.amazon.com/cognito/pricing/)
- [AWS Lambda pricing](https://aws.amazon.com/lambda/pricing/)
- [Amazon S3 pricing](https://aws.amazon.com/s3/pricing/)
- [Amazon CloudFront pricing](https://aws.amazon.com/cloudfront/pricing/)
- [AWS KMS pricing](https://aws.amazon.com/kms/pricing/)
- [Amazon Route 53 pricing](https://aws.amazon.com/route53/pricing/)
- [Amazon SES pricing](https://aws.amazon.com/ses/pricing/)
- [Amazon CloudWatch pricing](https://aws.amazon.com/cloudwatch/pricing/)

The license, and what it does not include, is on the [licensing](licensing.md) page. Short answers on fees are in the [FAQ](faq.md).
