---
title: "Easter Eggs Are Never Okay"
date: 2020-12-22T12:07:17-08:00
tags: ["software", "codebase", "easter-egg"]
---

## The Parable 
You're writing a class to connect to your company's application. You and your colleagues all agree that the feature this class is for is the coolest thing you've ever heard of -- it's the "bees knees," one of your colleagues keeps jesting. 

Next thing you know, the driver of you mobbing session renames the class to `the_bees_knees`. Everyone giggles and moves on to working on other parts of the code base.

Unbeknownst to them all, they all just became accomplices in a crime yet to be committed. Five years later, a new developer at the company committed several instances of murder. When he was caught and confessed, his reasoning was "I was thrown into an uncontrollable rage while refactoring code because someone thought `the_bees_knees` was a good thing to name their class."

## The Moral
The above is obviously satire, but it is grounded in reality, since I had to deal with a class named `the_bees_knees` only a few weeks ago. The moral of the story certainly sounds like "Easter Eggs are bad," but what really _is_ an Easter Egg, and what kind of Easter Egg are we talking about here? 

[Merriam-Webster](https://www.merriam-webster.com/dictionary/Easter%20egg) defines an Easter Egg as  "a **hidden feature** in a **commercially** released **product.**"
In most cases, this describes a _Consumer-facing_ Easter Egg, since these features are included in the product in order to entertain customers. However, this same definition can apply to what I define as a _Developer-facing_ Easter Egg. The difference is in the bold words from above:

* **product**: The code itself _is_ the product that is being given to other employees.
* **commercial**: The code itself is commercial in the sense that it is a product given to other employees to maintain.
* **hidden feature**: The code can contain features that _only the programmer_ can see. Some examples include ASCII art in comments, or strings that contain references to cult-classic movies.

Customer-facing Easter Eggs are absolutely fine, since they add value to the product that you're creating. Dedicated fans can find these Easter Eggs and be entertained by them. At best, _Developer_ facing Easter Eggs add value to the code in a non-optimal way, and at worst, their existence makes the code more unmaintainable.

Therefore, I claim the moral of the story is the following:
> Developer-facing Easter Eggs in your codebase are never okay. Developer-facing Easter Eggs are an easily avoidable, existential threat to the maintainability of your code, with the only benefit being the potential of a few laughs from your coworkers.

A few examples of developer-facing Easter Eggs:
* Naming a class `the_bees_knees`
	* Completely non-descriptive of the class's purpose. How is anyone who inherits this code supposed to understand it?
* ASCII art in comments
	* What purpose does this serve? The one case I can think of is if your code generates ASCII art, and the comment describes what the code is supposed to produce.
* A movie quote as the string input of a function for a unit test
	* While this example is not as bad as the previous ones, it is still bad because the string could be more descriptive for the purpose of the test. For example, if you want the test to fail with an exception, the string "BAD STRING" could suffice. 
* "Meme numbers" in unit tests (420, 1337, etc.)
	* Again, not a terrible Easter egg to have, but you run the risk of limiting what your test suite tests if you use these numbers all over the place. If you are to use these numbers as inputs to a function like they're "some random number," then ensure you use them sparingly.

If your goal is to make code that makes other programmers laugh, then by all means add developer-facing Easter Eggs into your code. Otherwise, you should recognize that your code is a product, and its selling point to your coworkers is its functionality and maintainability -- _not_ how many inside jokes you can stuff inside of it.

