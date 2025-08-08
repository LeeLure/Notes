
https://nuxt.com/docs/api/composables/use-fetch

https://nuxt.com/docs/examples/advanced/use-custom-fetch-composable

https://nuxt.com/docs/guide/recipes/custom-usefetch

```
composables/request.js

/**
 * Fetch data from an API endpoint with an SSR-friendly composable. See https://nuxt.com/docs/api/composables/use-fetch
 * 
 * @description 封装请求
 * @param {String} request — The URL to fetch
 * @param {Object} option   extends $fetch options and useAsyncData options
 * @returns {Promise}
 *  https://nuxt.com/docs/api/composables/use-fetch
 *  https://nuxt.com/docs/examples/advanced/use-custom-fetch-composable
 *  https://nuxt.com/docs/guide/recipes/custom-usefetch
 */
const request = (url, option) => {

  const config = useRuntimeConfig()

  return useFetch(url, {
    baseURL: config.public.apiUrl,
    onRequest({ options }) {
      let token = null
      // 只在客户端获取 token
      if (import.meta.client) token = localStorage.getItem('token')

      options.headers = {
        Authorization: `Bearer ${token}`,
        ...options.headers
      }
    },
    ...option
  })
}

export default request
```