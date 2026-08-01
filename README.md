# yimai-humanizer-v4

面向中文公众号、经营文案、报告、技术内容和故事文本的去 AI 味编辑 Skill。

它融合了三类方法：

- `no-ai-slop` 的最小有效修改、作者声音保护和事实安全原则
- `Master-humanizer-skill` 的两遍法、中文伪口语和模式优先策略
- 一麦经营智能体旧版 Humanizer 的中文场景规则、分层质检和停止条件

## 核心原则

1. 不编造数字、案例、地点、经历、引语、功能或用户反馈。
2. 人类草稿默认最小修改，纯 AI 初稿才使用两遍法重写。
3. 识别语言模式，不靠无限扩充禁词表。
4. 删除信息冗余，保留有声音、情绪或叙事作用的冗余。
5. 标点、成语、短句和口语词都不是绝对禁令，必须结合场景判断。

## 工作模式

- `detect`：只报告 AI 味模式及证据，不改写，不判断作者身份。
- `light-edit`：默认模式，最小修改并保留作者声音。
- `rewrite`：用于纯 AI 初稿或明确重写请求，使用两遍法。

## 安装到 Hermes Agent

```bash
hermes skills install https://raw.githubusercontent.com/a6828464/yimai-humanizer-v4/main/SKILL.md
```

也可以克隆后放入当前 Hermes Profile 的 `skills/` 目录。

## 文件结构

```text
yimai-humanizer-v4/
├── SKILL.md
└── references/
    ├── patterns.md
    ├── scenarios.md
    └── eval.md
```

## 使用示例

```text
使用 yimai-humanizer-v4 的 detect 模式检查下面这篇文章，只报告问题，不改写。
```

```text
使用 yimai-humanizer-v4 的 light-edit 模式润色下面这篇公众号文章，保留作者口吻。
```

```text
这是纯 AI 初稿，请使用 yimai-humanizer-v4 的 rewrite 模式重写，不要添加原文没有的事实。
```

## 致谢

本 Skill 吸收并重新整理了以下项目或规则体系的思想：

- [petergyang/no-ai-slop](https://github.com/petergyang/no-ai-slop)
- [masterball-w/Master-humanizer-skill](https://github.com/masterball-w/Master-humanizer-skill)
- Wikipedia WikiProject AI Cleanup 总结的 AI 写作特征

具体吸收和取舍见 `SKILL.md` 的“来源吸收说明”。

## License

MIT
