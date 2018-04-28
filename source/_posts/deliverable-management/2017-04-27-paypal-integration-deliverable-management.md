---
layout: post
title: Paypal integration deliverable management
category: 成果交付管理
keywords: null
---

# Before Reading(Before Reading)

1.  What you can learn after reading this article?

Paypal development deliverable for **EXPRESS CHECKOUT** with

* lowest development cost
* high reliability and security
* middle user experience

* How much time you will use for reading this article? 25 minutes

# Deliverable

Execute a integrated paypal payment from buyer@yourwebsite.com to seller@yourwebsite.com

# Basic background Knowledge

## What is developer.paypal.com

A website that provide third party integration with paypal.Your login on here using your real paypal.com account

## What is sandbox

Sandbox(<https://www.sandbox.paypal.com/>) is a test website to paypal(which have exactly the same functionality to real <https://www.paypal.com>)

# Preparation

A paypal account(You can register it on paypal.com)

## Create of sandbox account( buyer@yourwebsite.com to seller@yourwebsite.com) on developer.paypal.com

1.  Create seller& buyer

* Buyer[](https://www.awesomescreenshot.com/image/557043/af319b20-4e46-4085-66ad-55763013ec79)
* Seller[](https://www.awesomescreenshot.com/image/2510092/21a59bf325d99f6346acc73e50601538)

2.  Related user list [](https://www.awesomescreenshot.com/image/2510092/21a59bf325d99f6346acc73e50601538)

## Create apps

1.  Create Apps [](https://www.awesomescreenshot.com/image/2510126/4dbe36df97ed03ed2fc8c4a7b9f3d80a)
2.  Apps list [](https://www.awesomescreenshot.com/image/2510128/7ab5c8972ad8b7686040d70fa5994695)

## development

### Great tool - Low development cost

Use the official paypal sdk or payment processing library to greatly reduce development cost

### Security with low cost

Use express checkout with full page redirection instead of ajax api integration.

### Configuration

In sandbox environment,you should use clientID that is sandbox

### Time Cost

3 manday for senior development

## Testing

Create a purchase on your website and pay with seller@yourwebsite.com.Then check the account balance of buyer@yourwebsite.com on developer.paypal.com [](https://www.awesomescreenshot.com/image/2510120/03b9b9cb1711884fb796b189e953a5aa) . You should see the balance increase(**It will not be 100% become paypal will charge 1-2% transaction fee**)
