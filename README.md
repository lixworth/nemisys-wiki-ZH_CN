<h1 align="center">Nemisys</h1>

Nemisys是一个使用RakNet和SPP协议的代理，在synapse服务器之间提供快速和安全的传输，以及良好的控制和数据同步。

## 安装 & 设置
1. 下载Nemisys, nukkit 和 synapse
2. 使用synapse运行nemisys和nukkit服务器以生成所有必需的配置文件。（之后你可以关闭它们）
3. Nemisys 配置

    a) 更改server.properties中 IP, synapse 端口和密码
        
    * IP: 服务器 IP
    * Synapse Port: SPP 协议端口 (用于Nemisys与所有节点（Synapse）服务器之间的通信)
    * Password: SPP身份验证密码
    
    b) 其他设置
plus-one-max-count: 服务器列表中显示的最大玩家数量将根据当前玩家数动态更改。例如 245/246

4. Synapse 配置
* disable-rak: 禁用默认的nukkit RakNet，因此没有人能够直接连接到此nukkit服务器
* enable: 启用 Synapse
* entries: Synapse可以连接到多个Nemisys服务器（对于更大的服务器，一个Nemisys服务器不必足够），这意味着，您必须为每个Nemisys实例指定更多条目。

    * 配置:
        * server-ip: IP地址
        * server-port: synapse 端口
        * isLobbyServer: 表示如果当前玩家所在的服务器将关闭，玩家将会被传送到哪里。唯一的例外是，如果当前玩家服务器设置为主服务器（如下所述），则玩家将因服务器关闭而被踢出。同样，在synapse和nemisys中，有一种方法可以将玩家转移到大厅，选择随机的大厅服务器。
        * isMainServer: 第一台服务器，在加入后将在其中传输播放器。您可以定义更多的主服务器，然后随机选择一个。

        * password: nemisys 配置中SPP身份验证的密码

        * description: 表示服务器唯一标识符，您不必为更多服务器使用相同的标识符，即使Nemisys不会显示任何错误消息。

5. 现在，您可以启动两个服务器（Nemisys和Nukkit与Synapse），并尝试连接到Nemisys服务器。您应该被转移到nukkit服务器。

## 特征
* 基础的插件API
* Nemisys有一个全局命令的API，因此使用权限插件，您可以在游戏中执行这些命令，而不必强制在所有服务器上指定命令。
* 您可以使用插件消息API在nemisys和nukkit之间轻松进行通信。Nemisys还有一些可以使用的默认消息命令。
