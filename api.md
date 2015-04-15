##EHR BLL-API Design Documentation(1)##
>*该文档是EHR业务逻辑层的API设计文档，欢迎大家阅读、讨论、修改。*

---

### [卫生机构领导] ###

- 方法序号：wsjgld_01
- 方法名称：List\<string\> getChildOrgName()
- 方法描述：获取子机构名称

**输入**

| 请求参数 | 必选 | 数据类型 | 参数说明 |
|:---:|:---:|:---:|:---:|
|orgCode|true|string|该机构代码为父机构代码|
	
**输出**

| 返回值 | 数据类型 | 参数说明 |
|:---:|:---:|:---:|
|childOrgNameList|List\<string\>|子机构名称列表|

-------------------------------------------------------------------------------

- 方法序号：wsjgld_02
- 方法名称：Map\<string,T\> getArchiveStatistics()
- 方法描述：获取档案统计

**输入**

| 请求参数 | 必选 | 数据类型 | 参数说明 |
|:---:|:---:|:---:|:---:|
|orgCode|true|string|要做档案统计的机构代码|
	
**输出**

| 返回值 | 数据类型 | 参数说明 |
|:---:|:---:|:---:|
|archiveStatisticsInfo|Map\<string,T\>|**key->value:**</br>**orgName->string v1**，orgCode对应的机构名称</br> **population->int v2**，总人数</br> **filedCount->int v3**，建档数</br> **unfiledCount->int v4**，未建档数</br> **filedRate->float v5**，建档率|

**备注**</br>“上一级单位”是否保留，“应建档”是否保留，若保留，与“总人数”的关系。

-------------------------------------------------------------------------------

- 方法序号：wsjgld_03
- 方法名称：Map\<string,T\> getPsnList()
- 方法描述：获取人员列表

**输入**

| 请求参数 | 必选 | 数据类型 | 参数说明 |
|:---:|:---:|:---:|:---:|
|orgCode|true|string||
	
**输出**

| 返回值 | 数据类型 | 参数说明 |
|:---:|:---:|:---:|
|psnList|Map\<string,T\>|**key->value:**</br>**psnID->string v1**，人员ID号，默认为身份证号</br> **psnName->string v2**，人员姓名</br> **sex->dict v3**，性别</br> **birth->date v4**，出生日期</br> **orgName->string v5**，所属机构名称</br> **archiveDate->date v6**，建档日期|

**备注**</br>没有身份证号的人员其psnID由系统统一编号；</br>dict类型需要自定义。

-------------------------------------------------------------------------------

- 方法序号：wsjgld_04
- 方法名称：\<T extends CastleModel\> Map\<string,T\> getArchive()
- 方法描述：调阅个人档案

**输入**

| 请求参数 | 必选 | 数据类型 | 参数说明 |
|:---:|:---:|:---:|:---:|
|psnID|true|string|档案所属的人员ID号|
|access_token|false|string|访问令牌，采用OAuth方式必填参数，授权后获得|
	
**输出**

| 返回值 | 数据类型 | 参数说明 |
|:---:|:---:|:---:|
|archiveContent|Map\<string,T\>|**key->value:**</br>**psnBasicInfo->Map\<string,T\> v1**，个人基本信息</br> **outpatient->outpModel v2**，门诊模块</br>  **inpatient->inpMoel v3**，住院模块</br> **physicalExam->examModel v4**，体检模块|

**备注**</br>这个接口函数还没有设计好，需要讨论商定。

-------------------------------------------------------------------------------











###资源链接###

- 实用教程：[Markdown 语法说明](http://www.appinn.com/markdown/index.html#list)
- 参考案例：[微博API](http://open.weibo.com/wiki/%E5%BE%AE%E5%8D%9AAPI)

-------------------------------------------------------------------------------

###常用格式快捷键###

- **Bold** (`Ctrl+B`) and *Italic* (`Ctrl+I`)
- Quotes (`Ctrl+Q`)
- Code blocks (`Ctrl+K`)
- Headings 1, 2, 3 (`Ctrl+1`, `Ctrl+2`, `Ctrl+3`)
- Lists (`Ctrl+U` and `Ctrl+Shift+O`)

-------------------------------------------------------------------------------
