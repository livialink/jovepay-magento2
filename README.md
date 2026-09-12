# Installation Guide

# JOVEpay Crypto Payment Gateway

JOVEpay is a crypto payment gateway. Accept Bitcoin, Ethereum, stablecoins, and 100+ other cryptocurrencies on Magento Open Source and Adobe Commerce storefronts. Settlement goes to your wallet via [JOVEpay](https://www.jovepay.com).

The hosted payment widget supports **light and dark themes**, and displays in **multiple languages** based on the customer’s Magento store locale.

<!-- IMAGE PLACEHOLDER: JOVEpay logo / product banner -->
![JOVEpay logo](https://res.cloudinary.com/gysvswrq/image/upload/v1789253020/jovepay-240x240.png)

## What is a Crypto Payment Gateway?

A crypto payment gateway acts as a bridge between the merchant’s website and the cryptocurrency network, allowing the merchant to receive payments in cryptocurrency. Customers pay on JOVEpay’s hosted checkout widget; Magento receives order status updates through secure Instant Payment Notifications (IPN).

## Requirements

- Magento Open Source / Adobe Commerce 2.x (2.4.x recommended)
- PHP >= 7.3
- An open and **activated** [JOVEpay merchant account](https://app.jovepay.com/). If you do not have an account yet, [create one](https://www.jovepay.com). The plugin cannot process payments until the account is activated.
- **Merchant ID** (API key) and **IPN Secret** from the JOVEpay dashboard

## Plugin Installation Guide

### 1. Install From Magento Marketplace

You can install the JOVEpay plugin from the Magento Marketplace with Composer.

1. Log in to your server and go to your Magento root directory.
2. Download the plugin using this command:

```bash
composer require jovepay/magento2:1.0.0
```

`1.0.0` is the current plugin version. Check for the latest version before running the command.

3. You may be asked for a username and password while installing.
4. Get the public key and private key from **Access Keys** under **My Profile** on the [Adobe Commerce Marketplace](https://commercemarketplace.adobe.com/).

5. Enter the **public key** as the username and the **private key** as the password.
6. Enable the module:

```bash
php bin/magento module:enable Jovepay_Checkout
```

### 2. Install Manually (app/code)

1. Copy the `Jovepay/Checkout` module into `app/code/Jovepay/Checkout`.
2. Enable the module:

```bash
php bin/magento module:enable Jovepay_Checkout
```

### 3. After Downloading The Plugin

In order to proceed further, please run the following commands:

```bash
php bin/magento setup:upgrade
php bin/magento setup:di:compile
php bin/magento setup:static-content:deploy -f
php bin/magento cache:flush
```

You can now enable and adjust JOVEpay by implementing these steps:

**Stores → Configuration → Sales → Payment Methods**

<!-- IMAGE PLACEHOLDER: Magento admin — Stores → Configuration → Sales → Payment Methods -->
![Magento Payment Methods navigation](https://res.cloudinary.com/gysvswrq/image/upload/v1789253020/admin-payment-methods-nav.png)

## Plugin Configuration

On the configuration page, scroll to the **JOVEpay** payment method box and fill in the settings for your store.

<!-- IMAGE PLACEHOLDER: Magento admin — JOVEpay payment method configuration panel -->
![JOVEpay payment method configuration](https://res.cloudinary.com/gysvswrq/image/upload/v1789252800/admin-jovepay-config.png)

1. Make sure **Yes** is selected in the **Enabled** option. You can change the **Title** according to your preferences.
2. Optionally enable **Testnet Mode** for safe end-to-end testing.
3. Choose the payment widget theme with **Dark Mode Checkout**:
   - **No** — light theme
   - **Yes** — dark theme
4. Enter a valid **Merchant ID** and **IPN Secret** from the JOVEpay dashboard (see below).
5. Be sure when selecting **New Order Status** and **Paid Order Status**, because these appear on your website when the order status is displayed to the customer.
6. Optionally enable **Debug** to write IPN details to `var/log/jovepay.log`.
7. To save this setting, use the **Save Config** button at the top right of the page.

The payment widget language follows the storefront locale automatically (for example `en`, `de`, `fr`, `es`, `ar`, `zh`, and others supported by JOVEpay).

## Get Credentials From JOVEpay Dashboard

Before enabling payments, complete the following in [app.jovepay.com](https://app.jovepay.com/):

1. Sign in (or create and activate) your merchant account.
2. Open **Payment Settings**.
3. Under **[API](https://app.jovepay.com/en/apikey-settings)**, copy your **Merchant ID** / API key.
4. Under **[Webhooks](https://app.jovepay.com/en/webhooks-settings)** (Instant Payment Notifications), copy your **IPN Secret**.
5. Head back to your Magento store, paste these values into the JOVEpay payment method settings, and click **Save Config**.

Payment processing is handled by JOVEpay. See [jovepay.com](https://www.jovepay.com) for terms and privacy details.

## How To Make Payment

1. Once a customer fills in the mandatory details and orders a product, the system takes them to the Magento checkout payment step.
2. They select **JOVEpay** (or the title you configured) and click **Place Order**.

<!-- IMAGE PLACEHOLDER: Magento storefront checkout — JOVEpay selected as payment method -->
![Magento checkout with JOVEpay selected](https://res.cloudinary.com/gysvswrq/image/upload/v1789253020/checkout-select-jovepay.png)

3. Magento redirects them to the JOVEpay hosted payment widget. The widget supports **light and dark themes** and the store’s language.

<!-- IMAGE PLACEHOLDER: JOVEpay hosted payment widget — light theme -->
![JOVEpay payment widget (light theme)](https://res.cloudinary.com/gysvswrq/image/upload/v1789253021/payment-widget-light.png)
<!-- IMAGE PLACEHOLDER: JOVEpay hosted payment widget — light theme -->
![JOVEpay payment widget detail page](https://res.cloudinary.com/gysvswrq/image/upload/v1789253021/payment-widget-detail.png)

![JOVEpay payment widget processing page](https://res.cloudinary.com/gysvswrq/image/upload/v1789253021/payment-widget-processing.png)

![JOVEpay payment widget on redirecting](https://res.cloudinary.com/gysvswrq/image/upload/v1789253021/payment-widget-redirecting.png)

4. The customer pays with their preferred cryptocurrency.
5. JOVEpay sends a signed IPN to Magento. The plugin verifies the signature, updates the order status, and can create an invoice automatically.
6. Once payment is confirmed, the customer is redirected to the Magento order success page.

<!-- IMAGE PLACEHOLDER: Magento storefront — Thank you / order success page -->
![Magento thank you for your purchase](https://res.cloudinary.com/gysvswrq/image/upload/v1789253020/checkout-success.png)

Congratulations! The customer has successfully paid for the product with JOVEpay.

## Check Order Details

1. Go to your Magento admin panel menu and click **Sales**. Once the sidebar opens, click **Orders**.

<!-- IMAGE PLACEHOLDER: Magento admin — Sales → Orders list -->
![Magento Sales → Orders](https://res.cloudinary.com/gysvswrq/image/upload/v1789253020/admin-orders-list.png)

2. Once you reach the orders page, you will see a list of your orders. Select an order paid using JOVEpay’s payment option.
3. Click **View** on the order. Confirm the payment method and that the order status matches your configured **Paid Order Status** after a successful IPN.

<!-- IMAGE PLACEHOLDER: Magento admin — order view showing JOVEpay payment details -->
![Magento order view with JOVEpay payment](https://res.cloudinary.com/gysvswrq/image/upload/v1789253020/admin-order-view-jovepay.png)

4. If debug logging is enabled, review `var/log/jovepay.log` for IPN details when troubleshooting.

## Features

- Hosted JOVEpay payment widget with **light and dark themes**
- **Multi-language** checkout UI based on the Magento store locale
- HMAC-signed Instant Payment Notifications (IPN)
- Automatic invoice creation on successful payment
- Configurable order statuses and testnet mode
- Optional debug logging to `var/log/jovepay.log`

## Release Notes

  ### Version 1.0.0 (Initial Release)

  - Initial public release of the JOVEpay crypto payment gateway for Magento Open Source and Adobe Commerce 2.x
  - Hosted payment widget with light and dark themes
  - Multi-language checkout UI based on the Magento store locale
  - HMAC-signed Instant Payment Notifications (IPN) with signature verification
  - Automatic invoice creation on successful payment
  - Configurable new/paid order statuses, testnet mode, and optional debug logging
  - Merchant ID and IPN Secret stored as encrypted admin configuration
  - Storefront and admin strings translatable, with locale packs included
  - Payment method disabled by default until configured

## Support

- Email: [dev@jovepay.com](mailto:dev@jovepay.com)
- Website: [https://www.jovepay.com](https://www.jovepay.com)

## License

GPL-3.0-or-later. See `LICENSE.txt`.

---