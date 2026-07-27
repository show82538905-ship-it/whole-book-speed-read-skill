# 全书速读 Skill

一个面向 Codex 等支持 `SKILL.md` 的 AI Agent 的开源读书 Skill。它以用户提供的原书文件为第一事实来源，先核对版本、目录和完整性，再生成逐章、可核验、可续写的中文全书速读报告。

## 能做什么

- 处理 PDF、EPUB、DOCX、TXT、Markdown、扫描件或多卷书；
- 覆盖前言、正文、结语、后记和有实质内容的附录；
- 区分作者观点、他人观点、人物观点、事实、转述与外部分析；
- 自动适配非虚构、学术、商业管理、传记历史、小说与文学作品；
- 长报告按章节断点续写；
- 支持章节事实、故事、金句和后续问题；
- 文字报告完成后生成 2:3 中文全书信息图。

## 安装

仓库发布到 GitHub 后，在 Codex 中使用：

```text
$skill-installer install https://github.com/show82538905-ship-it/whole-book-speed-read-skill/tree/main/skills/speed-read-book
```

也可以手动把 `skills/speed-read-book` 复制到：

```text
~/.codex/skills/speed-read-book
```

安装完成后，新建一个 Codex 任务或重启客户端，让 Skill 列表重新加载。

## 使用示例

上传一本书后说：

```text
使用 $speed-read-book，完整速读我上传的书并生成中文报告。
```

也可以说：

```text
逐章拆解这本书，不要漏掉前言和结语；如果一次写不完就分段继续。
```

继续上次报告：

```text
继续
```

章节追问：

```text
第 6 章有哪些有趣的事实和可以核验的金句？
```

## 仓库结构

```text
whole-book-speed-read-skill/
├── LICENSE
├── README.md
└── skills/
    └── speed-read-book/
        ├── SKILL.md
        ├── agents/
        │   └── openai.yaml
        └── references/
            ├── continuation-and-follow-up.md
            ├── infographic-spec.md
            └── report-spec.md
```

## 数据与安全

这个仓库只包含 Markdown 和 YAML 指令，不包含脚本、依赖、后台进程、网络上传逻辑或凭证读取逻辑。Skill 会优先读取用户主动提供的书籍文件；只有用户仅给书名、明确要求补充资料，或必要信息无法从文件确认时，才会使用当前 AI 环境允许的公开检索能力，并要求标明外部来源。

生成内容应以摘要和分析为主，只保留少量必要短引文，不应被用于重建、传播或替代受版权保护的原书。

## 发布到 GitHub

1. 在 GitHub 新建公开仓库 `whole-book-speed-read-skill`。
2. 把本目录中的文件上传到仓库根目录。
3. 确认 GitHub 页面能看到 `README.md` 和 `skills/speed-read-book/SKILL.md`。
4. 复制上方安装命令，在另一台 Codex 设备完成安装测试。

## 许可证

本仓库中的 Skill 指令采用 [MIT License](LICENSE)。许可证不覆盖用户上传的书籍、第三方原文或由这些内容衍生且受其他权利约束的材料。
