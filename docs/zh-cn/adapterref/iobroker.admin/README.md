---
BADGE-Number of Installations: http://iobroker.live/badges/admin-stable.svg
BADGE-NPM version: http://img.shields.io/npm/v/iobroker.admin.svg
BADGE-Downloads: https://img.shields.io/npm/dm/iobroker.admin.svg
---
# Admin

管理适配器用于配置整个ioBroker-Installation及其所有适配器。
它提供了一个Web界面，可以通过“http：//<服务器的IP地址>：8081”打开
在Web浏览器中。此适配器与ioBroker一起自动安装。

## 配置：

适配器“admin”的配置对话框提供以下设置：
![img_002](img/admin_img_002.png)

**IP：** 可以在此处选择“admin”Web服务器的IP地址。
可以选择不同的IPv4和IPv6地址。默认值为0.0.0.0 \。
如果您认为，0.0.0.0是无效设置，请让它留在那里，因为它
绝对有效。如果更改地址，您将能够访问Web服务器
只能通过这个地址。 **端口：** 您可以指定“admin”Web服务器的端口。
如果PC或设备上有更多Web服务器，则必须自定义端口以避免出现问题
双端口分配。 **编码：** 如果应使用安全的https协议，则启用此选项。

**身份验证：** 如果您希望使用登录名/密码进行身份验证，则应启用此复选框。
用户“admin”的默认密码是“iobroker”**缓冲区：** 加速页面加载启用此选项。
通常只有开发人员想要取消选中此选项。

## 处理：

管理员的主页包含多个选项卡。 **适配器：** 这里的实例
可以安装或删除适配器。使用更新按钮
![img_005](img/admin_img_005.png)
如果新版本的适配器可用，我们可以在左上角看到。
![img_001](img/admin_img_001.jpg)

显示适配器的可用和已安装版本。对于整体观看的状态
适配器是彩色的（红色=在计划中;橙色= alpha;黄色= beta）。更新版本的更新
适配器也在这里制作。如果有更新的版本，标签的字体将为绿色。
如果最后一列中的问号图标处于活动状态，您可以从那里获取包含适配器信息的网站。
可用的适配器按字母顺序排序。已安装的实例位于列表的上半部分。

**实例：** 此处列出了已安装的实例，可以进行相应的配置。如果标题
实例加下划线，您可以点击它，相应的网站将被打开。

![img_003](img/admin_img_003.png)

**对象：** 管理对象（例如连接硬件的设置/变量/程序）

![img_004](img/admin_img_004.png)

**国家：** 当前状态（对象的值）
如果安装了适配器历史记录，则可以记录所选的数据点。
已记录的数据点在右侧选择，并显示绿色徽标。

**脚本：** 此选项卡仅在安装了“javascript”适配器时才有效。

**节点红色：** 此选项卡仅在安装并启用“node-red”适配器时可见。

**主机：** 安装了ioBroker的计算机。这里可以安装最新版本的js-controller。
如果有新版本，则选项卡的字母为绿色。要搜索新版本，您必须单击更新
左下角的图标。

**枚举：** 此处列出了CCU的收藏，交易和空格。

**用户：** 这里可以添加用户。要执行此操作，请单击（+）。默认情况下有一个管理员。

**组：** 如果单击左下角的（+），则可以创建用户组。从下拉菜单中，用户被分配到组。

**事件：** 条件的运行更新列表。 **日志：** 此处显示日志在选项卡实例中显示记录的日志级别
可以设置单个实例。在选择菜单中，选择显示的最小日志级别。如果发生错误
日志的字体显示为红色。

## Changelog
### 6.9.0 (2023-08-21)
* (bluefox) Added possibility to change log direction
* (bluefox) JSON config: Added possibility to filter out internal IP addresses
* (bluefox) JSON config: Added _changed flag for formula in JSON config
* (bluefox) JSON config: Added option `reloadBrowser` to sendto in JSON config
* (bluefox) JSON config: Allowed positioning of add button on the very top of the table
* (bluefox) JSON config: Trim strings by saving and not by typing
* (bluefox) Added alias creation from object browser
* (bluefox) Allowed to change chart type
* (foxriver76) show a date picker when setting state (role: date/type: number)
* (foxriver76) fixed problem, that creation of folders was not possible
* (foxriver76) adapted text to clarify, that only tarball can be installed from path
* (foxriver76) type string/role date will now also be previewed as a date in objects tab
* (foxriver76) fixed problem with table formatting on history data point viewer
* (foxriver76) fixed problem that could render update dialog with invalid property
* (foxriver76) fixed sentry icon being in wrong position if no compact flag provided

### 6.8.3 (2023-08-16)
* (foxriver76) added description to adapter rating dialog
* (bluefox) Extended the select component with grouping
* (bluefox) Allowed the sorting of adapters by name and not only by title
* (bluefox) Allowed the set state JSON config component

### 6.8.0 (2023-08-14)
* (foxriver76) try to find the correct IP for the controller UI multihost slave upgrade
* (foxriver76) admin is now showing update information, while it is stopped during upgrade
* (foxriver76) required Node.js version is 16 as 14 is End-Of-Life
* (foxriver76) fixed downloading folders recursive

### 6.7.2 (2023-08-09)
* (foxriver76) remove https certificate options
* (foxriver76) prevent error log of not used certificates even-though they are used
* (foxriver76) fixed issue with docker host cards on intro tab
* (foxriver76) fixed issue if adapter readme is opened in new tab
* (bluefox) corrected opening of custom tabs, e.g., for fullcalendar
* (bluefox) allowed downloading of recursive folders

## License
The MIT License (MIT)

Copyright (c) 2014-2023 bluefox <dogafox@gmail.com>