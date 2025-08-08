
1、静态标题

https://nuxt.com/docs/api/composables/use-seo-meta

```
useSeoMeta({
  title: 'My Amazing Site',
  ogTitle: 'My Amazing Site',
  description: 'This is my amazing site, let me tell you all about it.',
  ogDescription: 'This is my amazing site, let me tell you all about it.',
  ogImage: 'https://example.com/image.png',
  twitterCard: 'summary_large_image',
})



const title = ref('My title')
useSeoMeta({
  title,
  description: () => `description: ${title.value}`
})

```

2、动态标题

```
const siteTitle = ref('Site Title')
useHead({
  // as a string,
  // where `%s` is replaced with the title
  titleTemplate: '%s - Site Title',
  
  titleTemplate: `%s - ${siteTitle.value}`,
  
  // or as a function
  titleTemplate: (productCategory) => {
    return productCategory
      ? `${productCategory} - Site Title`
      : 'Site Title'
  }
})
```

https://nuxt.com/docs/getting-started/seo-meta
