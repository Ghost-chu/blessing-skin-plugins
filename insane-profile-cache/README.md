**如果你不清楚这是什么，请不要随意启用本插件。**

--------

本插件会在 `plugins/insane-profile-cache/cache` 目录下生成所有玩家 Profile 的静态文件缓存（就是 `玩家名.json` 里的内容），你可以直接将 `*.json` 请求的 root 设置为缓存目录，让 Web 服务器来处理静态文件，可有效降低服务器负载。当玩家更新 Profile（更换皮肤、优先模型等操作）时文件缓存也会更新。

因为不明原因，演示站负载一直高到爆炸（200+ QPS 是常态），再加上 Laravel 特有的运行效率低下，造成了整站响应速度屌慢的情况（可以说高并发打到 PHP 层的话就完了）。然而这只是个演示站点，我又没有钱上 CDN（好哥哥，唯一指定邮箱，请），遂出此下策，好孩子不要用哦。

如果你的皮肤站里玩家很多，请不要使用下面的网页链接，不然会因为生成持续时间太长而造成 504 Gateway Timeout 而导致失败。请在皮肤站目录下打开你亲爱的终端，运行如下命令：

```shell
$ php artisan profile:cache
```

如果没几个玩家的话直接用网页操作即可（然而没几个玩家的话也用不着这个插件）。
