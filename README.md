# Cardstream (cardstream)

Cardstream is an independent United Kingdom payment gateway providing a white-label payment platform that banks, PSPs, ISOs, acquirers and software companies resell under their own brand. It connects merchants to the card schemes, digital wallets and 150+ Alternative Payment Methods from a single integration, with PCI DSS Level 1 processing, tokenisation, recurring billing, 3-D Secure 2, risk/fraud checking and dynamic currency conversion. Its developer surface is a mature form-post gateway API — not a JSON/REST API and with no downloadable OpenAPI — exposed through Hosted, Direct and Batch integration methods and supported by SDKs across eight languages plus e-commerce modules.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/cardstream/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/cardstream/refs/heads/main/apis.yml)

## Tags

- Payments
- United Kingdom
- Payment Gateway
- Payment Processing
- White Label
- Card Payments
- Acquiring
- Hosted Payment Pages
- Tokenization
- 3-D Secure
- Alternative Payment Methods
- Subscriptions

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### Cardstream Gateway - Hosted Integration

Hosted Payment Pages (HPP) integration. The customer's browser POSTs a URL-encoded request to the Gateway, which collects and processes payment details on a Cardstream-hosted page (lightbox, redirect or iframe) and POSTs the signed result back to the merchant's `redirectURL`, keeping cardholder data out of the merchant's PCI scope.

- **Human URL:** [https://guides.gitbook.io/integrationguide/getting-started/introduction-to-our-gateway/integration-methods](https://guides.gitbook.io/integrationguide/getting-started/introduction-to-our-gateway/integration-methods)
- **Base URL:** `https://gateway.cardstream.com/hosted/`

#### Properties

- [Documentation](https://guides.gitbook.io/integrationguide/)
- [API Reference](https://guides.gitbook.io/integrationguide/gateway-functionality/features/new-transactions/request-fields)

### Cardstream Gateway - Direct Integration

Server-to-server integration. The merchant collects payment details on its own secure server and sends a URL-encoded HTTP POST directly to the Gateway, supporting sales, refunds, cancellations, 3-D Secure 2, tokenisation and management requests. Can be paired with Hosted Payment Fields so card data is tokenised by the Gateway first.

- **Human URL:** [https://guides.gitbook.io/integrationguide/getting-started/introduction-to-our-gateway/integration-methods](https://guides.gitbook.io/integrationguide/getting-started/introduction-to-our-gateway/integration-methods)
- **Base URL:** `https://gateway.cardstream.com/direct/`

#### Properties

- [Documentation](https://guides.gitbook.io/integrationguide/)
- [API Reference](https://guides.gitbook.io/integrationguide/gateway-functionality/features/new-transactions/request-fields)
- [Authentication](https://guides.gitbook.io/integrationguide/getting-started/setting-up-your-integration/authentication)

### Cardstream Gateway - Batch Integration

An enhancement to the Direct Integration that submits multiple transactions in one `multipart/mixed` HTTP POST. The Gateway queues them and returns a batch reference used to download a status file — useful for capturing many transactions or collecting recurring subscription and loan-repayment charges. No interactive (3DS/wallet) flows.

- **Human URL:** [https://guides.gitbook.io/integrationguide/getting-started/introduction-to-our-gateway/integration-methods](https://guides.gitbook.io/integrationguide/getting-started/introduction-to-our-gateway/integration-methods)
- **Base URL:** `https://gateway.cardstream.com/direct/`

#### Properties

- [Documentation](https://guides.gitbook.io/integrationguide/)
- [API Reference](https://guides.gitbook.io/integrationguide/getting-started/setting-up-your-integration/integration-details)

### Cardstream Hosted Payment Fields

A client-side library where only the input fields collecting sensitive cardholder data are hosted by the Gateway while the rest of the payment form is served by the merchant. On submission the Gateway returns a payment token, which the merchant processes via the Direct Integration — never handling raw card data.

- **Human URL:** [https://guides.gitbook.io/integrationguide/references/code-references/integration-libraries/hosted-payment-fields-library](https://guides.gitbook.io/integrationguide/references/code-references/integration-libraries/hosted-payment-fields-library)
- **Base URL:** `https://gateway.cardstream.com/hosted/`

#### Properties

- [Documentation](https://guides.gitbook.io/integrationguide/references/code-references/integration-libraries/hosted-payment-fields-library)

## Authentication

The Gateway is a form-post API: HTTP POST with `Content-Type: application/x-www-form-urlencoded`. Every request carries a `merchantID`; security is provided by optional `merchantPwd` password authentication, HMAC message signing (a `signature` field hashing the serialised request with a per-merchant signing secret, with signed responses and signed callbacks), and IP allow-listing. There is no OAuth2/OIDC or mTLS surface, and no downloadable OpenAPI/Swagger definition.

## SDKs & Modules

PHP, Java, Node.js, Go, Ruby, C#/.NET, iOS (Swift) and Android SDKs, plus Magento, WooCommerce, OpenCart and PrestaShop e-commerce modules — all on the [Cardstream GitHub organization](https://github.com/cardstream).

## Common Properties

- [Website](https://cardstream.com/)
- [Developer Portal](https://cardstream.com/developer/)
- [Documentation](https://guides.gitbook.io/integrationguide/)
- [Getting Started](https://guides.gitbook.io/integrationguide/getting-started/setting-up-your-integration)
- [GitHub Organization](https://github.com/cardstream)
- [Status Page](https://status.cardstream.com/)
- [Help Center](https://support.cardstream.com/hc/)
- [Login (MMS)](https://mms.cardstream.com/)
- [Blog](https://cardstream.com/blog/)
- [Privacy Policy](https://cardstream.com/privacy-policy/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
