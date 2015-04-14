##EHR BLL-API Design Documentation##
>*该文档是EHR业务逻辑层的API设计说明文档，欢迎大家阅读、讨论、修改。*

---
### [卫生机构领导] ###

- 方法名称：List\<String\> getChildOrgName()
- 方法描述：获取子机构名称

**输入**

| 请求参数 | 必选 | 数据类型 | 参数说明 |
|:---:|:---:|:---:|:---:|
|orgCode|true|String|该机构代码为父机构代码|
	
**输出**

| 返回值 | 数据类型 | 参数说明 |
|:---:|:---:|:---:|
|childOrgNameList|List\<String\>|子机构名称列表|

---



















###资源链接###

- 实用教程：[Markdown 语法说明](http://www.appinn.com/markdown/index.html#list)
- 参考案例：[微博API](http://open.weibo.com/wiki/%E5%BE%AE%E5%8D%9AAPI)

---

###常用格式快捷键###

- **Bold** (`Ctrl+B`) and *Italic* (`Ctrl+I`)
- Quotes (`Ctrl+Q`)
- Code blocks (`Ctrl+K`)
- Headings 1, 2, 3 (`Ctrl+1`, `Ctrl+2`, `Ctrl+3`)
- Lists (`Ctrl+U` and `Ctrl+Shift+O`)

---
