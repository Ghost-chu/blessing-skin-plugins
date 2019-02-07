## 鬼畜魔改，仅支持Flarum

## 论坛数据对接

本插件可以让 Blessing Skin 与 Flarum 论坛程序的用户数据互通，用户可以使用论坛程序的用户名、邮箱、密码登录皮肤站，反之亦可。可以配合 [Authme](https://github.com/bs-community/blessing-skin-plugins/tree/master/authme-integration)、[CrazyLogin](https://github.com/bs-community/blessing-skin-plugins/tree/master/crazylogin-integration) 等登录系统的数据对接插件实现游戏内外的统一账号系统。

**注意：本插件依赖[「单角色限制」](https://github.com/bs-community/blessing-skin-plugins/tree/master/single-player-limit)插件，使用之前请务必启用该插件。**

### 插件配置

要进行论坛数据对接，请先将在皮肤站的 `.env` 配置文件中将你的 [密码加密算法](https://github.com/printempw/blessing-skin-server/wiki/%E5%A6%82%E4%BD%95%E5%A1%AB%E5%86%99-.env-%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6#-%E5%AE%89%E5%85%A8%E7%9B%B8%E5%85%B3) 修改为 `PHP BCRYPT`。如果在皮肤站安装完成后再修改密码加密算法的话，之前已经注册的用户将会全部 **【无法登录】**（可以通过找回密码功能重置）。

接下来，请在「论坛数据对接」插件的配置页面正确填写以下项目：

- 论坛程序所在的数据库地址、端口、用户名以及密码；
- 支持跨数据库主机对接（前提需要目标数据库支持远程连接），但可能会造成延迟；
- 论坛程序的用户数据表名称（请根据你的实际情况填写）。

用户数据表名称，Flarum 默认为 `users`。

目前本插件仅支持对接 Flarum，如有其他需求可以联系我添加。

### 注意事项

如果登录论坛时提示密码不正确，请尝试让用户重新登录一次皮肤站以刷新密码 hash。
