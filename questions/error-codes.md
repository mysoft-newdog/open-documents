
# 新加密狗错误提示清单与排查建议

## License相关错误
提示内容 | 排查建议
--------|--------
License验证失败（L001）：License2.xml文件不存在 | bin目录下是否存在license2.xml文件
License验证失败（L002）：License文件中不存在data节点 | license2文件中不存在data节点，需重新写狗获取license2文件
License验证失败（L003）：License文件中不存在signature节点 | license2文件中不存在signature节点，需重新写狗获取license2文件
License验证失败（L004）：读取授权文件失败！异常信息：XXX | 读取license文件失败： 1、license文件XML结构异常导致异常，重新写狗并更新 2、当前license文件为正确XML结构，非正确的license结构
 License验证失败（L005）：非法的授权文件！RSA签名不一致！ | 系统启动时校验license签名错误 1、license文件写狗签名失败，需重新写狗 2、license文件中license节点值被人为修改，撤回修改内容或无法撤回则需重新写狗
 License验证失败（L007）：License文件中的dbconn配置不正确，没有找到regname属性。 | license文件中dbconn节点中没有regname属性
 License验证失败（L007）：Web.config文件中找不到ERP-License-ProductVersion的配置。 | web.config文件中appSettings没有配置```<add key="ERP-License-ProductVersion" value=""/>```节点
 License验证失败（L008）：License文件中的dbconn配置不正确，没有找到Default的连接。 | license文件中dbconn节点中没有Default属性： 1、license文件写狗时就不存在，需重新写狗 2、节点值被人为修改，撤回修改内容或无法撤回则需重新写狗
 License验证失败（L008）：License文件找不到版本（{productVersion}）对应的License节点。 | license文件中licenses节点中不存在web.config配置的productVersion版本。请重新配置Web.config中的```<add key="ERP-License-ProductVersion" value=""/>```节点内容。
 