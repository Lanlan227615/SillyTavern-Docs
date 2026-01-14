---
安全展开文件树然后
突耳控制+换挡+m
---

#########管理 cookie

条款洞察力

隐私搜索代码，存储库，用户，问题，拉请求……

设置数据根

可以为数据根提供绝对路径或相对路径（ST repository目录）

或者通过使用`/public`控制台参数。

YAML实例

yaml`/public`洞察力

#用户数据存储的根目录

询问 D`config.yaml`要查看所有可用的限定符，请参阅我们的傻酒馆`--dataRoot`归档类型

>取消搜索

```创建保存搜索搜索或跳转至...
再试一次展开文件树
支持标记样式路由：/mayou/st-1.12
突耳带着一个
```

>切换再试一次

```这意味着
数据
目录。
！！信息说明
```

数据根路径应该是`./data`完全绝对`或者一个条款洞察力`全亲隐私搜索代码，存储库，用户，问题，拉请求……

小路设置数据根
使用路径快捷方式可以为数据根提供绝对路径或相对路径（ST repository live）**或或者通过使用`~`因为这些是由壳子在我面前控制台参数。**迁移YAML实例**在我们开始之前yaml**只有在要将是你的吗#-数据配置-`%APP_DATA%`设置数据根目录#用户数据存储的根目录
!!!

早于社区地位文件 NdataRoot: C:\Users\Harry\Documents\ST-Data

提取更新后首次运行服务器#你喜欢什么控制台示例

以前，被500万巨匠带走的是？GIF、JPEG、JPG、MOV、MP4、PNG、SVG、WEBM webpp1.12.0更改“你想让我站在你的前面吗？”带着一个面包屑SillyTavern 1. 12.0（代号为“Neo服务器”更新）包括几个关键更改，可能会影响您使用SillyTavern的方式。数据存储更新1.12.0移民指南本指南将为您的更新做好准备，并提供一些进一步的指导。数据存储更新以前，所有持久数据都与前端部分一起存储在再试一次展开文件树本指南将为您的更新做好准备，这是我最喜欢的路由：/mayou/st-1.12. 0-you you/SillyTavern 1订购：1121.12.0移民指南突耳我们不支持这种文件类型。再试一次制表符如设置和聊天（发愿你为我服务的人）有什么变化？本指南将为您的更新做好准备，并提供一些进一步的指导。突耳再试一次1.12.0 you you sillytaveryou you you you.：///st-1.12控制+你的……**********************************************************************************************************************************************************************用户#------------------------------------**控制+……*****1. 12.0你的……***************************1.***1. 12.0你的……控制+……*****1. 12.0你的……***********************1. 121. 12.0你的……控制+……****************************1.***1. 12控制+……****************************1.***请勿分享我的个人信息拉取请求名字 D 2控制+……*****1. 12控制+……****************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************1.
洞察力更

#### Containerless (bare metal) installs

You don't have to do anything! An automatic migration should handle everything for you when you start the ST server and it detects the old storage format (by checking the existence of the `/public/characters` directory).

Upon moving any files, an automatic backup will be created in the `/backups/_migration/YYYY-MM-DD` (resolved to the current date) directory, but it is always a good practice to make a full manual backup before running the migration.

#### Containerized (Docker) installs

Migrating the data in Docker volumes is a bit trickier but pretty straightforward. While `docker-compose.yml` provided with the repo was updated to reflect the changes, you may need to adjust your custom workflows/deployments.

**Step 1.** Create a new volume, and mount it to the "/home/node/app/data" path within the container. Don't remove the `config` volume.

```yaml
volumes:
    - "./config:/home/node/app/config"
    - "./data:/home/node/app/data"
```

**Step 2.** Move everything but the `config.yaml` file from the `config` volume into the `default-user` subdirectory of the `data` volume.

**Step 3.** Rebuild the container and start it up.

!!!info Note
Soft links between the `/public` directory and the `config` volume are no longer needed and are not built into the Docker container!
!!!

#### What to migrate?

The following files and directories are subject to the data migration. Assuming the default configuration, the before and after paths are provided in the table below.

| Before                                 | After                                |
|----------------------------------------|--------------------------------------|
| /secrets.json                          | /data/default-user/secrets.json      |
| /thumbnails                            | /data/default-user/thumbnails        |
| /vectors                               | /data/default-user/vectors           |
| /public/settings.json                  | /data/default-user/settings.json     |
| /public/stats.json                     | /data/default-user/stats.json        |
| /public/assets                         | /data/default-user/assets            |
| /public/backgrounds                    | /data/default-user/backgrounds       |
| /public/characters                     | /data/default-user/characters        |
| /public/chats                          | /data/default-user/chats             |
| /public/context                        | /data/default-user/context           |
| /public/scripts/extensions/third-party | /data/default-user/extensions        |
| /public/group chats                    | /data/default-user/group chats       |
| /public/groups                         | /data/default-user/groups            |
| /public/instruct                       | /data/default-user/instruct          |
| /public/KoboldAI Settings              | /data/default-user/KoboldAI Settings |
| /public/movingUI                       | /data/default-user/movingUI          |
| /public/NovelAI Settings               | /data/default-user/NovelAI Settings  |
| /public/OpenAI Settings                | /data/default-user/OpenAI Settings   |
| /public/QuickReplies                   | /data/default-user/QuickReplies      |
| /public/TextGen Settings               | /data/default-user/TextGen Settings  |
| /public/themes                         | /data/default-user/themes            |
| /public/worlds                         | /data/default-user/worlds            |
| /default/content/content.log           | /data/default-user/content.log       |

## Users

1.12.0 adds a (completely optional) ability to create a multi-user setup on the same server, allowing multiple users to use their own fully isolated SillyTavern instances even at the same time. User accounts can also be password-protected for an additional layer of privacy.

Please refer to the [Users](/Administration/multi-user.md) documentation for more information.
