1、安装

pnpm install pinia @pinia/nuxt

https://nuxt.com/docs/getting-started/state-management

https://pinia.vuejs.org/ssr/nuxt.html#Installation

```
// nuxt.config.js
export default defineNuxtConfig({
  // ... other options
  modules: [
    // ...
    '@pinia/nuxt',
  ],
})
```

持久化插件

pnpm i -D @pinia-plugin-persistedstate/nuxt

```
export default defineNuxtConfig({
  build:{
    transpile:['pinia-plugin-persistedstate']
  },
  modules: [
    '@pinia/nuxt',
    '@pinia-plugin-persistedstate/nuxt',
  ],
})
```

建议配置项设置为： 

``` 
{persist: true}

```

https://prazdevs.github.io/pinia-plugin-persistedstate/zh/frameworks/nuxt-3.html

