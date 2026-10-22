---
layout: post
title: "Shopify Add to Cart Button Not Working? 7 Ways to Fix It"
seo_title: "Shopify Add to Cart Button Not Working? 7 Fixes | HSNLOGIX"
date: 2026-10-22
author: sania
image: /blog-images/featured-shopify-add-to-cart-not-working.webp
excerpt: "Shopify add to cart button not working? Seven checks from safest to most technical: browser, inventory and markets, templates, theme settings, apps, JavaScript errors and your theme code."
description: "Shopify add to cart button not working? Work through seven fixes in order, from device and inventory checks to app conflicts, console errors and theme code."
---

If your Shopify add to cart button is not working, the cause is usually one of four things: a browser problem, a product that is not available to buy, an app conflict, or an error in your theme code. Go through the seven checks in order, from the quickest and safest to the most technical. You will not need to touch any code until the last step.

Before you start, write down exactly what happens. Is the button missing, greyed out with "Sold out", unresponsive when clicked, or broken only on mobile? The symptom tells you which steps matter most.

## 1. Rule out a device, browser or network problem

A fault that shows up only on your own device is not a store problem, which is why Shopify's [theme troubleshooting guide](https://help.shopify.com/en/manual/online-store/themes/theme-support/troubleshooting) begins with local checks. Clear your cache and cookies, then test in a private window, a second browser and a second device. Switch to mobile data, update your browser, and make sure no VPN, firewall or ad blocker is getting in the way. If the button works everywhere except one device, your store is probably fine.

## 2. Check that the product can be bought

Sometimes a button that looks broken is the store doing exactly what it was told. Open the product in your Shopify admin and confirm the following:

- The status is Active.
- The product is available on the Online Store sales channel.
- The variant that fails has stock. Shopify treats an item as out of stock when its inventory is tracked and the level is zero or below, and by default customers cannot buy it.
- You are testing the exact variant that fails, because inventory is set per variant.

If you use several locations, watch for this trap: a location that fulfills online orders with no stock keeps the item sold out online, even when another location that does not fulfill online orders has plenty. To let customers buy past zero stock, turn on Continue selling when out of stock in the Inventory section of the product or variant. It only works when inventory tracking is on (the Track quantity or Inventory tracked setting, depending on where you look in the admin). Shopify covers both points in its guide to [selling out of stock products](https://help.shopify.com/manual/products/inventory/getting-started-with-inventory/selling-when-out-of-stock).

Two more cases to rule out:

- **Markets.** If you sell in more than one market, a product has to be in the catalog assigned to a customer's market before that customer can see and buy it. Shopify's [catalog documentation](https://help.shopify.com/en/manual/markets/customizations/catalogs) says shoppers who open a product that is unavailable in their market are redirected to your homepage. Some merchants report a 404 page instead, so check market availability before assuming the button is broken.
- **B2B.** If you sell to business customers, quantity rules on a catalog (minimums, maximums or increments) can stop a buyer from adding certain quantities.

## 3. Compare products and templates

Test three or four different products. If the button fails on only some of them, check which product template each one uses in the admin, because different templates can show different layouts and settings. If every product fails, suspect your theme, an app or a site-wide script instead.

## 4. Check theme settings and the mobile view

If the button is not visible at all, look at your theme's button color settings. Shopify's troubleshooting guide gives this very example: the button's text and background colors need to contrast, because matching colors can hide a button that is actually there.

If it fails only on mobile, switch the theme editor to the mobile view, review the product section's mobile settings, then confirm on a real phone. If the button seems unclickable in one spot, a chat widget, cookie banner or pop-up may be sitting on top of it. Turn those off temporarily and test again.

## 5. Test apps for a conflict with your theme

Apps that change the product page or the cart are a common cause. An app can attach to your theme as an app block, as an app embed, or through code added directly to theme files. In the theme editor, open App embeds, switch off the app you suspect, save, and test in a private window. If the app has no embed, check its settings or documentation.

If you installed or updated an app just before the problem began, uninstalling it temporarily is a fair test, and Shopify's troubleshooting guide suggests it. Read the app's documentation first, because removing an app can delete its settings or data. If the button still fails after removal, the app is probably not the cause. One caution from our own work: some apps leave code behind in theme files after they are removed, so a developer may need to look for leftovers.

## 6. Look for a JavaScript error and a failed cart request

Most themes add items to the cart with JavaScript that talks to Shopify's Cart API, so a script error can freeze the button even though it looks normal. You can check without changing anything:

1. Open the product page in Chrome, right-click, and choose Inspect.
2. In the Console tab, click the button. A red error shows which file failed.
3. Open the Network tab, click the button again, and look for a request to cart/add (often cart/add.js).

A 422 status means Shopify refused the request, so read the response message. Shopify's [Cart API reference](https://shopify.dev/docs/api/ajax/reference/cart) lists two common causes: the product is sold out, or all of its remaining stock is already in the cart. A 422 is its own clue, separate from console errors, and does not by itself prove your JavaScript is broken. The file name in a console error usually shows whether your theme or an app is responsible. Fixing it generally means editing Liquid or JavaScript, which is not beginner work.

## 7. Test a fresh theme, then repair your code

Add a free theme from the Shopify Theme Store (you do not need to publish it) and use Actions, then Preview, to test the button there. If it works in the fresh theme but not in yours, the problem is in your theme code or settings. If it fails in every theme, look at your admin settings and apps again. If it fails even in an updated, unmodified copy of your own theme, contact the theme's support team.

If you know which file was changed before the problem started, open it in the code editor (Online Store, Themes, Actions, Edit code) and restore an earlier version from the file's history. Restoring an old version replaces the file as it is now, and the history is limited, so copy the current contents first. Duplicate your theme as a backup before any code edit, and only edit code if you know HTML, CSS and basic Liquid.

## How to confirm the fix worked

Test in a private window on desktop and on a real phone, using more than one product and more than one variant. Confirm that the cart updates and that you can reach checkout. No single fix works for every store, because themes, apps and settings differ. If the problem returns later, repeat the checks above and note which step changes the result.

<img src="{{ '/blog-images/inbody-add-to-cart-troubleshooting-flowchart.webp' | relative_url }}" alt="Flowchart: does the button work in a fresh theme? No points to your admin settings and apps, yes points to your theme code or settings." width="1200" height="700" loading="lazy" decoding="async">

## When to bring in a Shopify developer

If the console shows errors inside your theme files, the button broke after a code change you cannot undo, or apps and custom scripts are clashing, we can investigate. Our [Troubleshooting & Support]({{ '/services/troubleshooting-support/' | relative_url }}) service covers bugs, app conflicts and checkout or theme errors, and larger fixes may fall under [custom theme development]({{ '/services/theme-development/' | relative_url }}).

If budget is a concern, our guide to [what a custom Shopify store costs]({{ '/blog/how-much-does-a-custom-shopify-store-cost-2026/' | relative_url }}) explains what drives quotes. When you are ready, send us your store URL and a short description of what happens when the button is clicked, or <a href="https://cal.com/hsnlogix" data-cal-link="hsnlogix" data-cal-config='{"layout":"month_view"}' rel="noopener">book a free strategy call</a>.
