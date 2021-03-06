# 导入一个存在的 Gluster Storage 集群 

EayunOS 4.2 允许您导入一个 Gluster Storage 集群，以及这个集群上的所有主机。 

在您提供了集群中的任何主机的相关信息（如 IP 地址，主机名和密码）后，gluster peer status 命令会通过 SSH 在主机上运行，并显示集群上的主机列表。您需要手工验证每个主机的指纹信息并为它们提供密码。当集群中的某个主机已经被关闭，或因一些原因无法访问，您将无法导入这个集群。因为新导入的主机没有安装 VDSM，bootstrap 脚本会在主机被导入后为它们安装 VDSM 软件包，并重新启动这些主机。

**导入一个存在的 Gluster Storage 集群**

1. 选择**集群**资源页来在结果列表中列出所有的集群。

2. 点**新建**打开**新建集群**窗口。

3. 在下拉菜单中选择这个集群需要属于的**数据中心**。

4. 输入集群的**名称**和**描述**值。

5. 选**启用 Gluster 服务**和**导入现有的 gluster 配置**。

    导入现有的 gluster 配置选项只在您已经选择了**启用 Gluster 服务**选项后才会被显示。

6. 在**地址**项中输入这个集群中的任何服务器的主机名或 IP 地址。

    检查主机的指印信息来保证您连接到了正确的主机。如果一个主机无法被访问或有网络错误，**获取指印失败**信息将会在**指印**项中被显示。

7. 输入服务器的 **Root 密码**并点**确认**。

8. 添加主机窗口会被打开，并列出这个集群所包括的主机。

9. 为每个主机输入**名称**和 **Root 密码**。

10. 如果您想为所有主机设定同一个密码，选择**使用公共密码**选项。

    点**应用**为所有主机设置密码。

    确认指纹信息，然后点**确定**提交您的改变。

在主机被导入后，bootstrap 脚本会在主机上安装了所需的 VDSM 软件包并重新启动它们。一个存在的 Gluster Storage 集群被成功地导入到 EayunOS 管理平台上。
