<p align="center">
  <img src="assets/fatleon-logo.png" alt="FatLeon self-hosted e-commerce software" width="280">
</p>

<h3 align="center">FatLeon Self-Hosted E-commerce Software for AWS Amplify Gen 2</h3>

<p align="center">
  <strong>Own your code. Control your data. Run your store on AWS.</strong>
</p>

<p align="center">
  <a href="https://fatleon.com/">
    <img alt="Official Website" src="https://img.shields.io/badge/Official_Website-111111?style=for-the-badge">
  </a>
  &nbsp;
  <a href="https://live.fatleon.com/">
    <img alt="Live Demo" src="https://img.shields.io/badge/Live_Demo-0F6B4C?style=for-the-badge">
  </a>
  &nbsp;
  <a href="https://docs.fatleon.com/">
    <img alt="Documentation" src="https://img.shields.io/badge/Documentation-1B4F8A?style=for-the-badge">
  </a>
</p>

<p align="center">
  FatLeon commerce software is a complete e-commerce system distributed as commercial source code. It brings together a storefront, checkout, order management, an admin dashboard, and supported integrations in one customizable codebase.
  <br><br>
  Deploy it in your own AWS account and adapt it to your business.
</p>

## Overview

If you already see AWS Amplify as a self-hosted option that performs well and keeps infrastructure costs down, FatLeon e-commerce is the commerce system to start from. The storefront, checkout, order, and admin flows are already in the source code, so you do not have to map that logic out again.

### Why FatLeon Commerce?

- **Full source code:** Start with an existing commerce application and customize it for your needs.
- **Self-hosted on AWS:** Run the application in your own AWS account and retain control over your environment.
- **Customizable:** Adapt the storefront, workflows, and application code to your business requirements.
- **One-time FatLeon license:** No recurring FatLeon platform subscription fee. AWS infrastructure and third-party services are billed separately.
- **Core commerce functionality:** Bring storefront, checkout, orders, administration, customer accounts, and supported integrations together in one system.

## What's Included?

| Component | Description |
|---|---|
| Storefront | Product listings, product pages, cart, wishlist, and categories |
| Checkout and orders | Checkout flows, order tracking, and order administration |
| Admin dashboard | Manage products, inventory, customers, and store settings |
| Localization and SEO | Multilingual URLs and configurable SEO fields |
| Integrations | Supported payment, analytics, and customer communication integrations |
| AWS deployment | Deploy the application within your own AWS account |

See the [feature list](docs/product/features.md) for what ships in the source, and the [live demo](https://live.fatleon.com/) for how it runs.

## Technology Stack

FatLeon uses technologies from the modern web and AWS ecosystem, including:

| Service | Role |
|---|---|
| <a href="https://nextjs.org/"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/icons/nextjs-dark.svg"><img src="assets/icons/nextjs.svg" width="28" height="28" alt="Next.js"></picture></a> [Next.js](https://nextjs.org/) | Frontend |
| <a href="https://aws.amazon.com/amplify/"><img src="assets/icons/aws-amplify.svg" width="28" height="28" alt="AWS Amplify"></a> [AWS Amplify Gen 2](https://aws.amazon.com/amplify/) | Application development and deployment |
| <a href="https://aws.amazon.com/appsync/"><img src="assets/icons/aws-appsync.svg" width="28" height="28" alt="AWS AppSync"></a> [AWS AppSync](https://aws.amazon.com/appsync/) | API |
| <a href="https://aws.amazon.com/lambda/"><img src="assets/icons/aws-lambda.svg" width="28" height="28" alt="AWS Lambda"></a> [AWS Lambda](https://aws.amazon.com/lambda/) | Serverless functions |
| <a href="https://aws.amazon.com/cognito/"><img src="assets/icons/amazon-cognito.svg" width="28" height="28" alt="Amazon Cognito"></a> [Amazon Cognito](https://aws.amazon.com/cognito/) | Authentication |
| <a href="https://aws.amazon.com/dynamodb/"><img src="assets/icons/amazon-dynamodb.svg" width="28" height="28" alt="Amazon DynamoDB"></a> [Amazon DynamoDB](https://aws.amazon.com/dynamodb/) | Database |
| <a href="https://aws.amazon.com/s3/"><img src="assets/icons/amazon-s3.svg" width="28" height="28" alt="Amazon S3"></a> [Amazon S3](https://aws.amazon.com/s3/) | Storage |

The exact services and configuration required depend on the application features you enable and your deployment setup.

FatLeon starts from a commerce foundation you can own, then leaves room to specialize the parts that make the business different. See the [design philosophy](docs/product/design-philosophy.md).

## Why AWS Amplify?

FatLeon uses AWS Amplify Gen 2 and managed AWS services so you spend less time maintaining servers and more time on the store.

| | |
|---|---|
| Streamlined deployment | Managed hosting and Git-based CI/CD. You still set up the app, AWS resources, domains, and integrations. |
| Less infrastructure to manage | Fewer servers and database instances to run yourself. Updates, access, security, monitoring, and backups stay with you. |
| Designed to scale | Services can grow with traffic. Capacity and cost depend on architecture, quotas, and workload. |
| Pay for what you use | A quiet store does not need an always-on application server. See the cost note below. |
| Your AWS account | Code, configuration, and data stay in your account, under AWS terms and the FatLeon license. |

An always-on EC2 `t3.small` in US East (N. Virginia) is about $15.18 per month for compute alone, before disk and data transfer. That instance is not elastic: it bills for every hour it stays on, whether the store has visitors or not. A low-traffic Amplify deployment can stay under $10, but FatLeon does not guarantee the total AWS bill will. Check current rates on the [EC2 pricing](https://aws.amazon.com/ec2/pricing/on-demand/) and [Amplify pricing](https://aws.amazon.com/amplify/pricing/) pages.

[Learn more about AWS Amplify](https://aws.amazon.com/amplify/) · [Explore AWS Amplify pricing](https://aws.amazon.com/amplify/pricing/)

## Who Is FatLeon E-commerce For?

- **Businesses and brands** that want more control over their commerce application and data environment.
- **Developers** who want an existing foundation for building customized online stores.
- **Agencies and studios** delivering e-commerce projects for clients, subject to the applicable license.
- **Technical teams** looking for a customizable commerce application that can run in their own AWS account.

## Licensing and Costs

FatLeon is commercial software distributed under a license. Public documentation on GitHub does not make the product open source.

The Standard and Agency licenses include the same product and differ in usage rights. See [licensing](docs/product/licensing.md), and review the current terms on the [licensing reference](https://docs.fatleon.com/reference/licensing) before a client project.

FatLeon does not charge a recurring platform subscription fee. You are responsible for AWS infrastructure charges and any fees from payment providers or other third-party services you use.

Common questions on hosting, fees, and resale are in the [FAQ](docs/product/faq.md).

## Get Started

1. **Explore the live demo:** [live.fatleon.com](https://live.fatleon.com/)
2. **Read the documentation:** [docs.fatleon.com](https://docs.fatleon.com/)
3. **Visit the official website:** [fatleon.com](https://fatleon.com/) to learn more about the product and available licenses.

---

FatLeon is an independent product and is not affiliated with or endorsed by Amazon Web Services (AWS).
