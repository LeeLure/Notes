
## Deprecation Warning: The legacy JS API is deprecated and will be removed in Dart Sass 2.0.0.
>[!warning]+  Deprecation Warning: The legacy JS API is deprecated and will be removed in Dart Sass 2.0.0.
>![[ErrorResolution/powershell waning/assets/Sass-1.png|1003x85]]

### 解决方案
- #### 按照官网方案静音警告
	-  ##### [Sass: Breaking Change: Legacy JS API](https://sass-lang.com/documentation/breaking-changes/legacy-js-api)entation/breaking-changes/legacy-js-api/)ntation/breaking-changes/legacy-js-api/)
	- ![[ErrorResolution/powershell waning/assets/Sass.png]]
```js
 # vite.config.js 
css: {
    preprocessorOptions: {
      scss: {
        // 1.更新Vite配置文件，设置api为"modern"或"modern-compiler"，Vite将使用现代的Sass API，而不是即将被废弃的旧版API。
        // api: "modern-compiler", // Element Plus 中的解决办法

        // 2.暂时静默警告
        silenceDeprecations: ['legacy-js-api']
      }
    }
  }
```

- #### 升级到现代API  
  - 使用官方推荐的`@sass`模块替代旧版`sass`  
  - 参考迁移指南：[Migrating from node-sass](https://sass-lang.com/documentation/breaking-changes/node-sass)  
  - 示例安装命令：`pnpm install sass@latest -D`

## Deprecation Warning: Sass @import rules are deprecated and will be removed in Dart Sass 3.0.0.
>[!warning]+  Deprecation Warning: Sass @import rules are deprecated and will be removed in Dart Sass 3.0.0.

### 解决方案
- **使用`@use`规则替代`@import`**：Sass 引入了`@use`和`@forward`规则来替代`@import`，以提高样式表的可维护性和减少错误。您可以将现有的`@import`规则替换为`@use`规则。例如，如果您的代码中有`@import "variables.scss";`，则可以替换为`@use "variables.scss";`。

- **使用Sass migrator自动迁移**：Sass提供了一个迁移工具[sass-migrator](https://zhida.zhihu.com/search?content_id=250595573&content_type=Article&match_order=1&q=sass-migrator&zhida_source=entity)，可以帮助您自动将`@import`迁移到模块系统。您可以按照以下步骤使用sass-migrator：`$ npm install -g sass-migrator $ sass-migrator module --migrate-deps your-entrypoint.scss` 这将帮助您自动更新样式表以使用模块系统。

- **控制弃用警告**：如果您希望在迁移过程中暂时静默`@import`的弃用警告，可以使用`--silence-deprecation`命令行选项。例如： `--silence-deprecation=import`  这将暂时隐藏弃用警告，让您有时间完成迁移。

- **更新配置文件**：如果您使用的是Vite或类似构建工具，您可能需要更新配置文件以适应新的模块系统。例如，在`vite.config.js`中，您可以添加或更新以下配置： `exportdefaultdefineConfig({ css:{ preprocessorOptions:{ scss:{ api:'modern-compiler' } } } });`  这将确保您的构建工具使用现代的Sass API。

