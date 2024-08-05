## Tabs标签页学习
何时使用：提供平级区域将大块内容件事收纳和展示，保持界面的整洁。
1. 卡片式的页签，提供可关闭的样式，常用语容器顶部
2. 可用于容器顶部，可用于容器内部
3. radio.button可用作次级页签使用
#### 一些属性
`<Taps></Taps>`
在子元素中添加disabled :true禁用某一个
items，放置tab选项
centered， 居中展示
icon，确定
indicator，确定指示条的宽度和对齐方向
tapPosition，确定tab展示的方向
tabBarExtraContent，额外附加操作，或标签



# modal对话框学习
会弹出一个对话框，对话框的内容是可以写死的，也可以是一个组件



# Typography排版
## 何时使用
- 当需要展示标题、段落、列表内容时使用，如文章/博客/日志的文本样式。
- 当需要一列基于文本的基础操作时，如拷贝/省略/可编辑。
## 使用方法
```
import {Typography} from 'antd'
const {Text} = Typograpgy
<Text ellipsis = {{ tooltip: fullStr }}></Text>
```

## 类型分类，4种
***const { Title, Paragraph, Text, Link } = Typography***
主要从Typography中分为这四种标签
* 标题
* 段落
* 语句
* 链接

可以根据需要在后面添加属性有，可复制，可编辑，
```
<Paragraph
      copyable={{
        text: async () =>
          new Promise((resolve) => {
            setTimeout(() => {
              resolve('Request text');
            }, 500);
          }),
      }}
    >
```
在可以复制中，可以通过异步操作返回text的值，用简单的复制字段请求远端数据。