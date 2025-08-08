
https://nuxt.com/docs/guide/directory-structure/error

1、服务端创建错误

https://nuxt.com/docs/api/utils/create-error

```
throw createError({ statusCode: 404, statusMessage: 'Page Not Found' })

// 清除错误
clearError(options?: { redirect?: string })
```

2、客户端创建错误

```
showError({statusCode: 404,statusMessage: "Page Not Found"})
```

