---
title: "What Really is Design Verification?"
date: 2020-12-04T05:02:46Z
draft: true
tags: ["design-verification", "dv", "industry"]
---

The hardware industry is generally misunderstood by those in other technical fields. Go on any HackerNews post about Apple's new M1 chip, and the conversations usually only discuss the products performance or what M1 means for other SoC manufacturers. Granted, these are important things to discuss, but it's in stark contrast to other posts with threads discussing new Rust features, or why Go still doesn't support generics.

I can't really blame those in other technical fields, though. There are very few resources for learning about the hardware industry online, and a web developer will gain virtually no career-building skills for learning about out of order CPU execution. Regardless, those who are curious should have an avenue for learning about this industry aside from Wikipedia and overpriced textbooks.

While I am not an expert in every field of the hardware industry, I do have experience with one field in particular: Design Verification, or DV for short. With this post, my goal is to describe the purpose of this role, how it fits into the SoC product lifecycle, and what makes a DV engineer good at what they do. Hopefully I can convince you that DV isn't the same thing as software QA -- it's a complex domain that you can even focus on in master's or doctorate degrees.


### Nanofabrication: Big Risk, Bigger Reward
Consider a critical bug found in production at your software company. How much does it cost the company to fix that bug? Usually, it only costs as many hours as the engineer needed to spend to fix that bug. With modern continuous integration and rolling releases for many products, even a moderately complex bug can be fixed in a few hours and shipped with the next release of the product.

I'm taking plenty of liberties with this statement ("My bugs take a lot more than a few hours to fix!" and "But QA needs to make sure I didn't break anything else!"), but bear with me.

Now, consider a cricial bug found _in a CPU that was just put on shelves_. How much does it cost the company to fix _that?_ The term *hard*ware really does live up to its name. Not only is it hard as in challenging, but it's hard as in "hard to modify after its completed." In many cases, it can cost a company millions of dollars to recall a piece of hardware, along with thousands of person-hours finding the bug, fixing it, re-fabbing the part, and re-shipping it. 

This is why design verification is critical to the semiconductor industry. Without it, one simple bug can waste the company millions of dollars, and most likely make the product miss its market opportunity. 
