#classLoader #idea

## 概念及idea

加载类:将class文件加载入内存

jvm通过调用 _ClassLoader_ 的 _loadClass()_ 方法进行加载(双亲委派模式)

由设计Class插件想法而来:外部引入实现接口了的class文件,服务进行动态调用

## content



