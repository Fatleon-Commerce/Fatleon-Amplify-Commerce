# Customization

The store already sells. Catalog, checkout, orders, and the admin ship in the source. You can run it from the admin and never change a file.

A code change is graded by how far it reaches. Stop at the first grade that covers the change. A store can stay on the admin grade for its whole life. The same grading is on [Development path](https://docs.fatleon.com/local-development/development-path). The file for a specific edit is in [Where to change the storefront](https://docs.fatleon.com/reference/where-to-change).

| Grade | What it covers | When you open it |
|---|---|---|
| Admin | Images, copy, prices, and switches the admin already saves | This is the store. No code. |
| Frontend | Color, fixed labels, header, and footer | The admin has no field for that chrome. |
| Page | What a route renders, or a new route | The current pages do not do that. |
| Backend | A new data model or a server-side rule | The current schema and Lambda functions cannot hold it. |

Saving in the admin updates the running store. No new build. A change to a file is checked on the [local sandbox](https://docs.fatleon.com/local-development/local-sandbox), then pushed. Customers see it after that Amplify build finishes.

## Admin

A first launch is enough to sell. Import the sample catalog or enter products by hand, then replace the images and the words in the admin. The admin stores those records.

| What you replace | Where |
|---|---|
| Store name, tagline, Site URL, logo, favicon | System → Site Settings |
| Sender, SMTP, and which order emails go out | System → Email Settings |
| Stripe, PayPal, and the mock provider | System → Payment Settings |
| Currency, tax, guest checkout | System → Currency & tax |
| Which installed languages are public | System → Storefront Languages |
| Categories, brands, tags, products, photos, prices, stock | Product, category, brand, and tag screens |
| Homepage carousel, feature banners, inner-page hero, footer band, mobile menu image, why-choose rows | Content |
| Policy pages and journal posts | Blog |
| Campaigns and coupons | Marketing |
| Shipping templates and pickup points | Shipping template screens |

Product names, category copy, and blog posts are the language fields on those forms. A picture, a price, a page of copy, or a switch the admin already has stays in this grade. Screen-by-screen steps are in [System and global settings](https://docs.fatleon.com/operations-and-admin/system-and-global-settings) and [Catalog and products](https://docs.fatleon.com/operations-and-admin/catalog-and-products).

## Frontend

Open this grade when the change is color, a fixed label, or a header and footer link. The pages, catalog, and checkout stay as they ship.

That work is the stylesheet, the message packs for navigation and checkout labels, and the header and footer components. The paths are on [Where to change the storefront](https://docs.fatleon.com/reference/where-to-change).

Site Settings can still replace the logo and favicon after you change the files. Carousel slides, feature banners, and page-layout images stay in Content. Leave a picture in the admin when it is content. Edit the stylesheet and the message packs when the change is the chrome around that content.

## Page

Open this grade when a route should render something the current pages do not, or when you add a route. The page still reads the catalog, banners, and copy the admin already stores. Skip it when the admin grade or the frontend grade already covers the change.

A new page under the storefront layout already includes the header and footer. The admin stays outside that shell. Checkout, the cart, and account pages already exist. A change to how one of those screens looks, or which fields it shows, belongs here. Payment capture, webhooks, and order status stay in the backend grade. That split is in the [architecture](architecture.md).

Keep images and translated copy in the admin when the page only rearranges data you can already save. Add a field on the page, and keep feeding it from Content or the catalog, before you add a new table.

## Backend

Open this grade when the change is a new data model or a server-side rule. The three grades above leave checkout, payments, orders, and mail as they ship.

The Amplify Gen 2 schema and the Lambda functions live under `amplify/`. The sandbox redeploys that stack when those files change. AppSync and DynamoDB hold the catalog, carts, orders, and content. Lambda runs checkout, payment settlement, returns, admin writes, and mail. A new page that only rearranges products and banners does not need a schema change. Add a model when the admin must store something the current models cannot, or when a rule has to run on Lambda.

Payment webhooks stay on the shop domain. Leave that path in place unless the settlement flow itself is what you are changing.

## Where a change stops

Match the change to one row. Finish that grade and stop.

| Grade | You are changing | Customers see it |
|---|---|---|
| Admin | Images, copy, prices, and switches in the admin | On save. No build. |
| Frontend | Styles, labels, header, and footer | After the Amplify build |
| Page | A page or a new route | After the Amplify build |
| Backend | The `amplify/` schema or functions | After the sandbox is ready, then after the Amplify build |

Before a code change is committed, name the boundary it has to respect. An admin-only change stays on the first grade and does not need that review. The boundaries are in [Development Security](https://docs.fatleon.com/local-development/development-security).
