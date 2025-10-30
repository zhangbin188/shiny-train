# 在CM源代码基础上增加三个变量，统一生成 ADDCSV 文件的节点名称

- 变量 `RENAME`：节点别名的前缀，例如：`CF优选🚀`
- 变量 `COUNTRYNUM`：节点显示的`国家`名称，查看你的`csv文件表头`中**国家**位于`TLS列`后`第几列`，比如我的是TLS后第四列，我这里就填写`4`
- 变量 `CITYNUM`：节点显示的`城市`名称，查看你的`csv文件表头`中**城市**位于`TLS列`后`第几列`，比如我的是TLS后第五列，我这里就填写`5`
- 最终订阅出来的节点名称为 `CF优选🚀日本 - 大阪`

![image](https://github.com/user-attachments/assets/9d61c9d2-b69e-4a75-a2cd-bd08bd0dc73b)

我使用的[测速工具](https://github.com/bh-qt/Cloudflare-IP-SpeedTest)生成的csv表头是这样的：

![image](https://github.com/user-attachments/assets/8de5cf81-4490-4499-b505-42375159698a)

如果你不想以`国家-城市`显示节点名称，例如你想显示为`数据中心-延迟`，则可将变量 `COUNTRYNUM`的值设为`4`，将变量`CITYNUM`的值设为`5`

修改后的代码文件为 `_worker2.js`

**生成补丁**：

```bash
diff -u _worker.js _worker2.js > worker.patch
// 或者
git diff --no-index _worker.js _worker2.js > worker.patch
```

**声明：本修改不负责维护，一切错误请自行解决。如果没有代码动手能力，建议用CM大佬的源代码进行搭建**

# 🚀 edgetunnel 原仓库说明

**除新增变量外，其他变量与CM源码相同**

https://github.com/cmliu/edgetunnel
