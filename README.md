<div align="right">

**[English](README.md)** · [简体中文](README.zh-CN.md)

</div>

# ai-studio-yangzi

Eleven production skills for AI film-making, plus project templates and cross-platform install scripts.

<sub>Skills · project template · 8-stage pipeline</sub>

---

## What this is

A skill bundle for a local AI agent doing film work. Each skill covers one stage of production and can be used alone or chained.

```
skills/             eleven skills, each one stage of the pipeline
project-template/   a working project skeleton
scripts/            install, upgrade, and knowledge-base setup
课程文档/ 课程图片/   course material (Chinese)
```

## The eight stages

```
00 research → 01 story → 02 script → 03 assets
→ 04 prompts → 05 storyboard → 06 video → 07 assembly
```

Each stage reads the previous stage's confirmed output and writes one versioned artifact. The rule is that a stage reads only the **confirmed current version** — no reading an earlier draft, no reading a sibling's working notes.

That single rule is what makes the pipeline restartable. If stage 05 goes wrong, reset to the last confirmed `04` and run again.

## The project template

`project-template/` is the directory skeleton every project starts from:

```
00_research/   01_story/   02_script/   03_assets/
04_prompts/    05_storyboard/   06_video/   07_assembly/
```

Empty on purpose. The structure carries the convention; the content is per project.

## Scripts

| Script | Purpose |
|---|---|
| `新建AI影视项目.ps1` | scaffold a new project from the template |
| `升级旧电影工程规则.ps1` | bring an older project up to the current rule set |
| `安装课程包.ps1` | install the course bundle |
| `install_course.py` | same, cross-platform |
| `配置本地知识库.ps1` | point the agent at a local knowledge base |
| `更新本地知识库.ps1` | refresh it |

The upgrade script exists because the rules change. Rather than leaving old projects silently out of date, it migrates them and reports what changed.

## Notes on scope

The skills assume you supply the models; nothing here calls a hosted API. Research, script and storyboard work is text. Asset and video stages hand off to whatever generator you have configured.

A worked example of all eight stages in practice — with a real film's artifacts — is in [ai-film-production](https://github.com/YGtemple/ai-film-production) and [ai-drama-master-suite](https://github.com/YGtemple/ai-drama-master-suite).

## Install

```powershell
.\scripts\安装课程包.ps1
```

Or with Python:

```bash
python scripts/install_course.py
```

Getting started is documented in `00-开始使用.md`.

## License

MIT
