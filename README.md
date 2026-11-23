# 静态游戏 H5 长图 · Game H5 Long Image

面向游戏活动、版本专题和角色介绍的静态长图 Skill。从真实文案和参考素材出发，先排出手机长页的阅读顺序和版式，再准备分区素材，最后融合成一张完整长图。

[安装](#安装) · [怎么用](#怎么用) · [模型与 API Key](#模型与-api-key) · [交付](#交付)

## 安装

下载仓库 ZIP 或克隆仓库。把完整的 `game-h5-long-image` 文件夹放入助手支持的 Skill 目录，保留其中的 [SKILL.md](game-h5-long-image/SKILL.md) 和 `references/`。

**Codex · Windows PowerShell**

```powershell
git clone https://github.com/hx143853-sys/game-h5-long-image-skill.git
$skillRoot = Join-Path $env:USERPROFILE '.agents\skills'
New-Item -ItemType Directory -Path $skillRoot -Force | Out-Null
Copy-Item -LiteralPath '.\game-h5-long-image-skill\game-h5-long-image' -Destination $skillRoot -Recurse
```

**Codex · macOS / Linux**

```bash
git clone https://github.com/hx143853-sys/game-h5-long-image-skill.git
mkdir -p "$HOME/.agents/skills"
cp -R game-h5-long-image-skill/game-h5-long-image "$HOME/.agents/skills/"
```

也可以在 GitHub 点 **Code → Download ZIP**，解压后复制上述文件夹。如果已安装同名 Skill，请先核对版本，再更新原目录。其他支持 Agent Skills 的助手可按各自的目录规则安装。[Codex Skills 官方文档](https://developers.openai.com/codex/skills)

## 怎么用

1. 选择 `game-h5-long-image`，或在需求中写明「使用静态游戏 H5 长图 Skill」。
2. 给出页面用途、目标阅读宽度、完整文案和参考素材。标明要保留角色或活动信息的素材，以及只借鉴版式或画风的参考。
3. 先看章节顺序、布局样图和素材清单。只需要方案时，在该阶段取得布局说明和可复制的提示词。需要直接出图时，再用已配置的图像工具制作素材与整页。
4. 在手机阅读尺度核对文案、信息层级和章节衔接，再交付长图及可复用素材。

```text
使用 game-h5-long-image，先给我一套静态活动长图方案。
按我提供的首屏、角色介绍、活动规则和奖励内容排版，保留原文。
附件 1 保留角色和服装，附件 2 只参考版式。
请给出手机阅读宽度下的布局、素材清单和整页提示词。
```

## 模型与 API Key

| 环节 | 工作流用法 |
| --- | --- |
| 读参考、定布局 | 使用支持图片输入的助手分析素材、拟定章节和制作指令。 |
| 首图、字组和分区素材 | 工作流使用 GPT Image 2.5。复杂艺术字或多元素组图可选 Sunburst。 |
| 整页融合 | 工作流使用 Nano 2.1 制作连续背景、章节过渡和最终整页。 |

需要直接出图时，在助手或生图工具的模型设置中接入相应服务，并配置所选服务的 API Key。可用画幅、尺寸、透明和参考图数量以当前模型接入为准。

## 交付

- 布局方案与素材清单
- 一张完整的静态长图
- 已制作的素材组与裁切素材
- 按手机阅读尺度复核后的修改建议

参考资料位于 [布局](game-h5-long-image/references/layout.md)、[素材制作](game-h5-long-image/references/materials.md) 和 [整页融合与交付](game-h5-long-image/references/final-page.md)。流程整理自静态游戏 H5 工作流 v4.0.0，适合在通用 Agent Skills 环境中阅读和使用。
