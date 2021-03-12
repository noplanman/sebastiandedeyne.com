---
title: "Freek.dev redesign part 1: conception and analysis"
slug: freek-dev-redesign/part-1-conception-and-analysis
date: 2021-09-01
categories: ["articles"]
keywords:
  - Design
---

Recently, Freek and I decided to put a new coat of paint on [freek.dev](https://freek.dev). Well, not just a visual refresh, but a complete restructure of its content.

The idea sparked from [this tweet](https://twitter.com/freekmurze/status/1369936456249085952):

> I’ve been thinking about what the next step for my blog could be.
>
> A thing that is bothering me a lot is that only recent links get attention. There are a lot of interesting things in the archive that are buried under the new ones.

The main goal of this redesign project is to have the site behave more like a news site or resource library, and less like a traditional blog.

I've decided to document the entire design process, from conception to the final product.

<!--more-->

## Analyzing the current site

### Content & taxonomy

Traditionally, freek.dev has had three main content types: 

- **Posts** (aka "originals")
- **Links** to external posts with an optional quote or comment
- **Tweets** embedded and shared on the blog

In addition, it's worth exploring adding videos and livestreams as first-class post types, since those have become a lot more important since the previous design iteration.

Posts are divided into one of four categories: Laravel, PHP, JavaScript, and other. If we'd want to link related content more often, we need to use a more fine-grained taxonomy.

Another distinction between posts worth mentioning is user-submitted content. Some links are shared by users as community links.

Finally, there are a few pages and features to keep in mind. These could be part of a main or secondary navigation.

- About
- My setup
- Speaking
- Newsletter
- Advertising
- Music
- Search
- Social links
- Community section

### CTA's & sponsors

There are three types of sponsorships that need to appear:

- **Carbon:** A small ad, must be above the fold
- **Sponsor:** A message from a sponsor, placement is flexible
- **Additional Spatie/Oh Dear/FSEU placement:** Currently the sponsor message is used for this, but it might be worth giving personal projects a more personal treatment

In addition, posts and pages should contain a CTA to subscribe to a newsletter.

In the category of CTA's it might be worth mentioning upcoming livestreams, especially when the livestream is about a similar topic as the current page.

### Interaction

Some posts support comments via [utteranc.es](https://utteranc.es). All posts display webmentions. They could be displayed a lot more densely and compressed compared to the current version.

## Desk research: looking for inspiration

[Laravel News](https://laravel-news.com) and [CSS-Tricks](https://css-tricks.com) have a good feel to them. They have a clear spotlight section, and Laravel News does a lot with categorization.

![](/media/murze/laravel-news.jpeg)

[Smitten Kitchen](https://smittenkitchen.com/2021/02/the-perfect-margarita/) has a few interesting discovery features. I like the "Previously" section where they share 6/12/24/36/… month old posts. The freek.dev newsletter already has a similar feature, we could port the idea to the site too. The spotlight section in the sidebar links to both posts and taxonomies, which can be a great way to promote a specific sections (like livestreams in general, etc.)

![](/media/murze/smitten-kitchen.jpeg)

I really like the representation of meta data and related content below the posts on [openai.com](https://openai.com/blog/dall-e/), but I'm afraid it might be a bit too minimalistic for content discovery on Freek.dev.

![](/media/murze/open-ai.jpeg)

Large media sites like the [New York Times](https://www.nytimes.com/2021/03/11/dining/drinks/non-alcoholic-wine.html) are good at aggregating related content under a posts. NYT has three sections: more in {category}, most popular, and editor's picks.

![](/media/murze/nyt.jpeg)
