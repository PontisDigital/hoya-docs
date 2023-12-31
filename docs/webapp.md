# Merchant Web App

We want to increase value on the merchant-side by providing various useful analytics and tools
to help them run their business. On top of that we'd like an automated system for onboarding merchants.

## Where's the Github Repo?
You may have noticed there is no repo for this project. That's because I don't have a preference on
what technology gets used. I'd imagine the choice is going to end up being React, but whatever you
all think is best is the answer. So Hoya Developers will be creating the repo, and I'll make a fork
for hosting it on our side.

## Minimum data being collected
The data we can collect from merchants actually varies. This is because some have certain restrictions
at point of sale. Below is the data that is guranteed to be available across all of our partners.

### Merchant
* `email` - merchant's email address 
* `logo_url` - a URL to the image of their logo seen on the home screen
* `name` - merchant's display name
* `round_start` - a timestamp of when the latest round has started
* `total_allowance_spent` - total allowance spent **since the round has begun**
* `merchant_uid` - a unique id for the merchant

### Sale
Every merchant has a collection of sales

* `completed_at` - a timestamp of when the sale was completed
* `id` - a unique id for the sale
* `initiated_at` - a timestamp of when the sale was initiated (when the merchant has input the price)
* `merchant_id` - the merchant's unique id
* `merchant_name` - the merchant's display name
* `paid_with_credit` - the amount covered by allowance. (`total_price - actual_amount_user_paid`)
* `status` - The status of the sale (`"complete"`, `"pending"`, or `"aborted"`)
* `user_id` - The unique id of the user

## Additional data
The following data is available for all of our merchants except for GT Vapes

### Merchant
* `total_community_spend` - The total USD spent by our customers **since the round has begun**

### Sale
* `paid_with_cash` - the amount of money the user has spent at point of sale
* `total_price` - the full price of the sale

## Stores which use Allowance
All stores except for Georgetown Gourmet also have data regarding the user's balance.
Georgetown Gourmet runs a 20% discount and does not use the user's balance.

### Sale
* `new_allowance_amount` - the user's allowance balance after the sale
* `old_allowance_amount` - the user's allowance balance before the sale

## How do I get my hands on the data?
At the moment you can't. I will spin up a hoya developer exclusive readonly HTTP API.
You can use this API to develop the web app as well. And then when it comes time to deploy, I'll
build out real production endpoints which authenticate/authorize the merchant to access the data.

If you have never worked with an HTTP API before or don't know what that is do let me know in discord.

## UI
We'll have some figma mockups in the next couple of days. It's important to be on the discord for
feedback and discussion of the UI.

## Onboarding Merchants
We want merchants to be able to join our platform with minimal manual interaction.
They should be able to select what type of rewards program they want to run.
Either Allowance, a straight up discount, or come up with their own.

