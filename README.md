﻿# 新加密狗开放文档索引

## 部署相关文档

Q：作为开发、测试人员，如何将自己的开发环境、测试环境切换到新狗？

参见：[产品狗切换配置说明](product-dog-deploy.md)

Q：作为一线实施顾问，如何将自己的测试环境切换到新狗？

参见：[自用狗切换配置说明](personal-dog-deploy.md)

Q：作为客户，如何将环境切换到新狗？
产品狗配置切换说明：http://note.youdao.com/noteshare?id=09e9911e6ec4faa495a77427932d83c3&sub=DDF5F3F8DA9F4C8D8F910884A3D562B9
新云狗配置切换说明：http://note.youdao.com/noteshare?id=426d05403bcbb3b02e958175d6f6bf3d&sub=6C0A9312A5824A8AA49A2951C2200E75

Q：客户的测试环境如何部署？
测试狗配置切换说明：http://note.youdao.com/noteshare?id=777a1e33b497a8d1b96962c14ffa4fec&sub=A394436A5A7C4DEC953CB37C413D960D

## 新狗方案类问题
Q：切换到新狗对产品有哪些要求、限制？
1. 重构ERP V1.0 SP3及以上版本，核心ERP3.5.3（即将发布）直接支持新狗。
2. 核心ERP2.5.2及以上版本，可以通过修改MAP平台代码，移植新狗校验代码包支持新狗。核心ERP移植相关事项请联系：吕奔之。
3. 核心ERP2.5.1及以下版本，不支持新狗方案。

Q：切换到新狗后，有哪些好处？
1. 部署方式灵活：新产品狗支持多套ERP共用一只狗，通过网络访问。通常将硬件狗插在数据库服务器上。同时新狗还支持高可用性的双狗负债均衡的部署方式。
2. 授权文件无需写狗：增购子系统、增值模块、用户数，无需重新写狗，减少来回寄送成本。
3. 授权文件自动更新：接上一条，如果ERP服务器可以连接公网，甚至无需手工更新授权文件，业财确认后，新的授权文件在指定时间自动更新到ERP环境。
4. 使用了新的License文件：客户的多套环境（ERP站点）共用一个license文件（license2.xml），不容易出现文件弄混的情况。
5. 等等等等。如果想了解更多特性，请联系王渊（武汉产品）索取新狗方案的资料。

## 附录
1. [新狗部署故障集](questions/error-codes.md)


