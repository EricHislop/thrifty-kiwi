---
title: "Setting Up a Hugo Stacks Blog"
description: 
date: 2023-03-20T23:37:10+13:00
image: programmers_desk_with_lots_of_computer_screens.png
math: 
license: 
hidden: false
comments: true
draft: false
categories:
    - Tutorials
tags:
    - Hugo
    - Favicon
    - Github-Pages
---

# Setting Up Hugo Theme Stack

[Hugo](https://gohugo.io/) is a fast and flexible static site generator that allows you to build websites quickly and easily. One of the many benefits of using Hugo is the variety of themes available. In this tutorial, we will cover the setup process for the [Stack](https://github.com/CaiJimmy/hugo-theme-stack) theme, which is a modern and elegant theme that is perfect for building portfolios, personal websites, and blogs.

## Prerequisites

Before getting started, you will need to have the following software installed on your computer:

- [Git](https://git-scm.com/)
- [Go](https://golang.org/)
- [Hugo](https://gohugo.io/)

## Setup

To get started, you'll need to create a new repository on GitHub and use the Stack theme starter template. To do this, follow these steps:

1. Click the "Use this template" button on the [Stack theme starter template](https://github.com/CaiJimmy/hugo-theme-stack-starter) repository.

2. Name your repository and click "Create repository from template".

3. Clone the repository to your local machine using Git.

4. Run `hugo server` to start the local development server and see the default Stack theme in action.


## Setting Up Favicon

To set up a custom favicon for your Hugo site, follow these steps:

1. Create an SVG file with the desired icon. For example:


```
<svg xmlns="http://www.w3.org/2000/svg">
      <text y="26" font-size="26">🥝</text>
</svg>
```

2. On Windows you can press the Windows key and . to bring up emojis to use as a favicon.
3. Save the SVG file as `favicon.svg` in the `static` directory of your Hugo project.
5. Add the following link tag to the `layouts/partials/head/custom.html` file:

    ```<link rel="icon" type="image/svg+xml" href="/favicon.svg">```

4. Run `hugo server` to view the site with the custom favicon.

## Hosting on GitHub Pages

To host your Hugo site on GitHub Pages, follow these steps:

1. Push your changes to the repository on GitHub.
2. In the repository settings, navigate to the "Pages" section.
3. Under "Source", select the branch you want to deploy (usually main) and click "Save".
4. Wait a few minutes for GitHub Pages to build and deploy your site.
5. Visit ```https://<your-username>.github.io/<your-repository-name>/``` in your browser to see your site live on GitHub Pages.

## Conclusion

In this tutorial, we covered the setup process for the Stack theme in Hugo. We also showed you how to set up a custom favicon and host your Hugo site on GitHub Pages. With this knowledge, you should be able to build a beautiful and functional website using Hugo and the Stack theme. Happy building!