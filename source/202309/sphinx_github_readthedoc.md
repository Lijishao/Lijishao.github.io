# 个人博客部署流程

> 基于Github/Sphinx/ReadTheDoc

## 简介

简单介绍一下，各个平台/工具的作用

* Sphinx
  * 网页生成工具，可以将自己写的`md`或`rst`等文本格式的内容转换为`html`格式的内容，以供访问

* Github
  * 代码托管平台，在本文中，主要起到托管、管理文档的作用，可以将带有Sphinx环境的doc上传到github进行托管

* ReadTheDoc
  * 文档托管平台，虽说Github同有托管功能，但仅支持静态html的访问，若想获得最佳体验，只能另寻他法

## Sphinx

1. 安装
  * 命令`pip install sphinx`,安装失败可百度
2. 部署
  * 命令`sphinx=quickstart`,可快速搭建一个简单的doc环境
  * `独立的源文件和构建目录`,键入`y`;`项目语种`键入`zh_CN`
  * 其余按个人信息及需求进行填写
3. 执行
  * 执行`make html`命令，即可快速生成html网页文件(build/html/)
  * 可打开`index.html`简单预览一下
4. 其他
  * 更改主题
    * 执行`pip install sphinx_rtd_theme`
    * 修改`conf.py`文件中的html_theme字段为`html_theme='sphinx_rtd_theme'`
  * 增加扩展工具
    * 默认只支持`rst`格式的编译，若需支持`md`格式，则需安装扩展
    * 执行`pip install recommonmark`
    * 修改`conf.py`文件中的extensions字段为`extensions=['recommonmark']`
  * 收尾
   * 对于ReadTheDoc平台会自动帮我们进行文档编译，可以省很多工作
   * 但需要提供给平台一些信息，当平台知道我们需要那些额外的扩展项，让它自行安装
   * 新建`requirements.txt`, 并将所需的额外项全部列入,例
     ```
      recommonmark==0.7.1
      sphinx_rtd_theme==1.1.1
     ```

