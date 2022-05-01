---
title: Welcome to dependency hell
---

The time has come to talk about the current state of the average javascript developer experience.

## The elephant in the room: folder size

Let's create a really simple Next.js app. Nothing fancy, just running the `create-next-app` with the default parameters.

After the installation, running `du -sh node_modules` quickly highlights the problem:

```sh
$ du -sh node_modules
235M    node_modules
```

The `node_modules` folder size has quickly grown to 235 MiB, and that's just for bootstrapping our project!

As soon as we start adding more and more dependencies, we will see an even bigger folder size, and it's not long before we reach sizes in the magnitude of gigabytes.

And that is just for a single project. If you decide you want to work on two projects at once, be prepared to see the same size on another `node_modules` folder.

As an exercise, try heading over to [Package Phobia](https://packagephobia.com), look for whatever package comes to mind, and see for yourself.

## A workaround for size

To solve this multiple-project size issue, one could consider switching to [pnpm](https://pnpm.io/), an almost drop-in replacement for npm, with better size and install performance.

Still, the problem of the overly-complicated dependency trees is still a thing. At least it won't come and bite us for every project we create.

## The cost of flexibility

### Poor user experience

Time is of the essence when writing code.

Having a rough prototype shipped as soon as possible is the model many companies and developers are actively adopting, with the not-so-hidden cost of performance and size.

Sure, devices have become increasingly fast and disk sizes are at an all-time high, but application performance is still pretty much the same, we are just increasing complexity to accommodate this hardware real estate.

We have grown so accustomed to bloated, poorly-optimized web apps, that posts like [this](https://www.reddit.com/r/Telegram/comments/ma73uc/how_is_telegram_so_fast/) are becoming more and more uncommon.

### Security issues

Prior to working as a software developer, I worked for a couple of months in Application Security Testing, where one of the first things we looked for in a project were...

Outdated packages!

Another cost of flexibility - and this should really not come out as a surprise - is security.

Be it outdated libraries' vulnerability issues, or [political statements](https://fossbytes.com/developer-corrupts-faker-js-and-color-js/), sometimes avoiding to [reinvent the wheel](https://blog.npmjs.org/post/141577284765/kik-left-pad-and-npm) can have major security implications for a company.
