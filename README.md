# Seedance-Product-Video

为 [Seedance 2.0](https://jimeng.jianying.com) 视频生成模型撰写产品宣传动画提示词的 AI Skill。

Generate professional 15-second motion graphics prompts for Seedance 2.0 video model — one-take, no cuts, smooth morphing transitions.

## Features

- 4 种美学风格可选：Apple Cupertino / Microsoft Fluent / Bauhaus Zen / Vercel Dark
- 15 秒一镜到底，5-6 个连续形变阶段的时间戳结构
- 支持垫图（参考图）模式，自动标注图片占位符并引导使用"全能参考"模式
- 生成后可通过即梦 Dreamina CLI 直接生成视频（自动检测安装状态）

## Installation

### Option 1: npx skills (Recommended)

Using [vercel-labs/skills](https://github.com/vercel-labs/skills):

```bash
npx skills add op7418/Seedance-Product-Video -a claude-code
```

Global install:

```bash
npx skills add op7418/Seedance-Product-Video -a claude-code -g
```

### Option 2: Manual

Clone the repo into your Claude Code skills directory:

```bash
git clone https://github.com/op7418/Seedance-Product-Video.git ~/.claude/skills/seedance-prompt
```

## Usage

Tell your AI assistant:

```
帮我生成一个 Seedance 产品宣传视频的提示词
```

Or use the slash command directly:

```
/seedance-prompt
```

The skill will:

1. Ask about your product, requirements, and image assets
2. Analyze your materials and select the best visual style
3. Generate a 1000-2000 character English prompt with timestamp structure
4. Guide you through reference image setup (if applicable)
5. Offer to generate the video via Dreamina CLI

## Aesthetic Styles

| Style | Vibe | Best For |
|-------|------|----------|
| A: Apple Cupertino | Frosted glass, titanium depth | Flagship products, premium hardware |
| B: Microsoft Fluent | Acrylic layers, colorful gradients | Productivity tools, platforms |
| C: Bauhaus / Kenya Hara | Matte zen, minimal whitespace | Efficiency tools, readers |
| D: Vercel / Linear | Void black, neon accent lines | Developer tools, frameworks |

## Prompt Structure

```
0–2s  [STARTING STATE]    Particles form initial shape
2–5s  [SHAPE 1 → SHAPE 2] First feature transition
5–9s  [SHAPE 2 → SHAPE 3] Core value transformation
9–12s [SHAPE 3 → PRE-LOGO] Logo hint emerges
12–13s [COLLAPSE]          Silent beat, inward collapse
13–15s [LOGO]              Brand reveal
```

## Dreamina CLI Integration

After generating the prompt, the skill checks if [Dreamina CLI](https://jimeng.jianying.com/cli) is installed and offers to:

- Install it if missing: `curl -fsSL https://jimeng.jianying.com/cli | bash`
- Generate the video directly using the prompt

## File Structure

```
seedance-prompt/
├── SKILL.md                      # Main skill definition
├── README.md                     # This file
└── references/
    └── prompt-system.md          # Prompt system: aesthetic matrix + rules + template
```

## License

MIT
