# Prerequisites

FatLeon commerce software deploys into an AWS account you control. Before the first deploy, have a GitHub account, a full AWS account, a domain, and an email provider. Connecting the repository and pointing the domain are the later steps. Those steps are in [Launch to Amplify](https://docs.fatleon.com/getting-started/launch-to-amplify). The same preparation is on the [prerequisites](https://docs.fatleon.com/getting-started/prerequisites/) and [domain and email](https://docs.fatleon.com/getting-started/domain-and-email/) pages.

How the running store is wired is in the [architecture](architecture.md).

## Accounts

| Account | What you need |
|---|---|
| GitHub | A personal or organization account, and a private repository for the source. Amplify deploys from that repository. |
| AWS | A full AWS account, created with [Sign up for AWS (advanced)](https://docs.aws.amazon.com/accounts/latest/reference/getting-started.html). That path gives you a root user and control over where the account's resources are created. |

[Creating an account on GitHub](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github) is the GitHub signup. The two AWS signup paths are compared in [Compare sign-up options](https://docs.aws.amazon.com/accounts/latest/reference/sign-up-for-aws.html). Use the advanced signup. The newer signup creates an account with preconfigured defaults, and it is not the account this deployment expects.

When you connect the repository, Amplify creates the roles, the database, and Cognito in that account. You do not build those stacks by hand. [Amplify Hosting](https://docs.amplify.aws/nextjs/deploy-and-host/amplify-hosting/) is the service that builds and serves the Next.js app on each push, including the backend in the same repository. The console flow for a first deploy is in [Getting started with deploying an app to Amplify Hosting](https://docs.aws.amazon.com/amplify/latest/userguide/getting-started.html). Follow the FatLeon launch page for this product. The AWS tutorial is the reference for how Amplify Hosting itself works.

Keep the repository private. The license does not allow the kit source in a public repository. See [licensing](licensing.md).

## Domain

Register the store's domain with Amazon Route 53, in the same AWS account, if you do not already have one. Route 53 creates a hosted zone for the name and sets itself as the DNS service, so the domain and the deployment share one account. That is the setup Amplify uses when you attach the domain later. The registration steps are in [Registering a new domain](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-register.html). What Route 53 sets up for a name you just bought is in [Configuring DNS routing for a new domain](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-configuring-new-domain.html).

After the app is deployed, you connect that domain in Amplify Hosting. Amplify can provision the certificate for it. See [Connecting a custom domain](https://docs.aws.amazon.com/amplify/latest/userguide/custom-domains.html).

Registration is billed yearly, and a hosted zone has its own monthly charge. Check the current amounts on [Amazon Route 53 pricing](https://aws.amazon.com/route53/pricing/). The registration fee is not refundable.

If the name is already registered somewhere else, you can keep that registrar and enter the DNS records yourself. Buying the name in Route 53 avoids that extra mapping.

## Email

Sign-up codes, password resets, and order mail go out through an email provider you choose. Enter its SMTP settings in the admin before launch. Cognito and Amplify Hosting do not send that mail for you. The message path is in the [architecture](architecture.md).

Amazon SES is the provider in the same AWS account. A new SES account starts in the sandbox: it can send only to verified addresses, and only in small volume. Request production access before the store sends mail to customers. See [Setting up Amazon SES](https://docs.aws.amazon.com/ses/latest/dg/setting-up.html) and [Request production access](https://docs.aws.amazon.com/ses/latest/dg/request-production-access.html).

If that review is refused, or it is stricter than you want to wait through, use another provider. FatLeon does not lock these messages to one vendor. Enter that provider's SMTP host, port, username, and password in the admin.

| Provider | What it is for | Setup |
|---|---|---|
| Google Workspace | Mailboxes on your domain, and an SMTP relay for the store | [Route outgoing SMTP relay messages through Google](https://support.google.com/a/answer/2956491) |
| Zoho Mail | Mailboxes on your domain, with SMTP | [Zoho Mail SMTP configuration](https://www.zoho.com/mail/help/zoho-smtp.html) |
| Twilio SendGrid | Transactional mail over SMTP | [Integrating with the SMTP API](https://docs.sendgrid.com/for-developers/sending-email/integrating-with-the-smtp-api) |
| Mailgun | Transactional mail over SMTP | [Send via SMTP](https://documentation.mailgun.com/docs/mailgun/user-manual/sending-messages/send-smtp) |

Where those credentials go in the admin is on [Domain and email](https://docs.fatleon.com/getting-started/domain-and-email/).
