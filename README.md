# Project Lobster engineering
This is the Project Lobster Engineering public repo. The objective of this repo is to share public information to the world about *how* we do the tech in Project Lobster.

## Tech stack and ecosystem
Our Tech assets and needs fall into two big categories:

### An e-commerce storefront
Our website https://projectlobster.com/ is both tasked of our international and national sales, as well as informing and convincing our national customers of to come to our stores.

We use Shopify to abstract the most complicated parts of an e-commerce (payment processing, load balancing, deployment, working and clean CMS). We leverage their Themes to offer an (almost) fully customisable user experience, while leaving the heavy lifting and API management to Shopify.

The role of [Shopify tech](https://shopify.dev/) is to allow both our potential and existing customers to browse our latest products and news. 

While working on it, you will see plenty of the following: 
- Plain old HTML5
- Plain old Javascript
- Plain old CSS
- The [Shopify ecosystem](https://shopify.dev/), in particular their server-side-rendering language [Liquid](https://www.shopify.com/partners/blog/115244038-an-overview-of-liquid-shopifys-templating-language)
- Git & Github
- Build pipelines, even though we only use them to compress and treat our javascript and css assets

And in our case:
- [TailwindCSS](https://tailwindcss.com/) to easily apply styles
- [AlpineJS](https://alpinejs.dev/) to easily add light Javascript interactions to the HTML


But, as we soon found out that a pair of prescription lenses can have hundreds of different field combinations, and a simple mismatch will cause the customer to not see properly: we realised we needed something a bit more custom to take care of our operations and quality control. 

The operational handling of our orders comes goes beyond any existing application and is taken care with a custom in-house solution:


### A custom full-stack admin application
Managing an e-commerce is hard. Selling prescription glasses is also hard. Doing both at the same time with stores is quite hard.

In order to offer the best, quickest, and seamless experience for our customers: we developed a custom application that allows us to keep track of what we sell, who do we sell it to, when, and how.

This custom application is mainly made for inside usage. Its primary users are our stores coworkers, that use it to track their operations day to day and scale the communications with our customers. So that they get the best possible experience, while allowing us to scale our sales of more than 1000 glasses fully customized glasses every month across the globe.

For the inner tech structure: we are big believers on the [Majestic Monolith](https://m.signalvnoise.com/the-majestic-monolith/) for small teams of development.

That means we don't work with popular heavy JS frameworks like React, Vue, or Angular. Mainly because we prefer a server-side-first approach, because it is more simple, straigh-forward, and stable accross clients.

That makes its front-end simple, and lightweight. In order to work on it we mainly work with:
- All of the technologies mentioned in the last part for the front-end of the admin side
- And supplement it with [AlpineJS](https://alpinejs.dev/), a lightweight javascript framework more geared for server-side rendered applications.

As for the back-end side, we mainly use:
- Node.js for the runtime, and organized in a MVC architecture following the [AdonisJS](https://adonisjs.com/) framework
- PostgreSQL for the database. Not only commands, but constraints, data structure, migrations... 
- a basic level of Typescript (existing Types, Type inference, custom Types and Interfaces)
- unit testing (Test Driven Development)
- integration and system testing with [Playwright](https://playwright.dev/)
- Heroku to deploy

[AdonisJS](https://adonisjs.com/) is a fully-featured back-end framework written in Typescript (but you can completely understand with with Javascript) that we use to organize our repository, and abstract the most basic levels of any HTTP based application: routing, asset handling, server-side view rendering, Database ORM....



Here are some examples of past and planned interesting projects we do:
- Lobster Just-in-time: stock and offer hundreds of prescription lenses references to cut and sell in under an hour, across several stores. 
As well as making a custom component on our website so that customers can see where their prescription is available, and to even order it online to deliver prescription glasses in under 3 hours.
- Lobster virtual-try-on: connect the API of an external virtual provider to our website to offer virtual-try-on to our customers on the collection and product pages.
- Creating a testing system to automate front-end end-to-end testing before every Git push to ensure the highest level of quality development without manually testing everything.
- Integrating external lenses providers APIs to estimate the cost down to an order item level. Giving insights our most to least profitable best-sellers.
- Looking for and integrate into a service that will allow our ops team to draw custom charts and reports without using any code, independently.



## Workflows and team values
We work in cycles. In these cycles we assign work in the form of self-contained and (mostly) independent tickets. That have been throughly explained and redacted by either the Head of Technology, yourself, or another co-worker helped by a programmer. Cycles usually take two weeks for the most part. We use [Linear](https://linear.app/) to handle the tickets and discussions, Github to completely track the work we do, and [Basecamp](https://basecamp.com/) to communicate with the rest of the company.

Which tickets to prioritise will be decided by the stake-holders. But each developer can choose which tickets to tackle themselves. 

Tickets are not only about writing code: maybe you need to go to a store to talk to your co-workers on a improvement or new feature. Maybe you need to define with the Head of Technology a new process or improvement. Shaping and writing a really complicated or important ticket is work itself, so it should be assigned as such.

When working with design heavy tasks: you will follow a Figma design provided to you by the team's designer. Probably with a mobile, and desktop view to ensure good responsiveness.


We expect you to be agile, independent, and accountable of your work. But we know that just asking it without giving anything in return is just not fair.

We believe in the Agile manifesto, particulary in:
- pair programming. Developers should talk and work on code between them often, even more importantly when it comes to big changes
- testing your own code. Things will go wrong from time to time. If the didn't: it means that we are not being quick or independent enough. But we need to minimise those risks and increase our confidence in shipping quality bug-free code by testing it. And automatic tests at that. 
- no code silos. All developers need to work on everything so that there are no specialities.
- the right and obligation to refuse work you are not confident on how to do it Either because it has not been correctly shaped and described, or because you lack the specific knowledge in certain technologies to make it happen: it is your responsibility to say "I don't know how to do this". We, the developers, are the ones with technical knowledge to, at least estimate, how hard or possible something is.
- the right and obligation to ship good code. This means safe, well tested, and code you are proud of. You will probably ship bugs that will go in-between the tests now and then, but you should never consciously leave a mess behind when you pushed the commit button.

You also have to keep in mind that, even though each of these values need to be uphold at every single commit: *the amount varies on how complex, dangerous, or important the commit is to the business*.

If you are switching the padding of a button that the designer asked you: we do not need to pair program, don't worry. But if the head of operations wants to introduce a new concept of Lenses that needs database migrations and major Model changes: you can bet your search history we are going to talk about it and throughly test it.


