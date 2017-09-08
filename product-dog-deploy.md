# 新产品狗切换配置说明

## 更新步骤
1. 备份相关文件，包括：
    web.config
    bin\license.xml
    以及站点中会被更新包文件覆盖的文件
2. 安装新狗驱动包。插狗服务器和产品站点所在的服务器都需要安装。

3. 将更新包中的文件覆盖到站点目录。
4. 将新的License文件（License2.xml）和狗文件（licenseDog.xml）放入站点\bin目录。
5. 调整web.config配置。参见后续说明。
6. 调整注册表配置。参见后续说明。
7. 浏览器中访问站点，测试部署是否成功。

## 修改Web.config配置
1. 配置狗类型：
在AppSettings节点下搜索原有的AppSettings下的SoftDogType节点，将其替换为以下内容：
```xml
<add key="SoftDogType" value="ProductDog" />
```

2. 增加License版本节点
在```AppSettings```节点下增加下列节点：（注意value中的值需要手工调整）
```xml
<add key="ERP-License-ProductVersion" value="3.0.3"/>
```
> 节点的Value值含义说明： 
> 这个值用于ERP底层代码从合并的License文件(license2.xml）中找到当前站点使用的License。

配置方法(重要）：
1. 用记事本或其他文本编辑器（推荐Notepad++）打开license2.xml文件
2. 搜索：productVersion，会找到多个匹配项。这里每一个匹配项所在的license节点是一个完整的License。
3. 从上一步找到的节点中选取当前站点使用的License节点。
4. 将当前站点使用的License节点的```productVersion```的值填入web.config中的```ERP-License-ProductVersion```节点的value值中。

## 注册表配置调整说明
由于更换新的License文件，注册表项名称也需要跟随License调整。
调整方法如下：
1. 用记事本或其他文本编辑器（推荐Notepad++）打开license2.xml文件
2. 搜索：```productVersion```，会找到多个匹配项。这里每一个匹配项所在的license节点是一个完整的License。
3. 从上一步找到的节点中选取当前站点使用的License节点。
4. 在上一步找到的License节点下找到节点：
```xml
<dbconn appname="Default" regname="ERP3.0.3" />
```
注册表项需要更改为regname属性的值。在上述示例中，应为ERP3.0.3。

> 安全起见，更改注册表项前，可以先导出注册表项。（注册表编辑器中的文件->导出功能）

## 其他配置调整
重构ERP 1.0 SP1/SP2需调整```App_Data\AuthorizedWhitelist.config ```

在```Whitelist```节点内增加以下内容：
```xml
<!--加密狗相关-->
<Url>/DogOffline.ashx</Url>
<Url>/DogInfo.ashx</Url>
```
