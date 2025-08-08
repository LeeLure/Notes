1、基本使用

https://nuxt.com/docs/api/components/nuxt-layout

```
// ~/layouts/defalut.vue

<template>
  <header>
    <ElButton type="primary"><NuxtLink to="/">index</NuxtLink></ElButton>
    <ElButton type="warning"><NuxtLink to="/login">Login</NuxtLink></ElButton>
    <ElButton type="success"><NuxtLink to="/register">register</NuxtLink></ElButton>
  </header>
  <main>
    <slot />
  </main>
  <footer>
    <ElButton type="primary"><NuxtLink to="/">index</NuxtLink></ElButton>
    <ElButton type="warning"><NuxtLink to="/login">Login</NuxtLink></ElButton>
    <ElButton type="success"><NuxtLink to="/register">register</NuxtLink></ElButton>
  </footer>
</template>

```

```
// app.vue

<NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
  
 ```
  
  
  如需要再某页面不使用 layouts 或使用另一个，可使用 `definePageMeta` 
  
  ```
 definePageMeta({
 	layout: 'default'
})
```

  https://nuxt.com/docs/api/utils/define-page-meta