# 生成gitbook记录

> 对使用gitbook+github.pages生成blog网站的过进行记录。  
> 生成的页支持：GFM、mermaid、plantUML。

## plantUML支持
- 在*.md文件中使用GFM+plantUML描述。

```reStructuredText
​```plantuml
@startuml
  a-->b: hello
  b-->c: how are you
@enduml
​```
```

显示效果如下：  
```plantuml
@startuml
  a-->b: hello
  b-->c: how are you
@enduml
```
- 在生成根目录中放入plantuml.jar，这个文件可以从[plantuml](http://plantuml.com/zh/download)下载。
- 在.travis.yml配置中增加plantUML、graphviz等组件，这些组件可以把markdown源文件中的plantUML转换成图片。安装时需要安装中文字体，否则中文字乱码。
```shell
  - sudo apt-get install ttf-wqy-microhei
  - sudo apt-get install default-jre
  - sudo apt-get install graphviz
  - export GRAPHVIZ_DOT=/usr/bin/dot
  - java -jar plantuml.jar -testdot
  - npm install -g gitbook-plugin-uml
```
- 在book.json中增加配置。具体配置说明见[gitbook-plugin-uml](https://www.npmjs.com/package/gitbook-plugin-uml)。
```json
{
  "plugins": ["uml"]
}
```
```json
"pluginsConfig": {
  "uml": {
    "format": "png",
    "nailgun": false
  }
}
```
- 排查错误。

> 查看Travis CI日志，如果生成失败，在“java -jar plantuml.jar -testdot”的输出中可以看出来，这个脚本是一个测试脚本。

## Travis CI
...
