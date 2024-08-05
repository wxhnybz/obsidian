# 为什么选择 webpack

想要理解为什么要使用 webpack，我们先回顾下历史，在打包工具出现之前，我们是如何在 web 中使用 JavaScript 的。

在浏览器中运行 JavaScript 有两种方法。
* 第一种方式，引用一些脚本来存放每个功能；此解决方案很难扩展，因为加载太多脚本会导致网络瓶颈。
* 第二种方式，使用一个包含所有项目代码的大型 `.js` 文件，但是这会导致作用域、文件大小、可读性和可维护性方面的问题。


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


## vite和webpack区别
⭐构建速度⭐
Webpack: Webpack的构建速度相对较慢，尤其在大型项目中，因为它需要分析整个依赖图，进行多次文件扫描和转译。
Vite: Vite以开发模式下的极速构建著称。它利用ES模块的特性，只构建正在编辑的文件，而不是整个项目。这使得它在开发环境下几乎是即时的。
⭐开发模式⭐
Webpack: Webpack通常使用热模块替换（HMR）来实现快速开发模式，但配置相对复杂。
Vite: Vite的开发模式非常轻量且快速，支持HMR，但无需额外配置，因为它默认支持。
⭐配置复杂度⭐
Webpack: Webpack的配置相对复杂，特别是在处理不同类型的资源和加载器时。
Vite: Vite鼓励零配置，使得项目起步非常简单，但同时也支持自定义配置，使其适用于复杂项目。
⭐插件生态⭐
Webpack: Webpack拥有庞大的插件生态系统，适用于各种不同的需求。
Vite: Vite也有相当数量的插件，但相对较小，因为它的开发模式和构建方式减少了对一些传统插件的需求。
⭐编译方式⭐
Webpack: Webpack使用了多种加载器和插件来处理不同类型的资源，如JavaScript、CSS、图片等。
Vite: Vite利用ES模块原生支持，使用原生浏览器导入来处理模块，不需要大规模的编译和打包。
⭐应用场景⭐
Webpack: 适用于复杂的大型项目，特别是需要大量自定义配置和复杂构建管道的项目。
Vite: 更适用于小到中型项目，或者需要快速开发原型和小型应用的场景。
⭐打包原理⭐
Webpack: Webpack的打包原理是将所有资源打包成一个或多个bundle文件，通常是一个JavaScript文件。
Vite: Vite的打包原理是保持开发时的模块化结构，使用浏览器原生的导入机制，在生产环境中进行代码分割和优化