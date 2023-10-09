
## 约定大于配置

软件设计范式，减少开发人员配置工作(做决定)量.专注业务开发

1) 开发人员仅配置和约定不一致部分
2) 未规定配置地方，采用默认配置

传统ssm框架:
web.xml,dispacherservlet(start-web)
,jar包依赖通过(boot-starter 控制版本依赖)
内置tomcat
第三方依赖
applicaton.yml
****
## 自动配置流程
@SpringbootApplication -> @EnableAutoConfiguration -> @import()

***

## springboot启动流程

environmentPrepared 配置applicaion.yml(加载流程)

environmentPrepared 中的preparedEvent事件，会触发applicationListeners中的
ConfigFileApplicationListener进行配置加载

invokeBeanFactoryPostProcessors会将所有继承beanFactoryPostProcessor接口进行执行

优先处理ConfigurationClassPostProcessor，将代码中所有注解注册进springfactory中（并未实例化）

## 需要继续深入点:

BeanFactoryPostProcessor

getBeanDefinitionRegistry

this.AnnotatedBeanDefinitionReader.register(source);

BeanDefinitionLoader

ConfigurationClassPostProcessor
***

application和bootstrap.yml

自动装配失败,如何进行提示

如何优雅停机