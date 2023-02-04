# 关于jsdelivr的使用



## 1. jsDelivr是什么？
https://www.jsdelivr.com/
jsDelivr由ProspectOne维护的公共库，使用的融合CDN技术，由Cloudflare、Fastly、StackPath、QUANTIL等CDN供应商提供了全球超过750个CDN节点。

最重要的是，jsDelivr在中国大陆也拥有超过数百个节点，因为jsDelivr拥有正规的ICP备案，解决了中国大陆的访问速度优化，实现真正的全球极速低延迟体验。

jsDelivr是免费的、不限制带宽的，可以加速NPM、Github内的文件。

将静态文件资源放到Github的仓库内，再使用jsDelivr进行加速访问，达到完全零成本优化访问速度。

## 2. 如何访问？

#### 直接访问
文件路径为：`https://cdn.jsdelivr.net/gh/<user>/<repo>/<filename>`

#### 访问最新
文件路径为：`https://cdn.jsdelivr.net/gh/<user>/<repo>@latest/<filename>`

如：https://cdn.jsdelivr.net/gh/xu-ux/common@latest/css/jetbrains.css

#### 版本区分访问
文件路径为：`https://cdn.jsdelivr.net/gh/<user>/<repo>@<version>/<filename>`

## 3. 代码压缩

jsDelivr还提供了代码压缩服务，比如将JS/CSS的代码压缩，优化访问速度。

只是前几次访问会执行压缩操作，速度比较慢。后面就会将文件缓存，速度不会再慢了。

直接将访问链接的文件后缀改成`文件名.min.后缀名`即可，比如：

文件路径为：`https://cdn.jsdelivr.net/gh/<user>/<repo>@<version>/<文件名.min.后缀名>`

## 4. 统计引入

`https://www.jsdelivr.com/package/gh/<user>/<repo>`

比如这个：

https://www.jsdelivr.com/package/gh/xu-ux/common

## 5.更新缓存

解决方法:

1️⃣更新

将 cdn.jsdelivr.net中的cdn改为 purge.

执行请求:

`https://purge.jsdelivr.net/gh/<user>/<repo>@<version>/<文件名.min.后缀名>`

2️⃣生成Release

另一种方法，就是生成新tag的Release，然后使用 @latest 去引用。