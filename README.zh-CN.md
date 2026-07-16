<div align="center">

# Make Codex Skin

### 描述一种感觉，让 AI 把它设计成皮肤。

一个小而清楚的开源 Skill：教 Codex 把开放的视觉描述变成完整、可读的 Codex 桌面皮肤包。

[English](./README.md) · 简体中文

</div>

![名画夜班的脱敏模拟预览](./docs/masterpieces-after-hours-preview.jpg)

## 一个仓库，只做一个 Skill

这个仓库刻意不包含网站、皮肤聚合站、npm 工程、安装器、注入引擎，也不提供固定风格菜单。

这个 Skill 教会 AI：

- 理解用户描述的情绪、艺术参考、图片、材质与文化线索；
- 自主形成视觉方向，而不是从几种预设风格里挑一个；
- 让配色、界面材质、构图、图片、字体与动效属于同一个系统；
- 保护侧边栏、任务内容、代码、控件和输入框的可用性；
- 生成可以检查和分享的纯数据皮肤文件夹。

它**不会**修改 Codex、替换 `app.asar`、重启应用，也不会把自己描述成 OpenAI 官方主题系统。真实应用皮肤需要独立可信的渲染器，不属于第一版开源范围。

## 安装

```bash
git clone https://github.com/1zhangyy1/make-codex-skin.git make-codex-skin-repo
mkdir -p ~/.codex/skills
cp -R make-codex-skin-repo/make-codex-skin ~/.codex/skills/
```

如果没有立刻看到新 Skill，重新启动一次 Codex。

## 使用

直接描述你想要的感觉：

```text
使用 $make-codex-skin 做一个法式浪漫、有艺术气息的皮肤。
像一间安静的左岸工作室，温暖、细腻，同时适合长时间阅读。
```

你也可以提供图片、提出从未出现过的艺术方向，或者让 Skill 修复一个已有皮肤，同时保留它原本的个性。

结果是一个简单的文件夹：

```text
my-skin/
├── skin.json
├── preview.png          可选
├── LICENSE.txt          可选
└── assets/
    └── background.png   可选
```

仓库包含两个可以检查的真实结果：

- [`make-codex-skin/examples/parisian-atelier`](./make-codex-skin/examples/parisian-atelier/)：从“法式浪漫”描述生成的程序化皮肤。
- [`make-codex-skin/examples/masterpieces-after-hours`](./make-codex-skin/examples/masterpieces-after-hours/)：从“让名画里的人使用电脑”生成的带图皮肤。

它们用来展示工作过程，不是要求 AI 套用的配方。

## 带图案例：名画夜班

用户最初只说了一句话：

> 做一个艺术展皮肤，让名画里的人用电脑。

Skill 把它转译成闭馆后的美术馆：重新演绎的蒙娜丽莎、戴珍珠耳环的少女与梵高集中在右侧，围着没有品牌和屏幕文字的电脑工作；左侧与底部中央继续为 Codex 原生内容留白。

背景图使用 OpenAI 图像生成制作。人物来自公共领域名画的重新演绎，没有直接复制第三方画作文件，也没有嵌入 Logo、屏幕文字或假界面。图片素材目前保持 `UNLICENSED`，直到创作者明确选择再利用许可证。

上方图片是专门为仓库制作的脱敏模拟预览，不包含私人 Codex 任务，也不代表官方主题支持或一键安装能力。

图片位置本身就是皮肤设计的一部分，不是最后改一个坐标。Skill 现在明确区分：全窗环境图、边缘主角、透明前景、纹理场，以及首页/任务页双图，并要求在多个窗口尺寸下检查裁切。详见 [`image-placement.md`](./make-codex-skin/references/image-placement.md)。

当前“名画夜班”源图被诚实记录为一次位置测试：它是 `2.50:1` 的超宽画布，放进普通 Codex 窗口时会被 `cover` 大幅裁切。README 模拟图展示目标层级，但案例说明已经标明：真正作为跨窗口成品之前，还需要重新构图为 16:10 画布。

## Skill 如何思考

```text
用户语言或参考图
        ↓
理解情绪、空间、光线、材质和节奏
        ↓
综合成一个连贯的艺术方向
        ↓
映射为可读的界面与本地素材
        ↓
交付纯数据皮肤文件夹与诚实的 QA 结果
```

创作判断保持高自由度；文件结构、可读性、素材权利和安全边界保持严格。

## 仓库结构

```text
make-codex-skin/          可以安装的 Skill，内含两个案例
docs/                     脱敏 README 预览图
README.md                 英文项目介绍
README.zh-CN.md           中文项目介绍
LICENSE                   MIT
```

## 当前边界

v0.1 先验证一件事：AI 能否在没有固定视觉配方菜单的情况下，学会设计多样的 Codex 皮肤。它暂时不解决一键安装，也不承诺跨版本实时渲染。

输出格式是实验性的社区格式，不是 Codex 官方 Appearance 主题格式。没有明确授权时，不要分发角色、品牌、照片、字体或其他受保护素材。

## 参考项目：Codex-Dream-Skin

本项目参考了 [Fei-Away/Codex-Dream-Skin](https://github.com/Fei-Away/Codex-Dream-Skin)。这个项目验证了外部渲染器可以在保持 Codex 原生控件可交互的同时，使用首页主图、低干扰任务背景、本机回环 CDP 与恢复流程；其 macOS 文档也建议图片宽度至少 2000 px，并为原生内容保留安静区域。

`make-codex-skin` 是独立的 AI 创作 Skill 与实验性数据格式，不复制、不捆绑、不安装 Codex Dream Skin 引擎，也不声称可以直接兼容它。感谢 Fei-Away 与贡献者把真实渲染路径公开给社区参考。

## 许可证

Skill 与原创文档采用 [MIT License](./LICENSE)。独立案例或社区贡献的素材可以声明自己的许可证。

“OpenAI”和“Codex”是其权利人的商标。本项目是独立社区项目，与 OpenAI 没有隶属、背书或官方支持关系。
