# webpack是一个编译处理的过程，有以下几个步骤
 1、初始化参数：从配置文件和 Shell语句中读取与合并参数，得出最终的参数 
 2、开始编译：用上一步得到的参数初始化 Compiler 对象，加载所有配置的插件，执行对象的 run 方法开始执行编译 
 3、确定入口：根据配置中的 entry 找出所有的入口文件 
 4、编译模块：从入口文件出发，调用所有配置的Loader 对模块进行翻译，再找出该模块依赖的模块，再递归本步骤直到所有入口依赖的文件都经过了本步骤的处理 
 5、完成模块编译：在经过第4步使上oader 翻译完所有模块后，得到了每个模块被翻译后的最終内寮以及它们之间的依赖关系 
 6、输出资源：根据入口和模块之间的依赖关系，组装成一个个包含多个模块的 Chunk，再把每个 Chunk 转换成一个单独的文件加入到输出列表，这步是可以修改输出内容的最后机会 
 7、输出完成：在确定好输出内容后，根据配置确定输出的路径和文件名，把文件内容写入到文件系统，在以上过程中，webpack 会在特定的时间点广播出特定的事件，插件在监听到感兴趣的事件后会执行特定的逻辑，并且插件可以调用 Webpack 提供的 API 改变 Webpack 的运行结果

# webpack性能优化
1.webpack是一个编译处理的过程
减小查找的范围，用一些常用的配置比如alias和extensions配置减小范围
2.减少需要解析的文件
使用noprase参数进行配置，告诉webpack这部分时不需要进行解析
3.避免去重复地编译第三方库
比如像echarts和elementui等库，可以单独打包到一个文件中，这样就可以提高webpack的一个打包速度
4.再webpack对代码进行压缩打包的时候进行压缩他会一个个进行压缩，这样我们可以通过多进程来进行压缩。

# Webpack的loader和plugin
1. loader是一个加载器，webpack将一切文件视为模块，如果想将非js（webpack原生只支持js）加载解析打包的话就需要用到loader
2. plugin扩展webpack的功能，再webpack运行的生命周期中，通过广播出更多的事件，插件就去监听这些事件，在合适的时候通过webpack提供的api来改变输出的结果。
3. loader在modle.rules配置，作为模块的解析规则，是一个对象数组。
4. 什么对象的文件使用什么样的loader
5. 插件单独配置，本质也是数组，通过构造函数传递
## webpack中Loader 和Plugin 的不同？（必会）
### 常用的loader以及相应的作用如下： 
1、file-loader：把文件输出到一个文件夹中，在代码中通过相对 URL 去引用输出的文件 
2、url-loader：和 file-loader 类似，但是能在文件很小的情况下以base64 的方式把文件内容注入到代码中去
3、source-map-loader：加载额外的 Source Map 文件以方便断点调试 
4、image-loader：加载并且压缩图片文件 
5、babel-loader：把 ES6 转换成 ES5 
6、css-loader：加载 CSS，支持模块化、压缩、文件导入等特 性 
7、style-loader：把PSS.代确法入到paygScript 中，通过DOM 操作去加载 CSS his loaderand our plugtn 
8、eslint-loader：通过 ESLint 检查 JavaScript 代码
### 常用的plugin以及相应的作用如下：
1、Webpack-dashboard：可以更友好的展示相关打包信息
2、Webpack-merge： 提取公共配置，减少重复配置代码 
3、speed-measure-Webpack-plugin：简称SMP，分析出 Webpack 打包过程中 Loader 和Plugin 的耗时，有助于找到构建过程中的性能瓶颈 
4、size-plugin：监控资源体积变化，尽早发现问题  
5、 HotModuleReplacementPlugin :模块热替换