## Marketplace listing fields

Use these fields in the Commerce Marketplace seller profile. Do not paste this section into the Long Description.

| Field | Suggested value |
| --- | --- |
| Product title | JOVEpay Crypto Payments |
| Demo store | [https://magento.jovepay.com](https://magento.jovepay.com) |
| Documentation | [https://www.jovepay.com/docs/plugins/magento](https://www.jovepay.com/docs/plugins/magento) |

**Title notes (Adobe marketing review):** Up to five words; Title Case; no Magento / M2 / Extension / Module / Plugin; JOVEpay is allowed because it is the integrated service name. See [Marketing review guidelines](https://developer.adobe.com/commerce/marketplace/guides/sellers/marketing-review-guidelines).

---

## Long description

Paste the content below into the Marketplace Long Description field.

**[JOVEpay](https://www.jovepay.com)** is a cryptocurrency payment gateway that helps online merchants accept digital asset payments across multiple blockchain networks and settle funds to merchant-configured wallets. Merchants use the [JOVEpay merchant dashboard](https://app.jovepay.com/) to manage API credentials, Instant Payment Notifications (IPN), and payment settings.

This Crypto Payments extension for Magento 2 connects your Magento Open Source or Adobe Commerce storefront to JOVEpay so shoppers can pay with supported cryptocurrencies while keeping a familiar Magento checkout experience. After the customer places an order and selects JOVEpay, they are redirected to the JOVEpay hosted payment widget, complete payment with their preferred digital asset, and return to your Magento success page when payment is confirmed. Magento receives HMAC-signed Instant Payment Notifications, updates the order status, and can create an invoice automatically—so merchants do not need to manually verify blockchain transactions before fulfilling orders. Use this extension when you want to offer Bitcoin, Ethereum, stablecoins, and other supported assets alongside existing payment methods; when you sell internationally and need multi-chain coverage; or when you run a Web3 or crypto-focused store and want settlement to go directly to your wallet while Magento continues to manage catalog, cart, orders, and customers. **An additional JOVEpay merchant account is required, and JOVEpay service / transaction fees may apply. The account is not created during extension installation.**

### Features

- Accept cryptocurrency payments on Magento 2 / Adobe Commerce checkout
- Multi-chain support across networks such as Bitcoin, Ethereum, BNB Smart Chain, Polygon, Solana, Tron, and other JOVEpay-supported networks and assets
- Direct settlement to the merchant’s configured receiving wallet
- Hosted JOVEpay payment widget with light and dark themes
- Multi-language payment UI that follows the Magento storefront locale
- Redirect-based checkout to JOVEpay’s secure payment environment
- HMAC-signed Instant Payment Notifications (IPN) with automatic Magento order updates
- Automatic invoice creation on successful payment
- Configurable new-order and paid-order statuses
- Optional testnet mode for safe end-to-end testing
- Optional debug logging for IPN troubleshooting
- Encrypted storage of Merchant ID and IPN Secret in Magento admin configuration
- REST API and webhook capabilities via the JOVEpay platform for custom workflows
- Payment activity and status tracking associated with Magento orders

### Demo

- Live Magento demo store: [https://magento.jovepay.com](https://magento.jovepay.com)
- Product website: [https://www.jovepay.com](https://www.jovepay.com)
- Merchant dashboard: [https://app.jovepay.com/](https://app.jovepay.com/)

### Account and Pricing

**An additional JOVEpay merchant account is required, and JOVEpay service / transaction fees may apply. The account is not created during extension installation.** To create an account, please visit the [JOVEpay signup page](https://www.jovepay.com). After registration and activation, obtain your Merchant ID (API key) and IPN Secret from [API settings](https://app.jovepay.com/en/apikey-settings) and [Webhooks](https://app.jovepay.com/en/webhooks-settings) in the [JOVEpay dashboard](https://app.jovepay.com/). For current pricing and commercial terms, please visit [https://www.jovepay.com](https://www.jovepay.com) or contact [dev@jovepay.com](mailto:dev@jovepay.com).

### Security and PCI Compliance

Upon checkout, customers are redirected to the JOVEpay hosted payment widget. The customer completes the cryptocurrency payment in JOVEpay’s secure environment so that wallet-signing and payment confirmation do not occur inside Magento admin or as card-form fields on your storefront. Once the payment process is complete, customers are redirected back to your Magento store. No cryptocurrency private keys or card payment data are entered into or stored on the Magento server by this extension.

JOVEpay communicates payment results to Magento through signed Instant Payment Notifications. The Magento server stores standard Magento order and customer data already collected during checkout, plus merchant configuration (Merchant ID and IPN Secret, stored as encrypted admin settings) and payment status updates received via IPN. Order context such as amount, currency, and customer name/email may be passed to JOVEpay to initiate the hosted payment session. Tokenization of card data is not used, because this extension processes cryptocurrency payments rather than card-not-present card capture.

Merchants remain responsible for securing their Magento environment, wallets, access controls, and any regulatory or compliance requirements that apply to their business and jurisdiction. Review JOVEpay product terms and privacy details at [https://www.jovepay.com](https://www.jovepay.com).

### How It Works

1. The shopper completes Magento checkout and selects JOVEpay as the payment method.
2. Magento redirects the shopper to the JOVEpay hosted payment widget (light or dark theme; language follows store locale).
3. The shopper pays with a supported cryptocurrency on a supported network.
4. JOVEpay monitors the payment and sends a signed Instant Payment Notification to Magento.
5. Magento verifies the notification, updates the order status, and can create an invoice automatically.
6. The shopper returns to the Magento order success page.

### Benefits

- Reach customers who prefer to pay with digital assets
- Offer multi-chain flexibility from a single Magento payment method
- Keep settlement under merchant control with configured receiving wallets
- Automate order status updates and reduce manual blockchain verification
- Preserve your existing Magento catalog, cart, checkout, and order-management workflows

### Ideal Use Cases

- Magento Open Source and Adobe Commerce merchants adding crypto alongside existing payment methods
- International stores that serve customers across multiple blockchain ecosystems
- Digital goods, online services, technology, and Web3 businesses
- Merchants that need automated IPN-driven order fulfillment

### Supported Networks

Supported networks may include Ethereum, BNB Smart Chain, Polygon, Arbitrum, Optimism, Base, Avalanche, Linea, zkSync, Sei, Tron, Solana, Bitcoin, Litecoin, Dogecoin, Bitcoin Cash, TON, and other networks and assets enabled for your JOVEpay merchant configuration. Availability can vary; confirm current support in the [JOVEpay dashboard](https://app.jovepay.com/).

### Documentation and Support

- Magento plugin documentation: [https://www.jovepay.com/docs/plugins/magento](https://www.jovepay.com/docs/plugins/magento)
- Live Magento demo store: [https://magento.jovepay.com](https://magento.jovepay.com)
- Website: [https://www.jovepay.com](https://www.jovepay.com)
- Merchant dashboard: [https://app.jovepay.com/](https://app.jovepay.com/)
- API credentials: [https://app.jovepay.com/en/apikey-settings](https://app.jovepay.com/en/apikey-settings)
- Webhooks / IPN: [https://app.jovepay.com/en/webhooks-settings](https://app.jovepay.com/en/webhooks-settings)
- Support email: [dev@jovepay.com](mailto:dev@jovepay.com)
