---
description: >-
  Customers can be your memberships or subscribe your products automatically
  with MixPay. Learn how subscriptions work within MixPay.
---

# Subscriptions

With Subscriptions, customers make recurring payments for access to a product. Subscriptions require you to retain more information about your customers than one-time purchases do because you need to automatically charge them in the future.

### How subscriptions work:

&#x20; _**Subscription objects**_&#x20;

&#x20; Use the following core API objects to build and manage subscriptions:

* Customers are your buyers. The Customer object stores information like names, email addresses, and payment methods (what kind of crypto to pay).&#x20;
* Products are what you sell. Prices represent how much and how often you charge for a product. You can define multiple prices for a product so you can charge different amounts based on currency or interval (daily, monthly, quarterly, yearly, or other customized intervals).&#x20;
* Subscriptions represent your Customers’ access to a product and require you to create a customer and payment method. The status of a subscription indicates when to provision access to your service for a customer.&#x20;
* MixPay generates Invoices when it’s time to bill a customer for a subscription. Invoices have line items and the total amount owed by a customer.&#x20;
* Payment Intents represent the state of all attempts to pay an invoice.

#### _Subscription integration_

**Landing page**&#x20;

On the frontend, the landing page collects the email address first. Your application might have other customer-specific information you want to collect like a username or address. Clicking the signup button sends the information collected on the landing page to the backend. This process creates a customer and displays the pricing page on the frontend.

**Pricing page**&#x20;

The pricing page displays the different subscription options based on the products and prices you create when you first set up your integration (you don’t need to create new ones every time customers sign up). Your pricing page displays the prices you created, and your customers choose the option they want.&#x20;

**Payment**&#x20;

The payment form collects a name and other information. MixPay hosts this form if you use Checkout-it’s one of the key features that allows you to collect payments and remain PCI compliant. Clicking **Subscribe**:

1. Creates a new subscription, with the customer and price IDs.&#x20;
2. Generates an invoice for the initial subscription cycle.&#x20;
3. Collects payment details and pays the invoice.&#x20;
4. Sets the payment method as the default payment method for the subscription, which is a requirement for subsequent payments.&#x20;

**Provisioning**&#x20;

A confirmation page displays after a successful payment. At this point it’s safe to provision the product for the customer. This generally means:

Verifying the status of the subscription is active. Granting the customer access to the products and features they subscribed to.
