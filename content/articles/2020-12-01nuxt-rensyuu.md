---
title: 11/16nuxt練習
description: This is the description for the article about all the things we know
img: https://images.unsplash.com/photo-1588065394015-68bf7e40738d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=675&q=80
alt: Article 10
createdAt: "2020-11-16 11:02:57"
author: 
  name: Choi
  bio: All about Choi and where he works and what he does
  img: https://images.unsplash.com/photo-1534471770828-9bde524ee634?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60
tags: 
  - nuxtjs
  - web development
  - 北海道
---
---
title: Displaying content
description: 'You can use `<nuxt-content>` component directly in your template to display your Markdown.'
position: 5
category: Getting started
---

<alert type="info">This section is only for Markdown files.</alert>

## Component

You can use `<nuxt-content>` component directly in your template to display the page body:

```vue
<template>
  <article>
    <h1>{{ page.title }}</h1>
    <nuxt-content :document="page" />
  </article>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const page = await $content('home').fetch()

    return {
      page
    }
  }
}
</script>
```



**Props:**
- document:
  - Type: `Object`
  - `required`

Learn more about what you can write in your markdown file in the [writing content](/writing#markdown) section.

## Style

Depending on what you're using to design your app, you may need to write some style to properly display the markdown.

`<nuxt-content>` component will automatically add a `.nuxt-content` class, you can use it to customize your styles:

```css
.nuxt-content h1 {
  /* my custom h1 style */
}
```

> You can find an example in the theme-docs [main.css](https://github.com/nuxt/content/blob/master/packages/theme-docs/src/assets/css/main.css) file. You can also take a look at the [TailwindCSS Typography plugin](https://tailwindcss.com/docs/typography-plugin) to style your markdown content like we do in the `@nuxt/content-theme-docs`.

## Live Editing

> Available in version **>= v1.4.0**

**In development**, you can edit your content by **double-clicking** on the `<nuxt-content>` component. A textarea will allow you to edit the content of the current file and will save it on the file-system.

<video poster="https://res.cloudinary.com/nuxt/video/upload/v1588091670/nuxt-content-ui_otfj5y.jpg" playsinline controls>
  <source src="https://res.cloudinary.com/nuxt/video/upload/v1588091670/nuxt-content-ui_otfj5y.webm" type="video/webm" />
  <source src="https://res.cloudinary.com/nuxt/video/upload/v1592314331/nuxt-content-ui_otfj5y.mp4" type="video/mp4" />
  <source src="https://res.cloudinary.com/nuxt/video/upload/v1588091670/nuxt-content-ui_otfj5y.ogv" type="video/ogg" />
</video>

<cld-image
  public-id="nuxt_demo/DSC00856"
  class="my-3"
  crop="fill"
  responsive
  quality="auto"
  fetch-format="auto" />