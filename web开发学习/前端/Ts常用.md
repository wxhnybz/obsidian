## export和export declare区别
都用于到处模块
* export用于到处模块中的变量函数吗泪，接口，使他们呢可以在其他模块通过import被导入。实质是在导出一个具体的的实现或声明
* export declare 组合通常在声明文件.d.ts中生命一个类型而不实现。declare用于高速ts，改名成代表的实体已经存在，只是进行类型定义，额不是创建一个新的实现。
* 