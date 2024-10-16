# Promt.cash integration examples
This repository contains code examples of how to integrate [Prompt.cash](https://prompt.cash) 
as a payment processor in your backend.

See our [API reference](https://prompt.cash/pub/docs/) for detailed descriptions
of each parameter used in the following examples.

## static page
This is the most minimalistic integration example into a [static HTML page](static).
It will generate a new address for every payment. You can then view a payment history including
"payment description/reference" and used addresses in your account.

#### Installation
Just put the 2 HTML files on your webserver and customize the `input` values
in the `form` tag.


## Node.js
See the [nodejs](nodejs) folder.

This example can add server-side parameters (such as order ID) and 
add a signature to each payment to prevent spoofing.

#### Installation
In the `index.js` file, add the following:
- your Account `PublicToken` and `SecretToken`
- customize payment amount, currency and other parameters as needed
```
yarn install # npm works too
yarn start
```


## PHP
See the [php](php) folder.

This example can add server-side parameters (such as order ID) and
add a signature to each payment to prevent spoofing.

#### Installation
In the `config.php` file, add the following:
- your Account `PublicToken` and `SecretToken`

In the `index.php` file, add the following:  
- customize payment amount, currency and other parameters as needed


## WordPress
Just download our [WordPress plugin](https://wordpress.org/plugins/prompt-cash-monetize-your-blog-with-bitcoin-cash/).

You can install it directly within WordPress under Plugins -> Add New


## Payment Control flow
``` text 
     +-------------+                      +-------------+                      +-------------+
     |             |                      |   Merchant  |                      | Prompt.Cash |
     |   Customer  |                      |   Website   |                      | Payment     |
     |             |                      |             |                      | Gateway     |
     +-------------+                      +-------------+                      +-------------+
            |                                     |                                   |
            |--(1)--Payment Request-------------->|                                   |
            |                                     |                                   |
            |<--(2)--Generate Payment Form--------|                                   |
            |                                     |                                   |
            |---(3)--Click "Pay" & Go to Gateway------------------------------------->|
            |                                     |                                   |
            |                                     |<---(4)--Payment Success Callback--|
            |                                     |                                   |
            |<---------------------------------(5)--Send Customer back to Return URL--|
            |                                     |                                   |
            |                                     |                                   |
```


## Contact
Follow me on [Twitter](https://twitter.com/ekliptor) and [Memo](https://memo.cash/profile/1JFKA1CabVyX98qPRAUQBL9NhoTnXZr5Zm).
