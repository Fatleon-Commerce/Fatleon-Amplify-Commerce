# FAQ

Short answers about buying, hosting, and running FatLeon commerce software. Use of the source is governed by the license file in your purchase. The [licensing](licensing.md) page explains Standard and Agency. The same questions are also answered on the [documentation site](https://docs.fatleon.com/reference/faq).

## How is this different from a SaaS shop?

You are not renting a hosted store. You buy a commercial license and deploy the source yourself.

| | SaaS | Non-SaaS FatLeon |
|---|---|---|
| What you buy | A hosted shop you rent | A commercial license to the source code |
| Who hosts | The platform | You, on your AWS account |
| Store data | On the platform's servers | In your AWS account |
| Fees | A monthly platform fee | One-time purchase. No recurring platform fee |
| Customizing | Themes and apps | The source code |
| If you cancel | The whole store cannot be moved into your AWS account | The store is already in your account |

Amplify has no whole-store migration that moves hosting, the API, accounts, the database, and files into your account as one application. A catalog file a vendor may let you download is not that move.

## Is FatLeon an AWS product?

No. FatLeon is independent and is not affiliated with or endorsed by Amazon Web Services. The store uses AWS services, and you deploy and operate it in your own account.

## Do I need a subscription?

No. The purchase is once. You receive the source code. There is no monthly platform fee from FatLeon.

## Do you host my store?

No. You deploy it on your own AWS account. The store and its data remain in that account. Deploy steps are in the [documentation](https://docs.fatleon.com/).

## What kinds of products does it fit?

FatLeon fits goods you fulfill yourself. Product types are listed on the [feature list](features.md).

| Product | How it is fulfilled |
|---|---|
| Physical goods | You ship them. A marketplace does not ship them for you |
| Virtual goods | You deliver them. A marketplace does not deliver them for you |
| Outbound commission links | The buyer leaves through a link, and you earn a commission |

## Can I customize the source code?

Yes. Restyling the storefront, fitting the market you sell in, and adding a tool the shop needs are the usual changes. Checkout, orders, and admin are already in the source. What ships is listed on the [feature list](features.md).

## How does multilingual work?

FatLeon treats language as part of the whole store, not as a translation laid over one page. When a visitor switches language, the page changes with it, and so does the content tied to that language, including related products and blog posts. Many shops only replace the words on the current page and leave the catalog and posts in the original language. Languages and URLs are described on the [feature list](features.md).

## What is the difference between Standard and Agency?

The product is the same. The difference is where you may use it. Standard covers storefronts you own and operate. Agency also covers stores you build for clients, and handing over that one store's project. The comparison is on the [licensing](licensing.md) page.

## Do I still pay AWS and payment fees?

Yes. AWS bills the account the store runs in. Stripe or PayPal bills you for payments they process. Those charges are separate from the FatLeon license.

## What does it cost to keep the system running?

FatLeon charges no maintenance fee. AWS bills for what you use. At the lowest usage, that monthly bill is usually under $10. That is a typical low-traffic figure, not a cap FatLeon guarantees.

## Does the backend scale with usage?

Yes. You do not rent a server for the whole month. Pages run on Amplify Hosting, the API is AppSync, data is in DynamoDB, sign-in is Cognito, files are in S3, and work such as placing an order runs on Lambda when a request arrives. Capacity follows use and falls back when the store is quiet. The shape is in the [architecture](architecture.md).

## Can I resell FatLeon as my own kit?

No. The license lets you run stores under the SKU you bought. Reselling, sublicensing, or redistributing the source as a template or a competing product is not included. Details are on the [licensing](licensing.md) page.

## Can I try FatLeon for my business?

Sign in at [fatleon.com](https://fatleon.com/) and open a support ticket. Say that you want to see whether FatLeon fits your business. FatLeon will send a temporary domain, plus an account and password, so you can test the store.

## How do I contact support?

Sign in at [fatleon.com](https://fatleon.com/) and open a support ticket. Use it for questions about the kit, including use, deployment, a trial of the store, and other requests.
