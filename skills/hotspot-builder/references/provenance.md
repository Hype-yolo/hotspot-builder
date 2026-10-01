# 来源与许可

本 Skill 由 Hype 独立整理，指导开发 Agent 复用并改造 [AIHOT](https://github.com/KKKKhazix/AIHOT)，不代表上游作者，不是作者原始开发聊天记录。

参考提交：`8d5a39bb47c917616798a3fdd71688a80f6c9b6c`。核对日期：2026-10-01。上游可能更新；开发时记录选定提交，核对源码、提示词、schema 与锁文件的一致性。

## 可追溯的上游资料

- [项目说明：`README.md`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/README.md)
- [项目开发约束：`AGENTS.md`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/AGENTS.md)
- [行业改造：`docs/customize.md`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/docs/customize.md)
- [架构：`docs/architecture.md`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/docs/architecture.md)
- [采集与信源：`docs/sources.md`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/docs/sources.md)
- [筛选与推荐：`docs/selection.md`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/docs/selection.md)
- [事实与事件归组：`docs/grouping.md`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/docs/grouping.md)
- [部署：`docs/deploy.md`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/docs/deploy.md)
- [行业配置：`industry/README.md`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/industry/README.md)
- [生产评分提示词：`industry/prompts/selection-score.md`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/industry/prompts/selection-score.md)
- [两次评分的执行：`packages/backend/src/editorial/analyze.ts`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/packages/backend/src/editorial/analyze.ts)
- [候选召回：`packages/backend/src/events/recall.ts`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/packages/backend/src/events/recall.ts)
- [关系判断：`packages/backend/src/events/relate.ts`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/packages/backend/src/events/relate.ts)
- [热度计算：`packages/backend/src/events/hot.ts`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/packages/backend/src/events/hot.ts)
- [模型请求回执：`packages/backend/src/providers/receipts.ts`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/packages/backend/src/providers/receipts.ts)
- [上游许可：`LICENSE`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/LICENSE)
- [品牌和第三方说明：`NOTICE`](https://github.com/KKKKhazix/AIHOT/blob/8d5a39bb47c917616798a3fdd71688a80f6c9b6c/NOTICE)

生产提示词从目标项目的 `industry/prompts/` 读取；本包保留任务清单和改造要求，没有复制一份脱离源码的提示词实现。参考资料中的数值是上述快照的行为，不代表任何行业的通用最优参数。上游新闻内容与运营数据不随本 Skill 分发。

## 品牌与第三方资料

AIHOT 名称和 Logo 不在上游 MIT 授权范围内，新网站应使用自己的名称和标志。复用源码时保留上游 `LICENSE`、`NOTICE` 及所使用字体、图标等资产的许可；本包不分发这些资产。

## 本 Skill 的许可

以下许可随安装目录保留，单独复制 Skill 目录时也不要删除。

```text
MIT License

Copyright (c) 2026 Hype-yolo

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 上游许可

架构与运行规则参考、改编自数字生命卡兹克的 AIHOT 项目，保留上游完整许可：

```text
MIT License

Copyright (c) 2026 数字生命卡兹克

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
