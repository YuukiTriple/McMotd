# Mirai-wiki
[![mirai](https://img.shields.io/badge/mirai-v2.10.0-brightgreen)](https://github.com/mamoe/mirai )  
基于[mirai](https://github.com/mamoe/mirai )的Minecraft服务器信息查询插件

> 关于Linux运行环境  
> 如果你正在使用Linux而不是Windows来运行Mirai,请确保系统中安装了中文字体，否则图片可能不会被正常渲染。  

## 如何安装
1. 在[这里](https://github.com/Under-estimate/McMotd/releases/ )下载最新的插件文件。
2. 将插件文件放入[mirai-console](https://github.com/mamoe/mirai-console )运行生成的`plugins`文件夹中。
3. 如果您还未安装[chat-command](https://github.com/project-mirai/chat-command )插件(添加聊天环境中使用命令的功能)，你可以从下面选择一种方法安装此插件：
> 1. 如果您正在使用[Mirai Console Loader](https://github.com/iTXTech/mirai-console-loader )来启动[mirai-console](https://github.com/mamoe/mirai-console )，您可以运行以下命令来安装[chat-command](https://github.com/project-mirai/chat-command )插件：  
> `./mcl --update-package net.mamoe:chat-command --channel stable --type plugin`
> 2. 如果您没有使用[Mirai Console Loader](https://github.com/iTXTech/mirai-console-loader )，您可以在[这里](https://github.com/project-mirai/chat-command/releases )下载最新的[chat-command](https://github.com/project-mirai/chat-command )插件文件，并将其一同放入[mirai-console](https://github.com/mamoe/mirai-console )运行生成的`plugins`文件夹中。
4. 启动[mirai-console](https://github.com/mamoe/mirai-console )之后，在后台命令行输入以下命令授予相关用户使用此插件命令的权限：
> - 如果您希望所有群的群员都可以使用此插件，请输入：  
> `/perm grant m* org.zrnq.mcmotd:command.mcp` (仅可使用`mcp`指令)  
> `/perm grant m* org.zrnq.mcmotd:*` (可使用全部指令)
> - 如果您希望只授予某一个群的群员使用此插件的权限，请输入：  
> `/perm grant m<QQ群号>.* org.zrnq.mcmotd:command.mcp` (仅可使用`mcp`指令)  
> `/perm grant m<QQ群号>.* org.zrnq.mcmotd:*` (可使用全部指令)
> - 如果您希望只授予某一个群的特定群员使用此插件的权限，请输入：  
> `/perm grant m<QQ群号>.<群员QQ号> org.zrnq.mcmotd:command.mcp` (仅可使用`mcp`指令)  
> `/perm grant m<QQ群号>.<群员QQ号> org.zrnq.mcmotd:*` (可使用全部指令)
> - 如果你希望了解更多高级权限设置方法，请参阅[mirai-console的权限文档](https://github.com/mamoe/mirai-console/blob/master/docs/Permissions.md )
5. 安装完成。
## 权限列表
*有关权限部分的说明，参见[mirai-console的权限文档](https://github.com/mamoe/mirai-console/blob/master/docs/Permissions.md )*  
根权限： `org.zrnq.mcmotd:*`  
获取MC服务器信息： `org.zrnq.mcmotd:command.mcp`  
绑定服务器到群聊： `org.zrnq.mcmotd:command.mcadd`  
删除群聊绑定的服务器： `org.zrnq.mcmotd:command.mcdel`
## 插件命令
> mcp (服务器地址/服务器名称) : 查询指定地址或绑定到指定名称上的服务器信息，当本群仅绑定了一个服务器时可省略参数  
> mcadd <服务器名称> <服务器地址> : 将指定地址的服务器绑定到指定名称上。各个群聊绑定的服务器相互独立。  
> mcdel <服务器名称> : 删除指定名称的服务器
## 插件配置
### 字体配置
如果您的系统中安装了多个字体，您可以在`/config/org.zrnq.mcmotd/mcmotd.yml`中设置渲染图片时使用的字体名称。

其中，服务器地址可以仅有域名，如`mc.example.com`，也可以带有端口号，如`mc.example.com:12345`

## FAQ
### Q: 在QQ群中发送命令没反应
A: 请检查是否安装了[chat-command](https://github.com/project-mirai/chat-command )插件，如果没有安装请看[这里](#如何安装 )

### Q: `UninitializedPropertyAccessException:lateinit property FONT has not been initialized`
A: 如果您正在使用Linux运行mirai，请检查是否安装了中文字体
