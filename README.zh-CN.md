<div align="right">

[English](README.md) · **[简体中文](README.zh-CN.md)**

</div>

# ai-studio-yangzi

11 个 AI 影视制作技能，加项目模板和跨平台安装脚本。

<sub>Skills · 项目模板 · 八阶段管线</sub>

---

## 这是什么

给本地 AI agent 用的影视制作技能包。每个技能对应制作中的一个阶段，可以单用，也可以串起来。

```
skills/            11 个技能，各管一个阶段
project-template/  可用的项目骨架
scripts/           安装、升级、知识库配置
课程文档/ 课程图片/  课程材料
```

## 八个阶段

```
00 调研 → 01 故事 → 02 剧本 → 03 资产
→ 04 提示词 → 05 分镜 → 06 视频 → 07 合成
```

每个阶段读上一阶段的已确认产物，写出一份带版本号的产物。规则是：一个阶段**只读已确认的当前版本**——不读更早的草稿，也不读隔壁阶段的临时笔记。

这一条规则才是让管线可重启的原因。如果 05 出了问题，退回最后一个确认过的 04 重跑即可。

## 项目模板

`project-template/` 是每个项目的起始骨架：

```
00_research/   01_story/   02_script/   03_assets/
04_prompts/    05_storyboard/   06_video/   07_assembly/
```

空是刻意的。结构承载约定，内容按项目来。

## 脚本

| 脚本 | 用途 |
|---|---|
| `新建AI影视项目.ps1` | 从模板生成新项目 |
| `升级旧电影工程规则.ps1` | 把旧项目升到当前规则 |
| `安装课程包.ps1` | 安装课程包 |
| `install_course.py` | 同上，跨平台 |
| `配置本地知识库.ps1` | 让 agent 指向本地知识库 |
| `更新本地知识库.ps1` | 刷新知识库 |

升级脚本存在的原因是规则会变。与其让旧项目悄悄过时，不如迁移过去并报告改了什么。

## 范围说明

技能假定模型由你提供，这里不调任何托管 API。研究、剧本、分镜阶段处理的是文本；资产和视频阶段交给已配置好的生成器。

八个阶段的实际应用、带真实影片产物的版本，见 [ai-film-production](https://github.com/YGtemple/ai-film-production) 和 [ai-drama-master-suite](https://github.com/YGtemple/ai-drama-master-suite)。

## 安装

```powershell
.\scripts\安装课程包.ps1
```

或使用 Python：

```bash
python scripts/install_course.py
```

上手说明见 `00-开始使用.md`。

## 许可证

MIT
