# matchbox-cards

火柴盒（Matchbox）App 角色卡市场的**在线目录**。

- 本仓库只存 `cards.json`（卡片元数据：名字/作者/简介/标签 + 原始下载直链）
- **不托管任何卡片本体**，卡片内容仍托管在各作者自己的仓库，点击下载时由 App 直连/镜像链拉取
- `cards.json` 结构：

```json
{
  "version": 1,
  "cards": [
    {
      "name": "角色名",
      "author": "作者",
      "description": "简介",
      "tags": ["标签1", "标签2"],
      "url": "https://raw.githubusercontent.com/作者/仓库/main/cards/xx.v2.json"
    }
  ]
}
```

## 如何添加新卡

1. 在 `cards.json` 的 `cards` 数组追加一条（只存元数据 + 原始直链，不传卡本体）
2. 提交并推送到 main 分支
3. App 端市场会自动拉取更新（在线目录优先，失败回退内置目录）

> 新增卡片前请确认：卡片内容可自由分发/作者同意公开；V2/V3 格式均可，App 解析器两者兼容。
