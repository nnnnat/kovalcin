---
layout: post
title:  "A Beginner's Guide to Performant Design Decisions"
date:   2015-10-02 10:30:30
---

_This article was originally published on [the Foundry](http://seesparkbox.com/foundry/beginners_guide_to_performant_design_decisions) on September 21, 2015._

I’m extremely excited by the influx of practitioners of all roles becoming interested in performance. There has been a large change in the conversation, thanks in no small part to [Lara Hogan’s book](http://designingforperformance.com/) (available for free—you have no excuse not to read it!) discussing the real performance issue being company culture and process.

I’m a firm believer that good performance requires education—not only for our own teammates of all disciplines but education for our clients from the first day of our engagement about how and why performance benefits our project. Only after we are all on the same page can performance truly shine throughout the entire process. One of my favorite performance conversations that has been picking up steam has been centered around [what other roles outside of development](http://pathtoperf.com/) can do to prioritize performance in our work, specifically designers. There are many things that a designer has to balance to craft a thoughtful and useful design, and aesthetic is a wildly important piece of that. Many people think that a fast site means boring design, but it is a balancing act to ensure that a site looks beautiful while delivering the content fast. Through trial and error the past year or so, I have found and tested various processes that help me keep performance as a priority in my work.

<!--more-->

Whether your company already fosters a culture around performance or you’re a designer starting to learn the implications of your aesthetic choices, here are some tips to consider when beginning to incorporate performance in designs.


###Image Optimization
This may seem like a no-brainer, but it’s crucial for performance to ensure that everyone working on the site, especially designers, choose the [right image format for the right purpose](http://larahogan.me/images/). It’s even more important that we properly educate our clients on choosing the right format as well, as they will more times than not be the ones uploading the images to their content management system.

Beyond making sure the image files themselves are optimized, we also want to make sure that our designs are optimized and consider images across the entire system. How many instances of the same image are we loading (and is it necessary to load all of them)? Are they all using the same aspect ratio? If not, can we change the design so that they are? We want to minimize the number of images we have to load, especially if it’s the same product shot used across the site in different contexts.

There are a variety of ways certain patterns can be handled to best optimize the image assets that are present—what’s most important to keep in mind is to have conversations with developers throughout your design process about what the fastest solution could be and openly iterate accordingly. These are where we can make concessions in our design choices to benefit performance without forfeiting personality.

###Fonts
One of the easiest ways for designers to create more performant designs in an impactful way is to be mindful of how many font weights they design with, and ultimately will be loaded in their font kit. Fonts are loaded on every page, so it’s a performance hit that spans the entire site.

As early as choosing the typeface, we can consider performance in our designs. [I’ve previously written about](http://cognition.happycog.com/article/7-alternatives-to-popular-web-typefaces-for-better-performance) the importance of designers considering this facet of typeface decision-making in addition to all the other things we take into account when choosing the right typeface. It’s not necessarily an “either/or” scenario where we can either have the typeface that we love or we can have the fast typeface. Similarly, there’s not a hard rule about what types of typefaces are faster than others. Performance is simply another consideration to factor into what typeface you choose to implement.

There are many resources about the [flash of unstyled text](https://css-tricks.com/fout-foit-foft/) and debates about the performance implications of self-hosting or using a service. While that’s more in the developer’s realm, the ways that designers can control a font’s performance fall directly on how we design and order our entire typographic hierarchy across the site. Generally, I try to not use more than 4 total different font weights across an entire site. That can be any mixture of different typeface or font families (for example: 2 from typeface A + 2 from typeface B or 3 from typeface A + 1 from typeface B). If you’re loading a weight in your font kit that you are not currently using “but might use in the future”—remove it. We don’t want to add unnecessary maybes to our design, we want it well-thought out and with every performance hit having a purpose.

Bonus—I’m also a fan of mixing in system fonts, when appropriate. It’s like the zero-calorie version of fonts: it adds no weight!

###Design Patterns
With almost any design pattern we create, there will probably be a way that we can explore a better option—and that better option should include how it will be built and loaded to optimize for performance. Not sure what could be optimized about a certain design pattern? Sit down with a developer (bonus points if it’s one who will be building the project), spend a few minutes discussing the pros and cons of all the build options, and find the holes in your solution that could be made more performant.

For example, I worked on a site where large quality product images were a huge performance hurdle. We had several design iterations for how to click a product image and display the necessary information to learn more about that product. Through trial and error, we eventually landed on a solution where the modal would display inline around the original product image so that it was just relying on CSS to style the modal box around the original image and not bogging down the page with an additional load of that same image. I never would have reached that solution for that particular design pattern without brainstorming and iterating with my teammate.

###Icons
A cohesive icon system is something that designers strategize about for more projects than not. Being mindful of not only how many icons we are using but also the formats of our icons is vitally important for the performance of the sites we design. Using PNGs versus SVG versus icon fonts all have their performance gains and losses. At Sparkbox we prefer using SVG whenever possible due to the smaller file size, ability to customize with CSS, and [a plethora of other reasons](http://seesparkbox.com/foundry/a_bit_about_svg). Being mindful of the icons that you use and create—and how many bezier curves, points, and all of the math-y components that make up the complexity of the SVG—is important. The complexity of the icon can add more points to the vector shape and add weight to the icon itself. While the file size of 1 icon will probably not make or break the site, the complexity of all of the icons together within the system will add up.

Speaking of the entire system, one of the things that I like to do is to copy over all the icons I’m using to a blank document. This helps me keep track of what icons I have available to use and where, so as to not create different icons for the same purpose.

###Social Shares, Ads, and Other Heavy-Hitters
On every project there are going to be requirements that sneak up and eat up all our [performance budget](http://timkadlec.com/2013/01/setting-a-performance-budget/). The best thing we can do is to educate our client upfront about the implications of loading these third-party scripts, extra libraries, video advertisements, and the like. The second-best thing we can do is to minimize the risk associated with using things like this. Coming up with a strategy at the intersection of content and design can help alleviate a client’s desire to load heavy “share” functions on every page and instead minimize the places we use these heavy-hitters by only using them at strategic points in our experience flows and in design priority.

###This Is Only the Beginning
While there are many hurdles designers face to bring sites to life (while still remaining fast on subpar connection speeds), there is hope that the conversation is changing and that the technology is at a point to help us improve our ideas in a faster way. Additionally, a well-planned performant design can only be made faster by implementing good [perceived performance](https://www.filamentgroup.com/lab/weight-wait.html) practices, or “heavy” design solutions can be implemented in a way that makes them feel faster. While I can’t offer absolute rules and numbers for designers to follow that are the fastest solution, I can offer support and encouragement that every design has the potential to be made faster through experience, education, and collaboration with teammates.