# FatLeon Features

FatLeon is self-hosted e-commerce software that brings the core components of an online store together in one codebase. It includes the storefront, checkout, order management, admin tools, customer accounts, promotions, analytics, and integrations to help you build and operate your store.

Deploy FatLeon to your own AWS environment and customize the code to fit your business needs.

This page provides an overview of the features included. Visit the [live demo](https://live.fatleon.com/) to explore the storefront and see FatLeon in action.

## Storefront

Build a shopping experience that helps customers discover products and move from browsing to checkout.

- **Product discovery:** Product listings, product detail pages, brands, and categories. Search matches published products and fits a catalog in the hundreds. A larger catalog can connect a search service you run, such as OpenSearch, in front of the same products.
- **Shopping tools:** Shopping cart and wishlist.
- **Responsive layouts:** Interfaces designed for desktop, tablet, and mobile screens.

## Checkout and Order Management

Support different purchasing scenarios and manage orders from a centralized admin interface.

- **Flexible checkout:** Registered customers check out once a payment provider is turned on. Guest checkout is included and stays off until you enable it under System → Currency & tax.
- **Customer order tracking:** Customers can view and track their own orders.
- **Order administration:** Manage orders through the admin interface.
- **Order status notifications:** Email customers when an order's status changes, once you connect an email provider.
- **Flexible fulfillment:** Support multiple delivery addresses, store pickup, and splitting an order across multiple fulfillments.
- **Multiple product types:** Support physical goods, digital goods, and affiliate products or outbound purchase links.
- **Configurable shipping charges:** Charge a flat shipping rate or a rate per item.
- **Single-store currency:** Prices and checkout use one currency for the whole store. The admin offers USD, EUR, and HKD. Another currency is a short edit to that list in the source. Re-price the catalog after the change, and pick a currency the payment provider can charge.
- **Checkout tax:** One optional rate for the store. Leave it off and the listed price is what the shopper pays. Turn it on and that rate is added to the merchandise subtotal at checkout. A rate that follows the shopper's country belongs with the payment service, where that service offers it. [Stripe Tax](https://docs.stripe.com/tax) is one. Wiring it in is a checkout change, and this store rate stays off so the order is taxed once. PayPal charges the total the store has already calculated.
- **Returns:** Approve the return in the admin. Complete the refund in Stripe or PayPal. The store keeps the approval and the record. The money moves on the provider's side, after you confirm it there.

## Admin and Content Management

Manage your store's products, content, and configuration from one place.

![FatLeon admin dashboard showing products, orders, sales, and support at a glance](assets/admin-dashboard.png)

- **Product catalog:** Manage products, brands, and inventory.
- **Content management:** Create and manage posts and other site content.
- **Site configuration:** Manage site settings and assets.
- **Analytics overview:** Review key store analytics in the admin interface.

## Localization and SEO

Prepare your store for customers using different languages and make your pages easier for search engines to understand.

- **Seven languages:** Support seven languages, with language detection based on the visitor's device language.
- **Language switching:** Let visitors switch languages using a language selector.
- **Localized URLs:** Use a language prefix in each URL.
- **Page-level SEO settings:** Configure SEO fields for individual pages.

## Customer Accounts, Referrals, and Support

Provide customer-facing features beyond the standard shopping and checkout experience.

- **Customer accounts:** Give customers a dedicated account area.
- **Referral and commission tracking:** Track referrals and associated commissions.
- **Support tickets:** Provide a ticket-based channel for customer support.
- **Visitor activity analytics:** Track visitor activity, including cart and wishlist interactions.

## Promotions and Discounts

Create offers for individual products or for the store as a whole.

- **Single-item discounts:** Apply a discount to an individual item.
- **Tiered site-wide promotions:** Configure site-wide promotions with tiered discounts.
- **Targeted coupons:** Offer coupons in addition to item discounts and site-wide promotions.

## Built-in Integrations

FatLeon includes integrations that can be enabled and configured through the admin interface. These are part of the product's codebase, rather than features that require browsing a separate third-party plugin directory.

- **Payment providers:** Stripe, PayPal, and a mock provider for testing. All three ship turned off. Checkout lists a provider after you enable it and save its settings.
- **Web analytics:** Google Analytics 4 (GA4).
- **Social sign-in:** Sign in with a Google account.
- **Live chat:** Crisp or Tawk.

### Email Provider

Order notifications and customer account emails require an email provider that you choose and configure. FatLeon does not restrict these email workflows to a single vendor.

## The shipped core

FatLeon ships the catalog, checkout, orders, and admin as one deployment. That first create is kept to a size CloudFormation can finish in one operation, so the core stays on those pieces. Product reviews and a loyalty program are left for you to add in the source when a store needs them.

## Explore FatLeon

The best way to understand the shopping experience is to try the live demo.

- **[Explore the live demo](https://live.fatleon.com/)**
- **[Visit the FatLeon website](https://fatleon.com/)**

FatLeon gives you an integrated e-commerce foundation that you can deploy in your own AWS environment and adapt to your business—without making your store dependent on a large third-party plugin ecosystem.
