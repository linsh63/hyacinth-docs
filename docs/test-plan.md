# 软件测试计划书：Hyacinth 应用测试

> [!NOTE]
> 在线版本文档部分信息已脱敏

## 1. 标识符

* 计划编号： Hyacinth-Web，EasyTier-GUI

* 计划名称： Hyacinth 应用 Web 界面功能及回归测试计划 , EasyTier 作为 GUI 页面+虚拟网络连接测试计划



## 2. 简介

* 测试对象：

  Hyacinth 应用的 Web 界面，一款集成了 Go 后端和 Vue 前端开发的商业化组网软件。

  EasyTier提供了用户具体连接虚拟网络的方式，方便用户实时更改虚拟网络连接的高级设置。

*   测试目标：

    *   验证 Hyacinth Web 界面的用户登录和注册功能的正确性和稳定性。
    *   验证 Hyacinth Web 界面的 Dashboard（网络管理主界面）核心功能的正确性和易用性。
    *   通过回归测试验证在前两轮测试中发现并修复的缺陷已得到解决，且未引入新的关键缺陷。
    *   确保 Web 界面的关键路径功能符合预期。
    *   验证Windows端和手机端通过EasyTier GUI连接虚拟网络正确性和稳定性。
    *   验证不同操作（停用虚拟网络，流量用完等）对虚拟网络连接以及ip分配的稳定性。
    *   通过回归测试验证在前两轮测试中发现并修复的缺陷已得到解决，且未引入新的关键缺陷。
    *   确保EasyTier核心功能符合预期。

*   测试策略：

    *   采用分阶段的功能测试和回归测试策略。
    *   主要进行黑盒测试，关注用户界面的交互和功能实现。
    *   测试将覆盖主要的用户场景和关键功能点。

*   测试过程：

    前端Hyacinth：

    *   第一轮测试： 重点测试登录、注册界面。
    *   缺陷修复阶段1： 负责开发的同学修复第一轮测试中发现的缺陷。
    *   第二轮测试： 重点测试 Dashboard 界面。
    *   缺陷修复阶段2： 负责开发的同学修复第二轮测试中发现的缺陷。
    *   第三轮测试（总测试/回归测试）： 对登录注册、Dashboard 均进行测试，重点验证已修复的缺陷及可能受影响的区域，确保整体稳定性。

    GUI EasyTier

    *   第一轮测试： 重点测试虚拟网络添加，删除功能以及主机能否正常连接虚拟网络并且ping ip。
    *   缺陷修复阶段1： 负责开发的同学修复第一轮测试中发现的缺陷。
    *   第二轮测试： 重点测试用户操作对虚拟网络连接的影响。
    *   缺陷修复阶段2： 负责开发的同学修复第二轮测试中发现的缺陷。
    *   第三轮测试（总测试/回归测试）： 对Windows和手机端的虚拟网络连接均进行测试，重点验证已修复的缺陷及可能受影响的区域，确保整体稳定性。

*   测试进程： 详见 "13. 进度安排"。



## 3. 测试项

Hyacinth Web 应用程序：
*   用户认证模块（登录、注册）
*   Dashboard 模块（仪表盘、虚拟网络管理、商城、用户个人中心）

EasyTier GUI 应用程序

*   GUI模块（添加、删除虚拟网络）
*   虚拟网络连接模块（仪表盘、虚拟网络管理、商城、Windows和手机端）



## 4. 待测软件特征

Hyacinth 应用 Web 界面的以下页面及其核心功能：

*   产品介绍页
    *   页面正确加载与内容显示。
    *   验证导航至“登录页”按钮的功能和跳转正确性。
    *   验证导航至“注册页”按钮的功能和跳转正确性。
*   注册页 (Registration Page)
    *   使用有效的、唯一的用户名、邮箱和符合要求的密码成功注册。
    *   对无效/缺失输入（用户名、邮箱、密码）的友好提示和处理。
    *   对已存在的用户名或邮箱进行注册时的处理和提示。
    *   密码策略的符合性（如最小长度、字符类型组合等）。
    *   注册成功后的用户反馈及自动跳转（至登录页或 Dashboard，根据设计）。
*   登录页 (Login Page)
    *   使用有效的“用户名”和密码成功登录。
    *   使用有效的“邮箱”和密码成功登录。
    *   使用无效的用户名/邮箱或错误密码登录时的处理和提示。
    *   登录成功后正确跳转至 Dashboard 页面。
*   Dashboard 页面及其模块
    *   Dashboard 整体
        *   登录后 Dashboard 页面的正确加载与显示。
        *   页面布局、导航栏、各模块入口的正确显示与可访问性。
        *   登出功能的正确性及登出后的页面跳转。
    *   仪表盘模块
        *   图表的正确显示
        *   统计数据的正确显示
    *   虚拟网络管理模块
        *   创建新虚拟网络的功能（输入、提交、反馈）。
        *   查看已创建的虚拟网络列表。
        *   对单个虚拟网络的操作：
            *   查看网络详情。
            *   修改网络配置（包括网络名称、密码、备注、启用状态及其他网络参数）。
            *   删除虚拟网络。
        *   验证当运行中的虚拟网络数量达到预设的最大限制时，系统能正确阻止用户运行更多网络。
    *   商城模块
        *   模块的正确加载与会员套餐/充值选项的显示。
        *   选择不同会员套餐/充值选项的交互。
        *   充值状态的反馈（如果由本系统直接展示）。
    *   关于模块
        *   模块的正确加载。
        *   软件基本信息（如系统介绍、版本信息等）的正确显示。
    *   个人中心模块
        *   模块的正确加载与当前用户信息的显示。
        *   修改用户名的功能：
            *   输入新用户名。
            *   保存更改及反馈。
            *   对无效/重复用户名的处理。
        *   修改密码的功能：
            *   输入当前密码、新密码、确认新密码。
            *   保存更改及反馈。
            *   对当前密码错误、新密码不一致、新密码不符合策略等情况的处理。

EasyTier 应用 GUI 界面的以下页面及其核心功能：

*   虚拟网络管理测试
    *   添加虚拟网络测试
        *   使用有效的、唯一的网络名、正确的网络密码进行连接
        *   使用全空的网络名、网络密码寻找连接虚拟网络
    *   删除虚拟网络测试
        *   对已经正确连接的虚拟网络进行删除测试
        *   对全空失败连接，失败分配ip地址的虚拟网络进行删除测试
    *   主机名称测试
        *   纯数字主机名测试
        *   纯字母主机名测试
        *   纯汉字主机名测试
        *   数字字母主机名测试
        *   数字字母汉字主机名测试
        *   数字字母汉字特殊字符主机名测试

*   连接虚拟网络测试

    *   DHCP测试
        *   开启DHCP，连接正确的虚拟网络测试
        *   关闭DHCP，手动分配合理ipv4地址测试
        *   关闭DHCP，手动分配已经占用但合法的ipv4地址测试
        *   关闭DHCP，手动分配不合法的ipv4地址测试
    *   网络方式测试
        *   使用手动网络方式，tcp://baka9.vip:60002
        *   使用手动网络方式，udp://baka9.vip:60002
        *   使用公共服务器网络方式
        *   使用独立网络方式

    *   ping ip测试
        *   两个主机都开启防火墙ping ip测试
        *   一个主机开启防火墙一个主机关闭防火墙ping ip测试
        *   两个主机都关闭防火墙ping ip测试

*   连接过程中更改虚拟网络测试

    *   连接虚拟网络后更改最大连接数测试
        *   连接虚拟网络后增大最大连接数测试
        *   连接虚拟网络后减小最大连接数测试
    *   连接虚拟网络后停用虚拟网络测试
    *   连接虚拟网络后停用再启用虚拟网络测试
    *   连接虚拟网络后删除虚拟网络测试
    *   连接虚拟网络后删除再创建相同网络名和网络密码虚拟网络测试
    *   连接虚拟网络后删除再创建相同网络名不同网络密码虚拟网络测试
    *   连接虚拟网络后更改ip段测试
    *   连接虚拟网络后关闭DHCP测试
    *   连接虚拟网络后更改套餐测试
        *   连接虚拟网络后升级套餐测试
        *   连接虚拟网络后降级套餐测试

*   仪表盘流量测试
    *   局域网文件共享传输小文件流量测试
    *   局域网文件共享传输大文件流量测试
    *   流量用完后主机是否被服务器踢出测试
    *   流量用完后能否连接虚拟网络测试	

*   重连接测试

    *   一个主机能否连接到同一个虚拟网络多次测试
    *   一个主机能否连接到多个虚拟网络测试

*   手机端apk文件连接虚拟网络测试

    *   手机端连接虚拟网络测试
    *   手机端ping ip测试



## 5. 免测软件特征

*   详细的性能测试、安全测试、跨浏览器兼容性深度测试（本次计划主要关注核心功能）。
*   软件强度测试



## 6. 测试策略和手段

*   测试方法：
    *   黑盒测试
    *   功能测试
    *   用户界面测试 (UI Test)
    *   可用性测试 (初步)
    *   回归测试
*   测试手段：
    *   手动测试
    *   测试用例驱动
    *   探索性测试



## 7. 测试项成败标准

*   单个测试用例通过标准： 实际结果与预期结果一致。
*   模块/功能通过标准：
    *   该模块/功能所有严重（Critical）和主要（Major）级别的缺陷已修复。
    *   次要（Minor）和微小（Trivial）缺陷数量较少且不影响核心流程。
    *   核心功能点100%通过。
*   第一轮/第二轮测试结束标准：
    *   所有计划的测试用例已执行。
    *   发现的缺陷已记录并告知负责开发的同学。
*   第三轮测试（总测试/回归测试）通过标准（即整体测试通过标准）：
    *   所有先前报告的严重和主要缺陷已确认修复。
    *   回归测试未发现新的严重或主要缺陷。
    *   所有核心功能按预期工作。
    *   软件达到团队预期的质量水平，基本可用。



## 8. 测试暂停/停止的标准

*   暂停标准：
    *   发现阻断性缺陷（Blocker），导致大部分关键测试用例无法继续执行。
    *   测试环境发生严重故障且短时间内无法恢复。
    *   测试所需的关键软件版本不可用。
    *   项目需求发生重大变更，导致现有测试计划和用例不再适用（需团队讨论）。
*   恢复标准：
    *   导致暂停的阻断性缺陷已修复并验证。
    *   测试环境恢复稳定。
    *   关键软件版本可用。
    *   根据需求变更调整了测试计划和用例。
*   停止标准：
    *   所有计划的测试活动已完成。
    *   测试结果满足第7节中定义的“整体测试通过标准”。
    *   团队成员共同决定停止测试。
    *   预定的测试时间结束。



## 9. 测试交付物

*   软件测试计划（本文档）
*   测试用例 (网页端针对登录、注册、Dashboard 功能，客户端中针对虚拟网络连接功能)
*   缺陷报告
*   测试执行记录
*   每轮测试的简要总结
*   最终测试总结报告 (第三轮回归测试报告)



## 10. 测试任务

*   计划阶段： 编写和评审软件测试计划 (本文档)。
*   设计阶段：
    *   设计登录和注册界面的测试用例。
    *   设计 Dashboard 界面的测试用例。
    *   设计虚拟网络添加删除连接的测试用例
    *   设计连接过程中更改虚拟网络设置的测试用例
*   准备阶段：
    *   准备和确认测试环境。
    *   准备测试数据。
*   执行阶段：
    *   第一轮测试执行： 执行登录、注册界面的测试用例，执行虚拟网络添加删除连接的测试用例，然后报告缺陷。
    *   第二轮测试执行： 执行 Dashboard 界面的测试用例，执行连接过程中更改虚拟网络设置的测试用例，然后报告缺陷。
    *   第三轮测试执行（回归测试）： 执行登录、注册、Dashboard 的关键测试用例，执行连接更改虚拟网络的关键测试用例。然后验证缺陷修复情况，进行回归测试。
*   总结阶段：
    *   编写每轮测试的简要总结。
    *   编写最终测试总结报告。



## 11. 测试环境

*   硬件： 团队成员各自的 PC/笔记本电脑 (Windows 10/11, Linux)
*   软件：
    *   操作系统： Windows 10/11, 常见 Linux 发行版
    *   浏览器： Google Chrome , Microsoft Edge(可选)
    *   被测应用： Hyacinth 应用程序（包含 Web 页面与 EasyTier GUI）
    *   后端服务： Hyacinth Go 后端服务实例（确保其稳定运行并可供 Web 前端访问，由开发同学部署或提供访问方式）
*   网络： 团队成员各自稳定的互联网连接。



## 12. 职责

本项目测试环节的参与人员及其主要职责如下：

*   W (开发人员):
    *   负责 Hyacinth Web 应用后端及前端的开发工作。
    *   提供符合测试要求的软件版本给测试人员（J、L）。
    *   及时修复在 Web 界面测试过程中由L报告的缺陷。
    *   及时修复在 GUI 界面测试过程中由J报告的缺陷
    *   在测试过程中提供必要的技术支持，协助解决与 Web 界面相关的环境或应用本身的技术问题。
*   L (网页端测试人员):
    *   根据本测试计划，设计和编写 Web 界面的详细测试用例。
    *   执行本计划中定义的针对产品介绍页、登录页、注册页及 Dashboard 各模块的各项功能测试及回归测试。
    *   准确记录、报告（提交给W）和跟踪 Web 界面测试中发现的缺陷。
    *   编写 Web 界面测试的阶段性总结和最终测试总结报告。
    *   与开发人员（W）就测试发现的问题进行沟通，并验证缺陷修复情况。
*   J (GUI测试人员):
    *   根据本测试计划，设计和编写GUI界面的详细测试用例
    *   执行本计划中定义的针对GUI连接虚拟网络，更改虚拟网络设置，Windows端和手机端测试
    *   准确记录、报告（提交给W）和跟踪GUI测试中发现的BUG
    *   编写GUI界面测试的阶段性总结和最终测试总结报告
    *   与开发人员（W）就测试发现的问题进行沟通，并验证缺陷修复情况。



## 13. 进度安排

| 任务                         | 开始日期    | 结束日期    |
| :--------------------------- | :---------- | :---------- |
| 测试计划编写与团队讨论       | 5月10日     | 5月15日     |
| 测试用例设计                 | 5月16日     | 5月20日     |
| 第一轮测试                   | 5月23日     | 5月23日     |
| **缺陷修复与验证 (第一轮)**  | **5月25日** | **5月28日** |
| 测试用例设计                 | 5月26日     | 5月29日     |
| 第二轮测试                   | 5月30日     | 5月30日     |
| **缺陷修复与验证 (第二轮)**  | **6月1日**  | **6月3日**  |
| 回归测试用例准备             | 6月4日      | 6月4日      |
| **第三轮测试 (总测试/回归)** | **6月5日**  | **6月5日**  |
| 最终测试总结报告编写         | 6月6日      | 6月7日      |
