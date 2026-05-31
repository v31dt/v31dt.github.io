---
title: "PromoRadar"
date: 2026-04-30
draft: false
hidden: false
description: "A project reflection on PromoRadar, a Belgian supermarket promo aggregator I am developing with a course friend."
tags: ["project", "web-development", "promoradar", "supermarkets", "collaboration"]
---

[PromoRadar](https://promoradar.be/) is a project I have been developing with my course friend @dedus. The idea is straightforward: collect promotions and sales from the five biggest Belgian supermarkets, Aldi, Lidl, Carrefour, Colruyt, and Delhaize, and notify people when something they actually buy goes on sale.

The target audience is mainly middle-aged and elderly people who are careful about how much they spend on groceries. For that group, a small price difference matters, especially when it repeats every week. Grocery shopping is not a one-time purchase. It is a routine, and routines are exactly where better information can save real money over time.

We focused on the categories that usually take up the biggest part of a typical basket: fresh meat and fish, charcuterie, drinks, beer and wine, dairy, snacks, frozen food, household products, baby products, and pet supplies. Those categories are practical. If someone cares about chicken, water, dog food, pampers, or cleaning products, they should not need to manually open five different supermarket websites every week just to check whether there is a good deal.

The main functionality is alerts. A user should be able to follow a category or product type, for example "chicken", "beer", "water", "dog food", or "pampers", and get notified when one of the big supermarkets has a relevant promotion. Everyone knows Colruyt is usually cheap, but that is not the whole point. Sometimes another supermarket has a sale you did not know about, and that is exactly the kind of thing PromoRadar should catch.

The comparison layer is still useful, but it supports the alert idea rather than replacing it. Users should also be able to view current sales per supermarket, search through them, filter by category or product type, and compare similar promotions when they want to plan a shopping trip more actively.

This project has also been harder than I expected because supermarket data is messy. Categorizing products sounds simple until you actually deal with the different backends, naming styles, category structures, missing fields, and weird edge cases. The technical challenge is not only collecting data. It is normalizing it enough that an alert for "chicken" or "baby products" actually catches the right promotions without drowning the user in unrelated results.

That made the project a good exercise in building something for real users instead of only building around the technology. The product only works if it stays simple enough for the people it is meant for, even when the data underneath is inconsistent.
