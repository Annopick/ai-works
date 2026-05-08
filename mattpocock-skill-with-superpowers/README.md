# 将Matt Pocock工程技能与superpowers融合使用的方案

## 项目来源

- [Matt Pocock技能](https://github.com/mattpocock/skills/tree/main/skills/engineering)
- [Superpowers](https://github.com/obra/superpowers)

## 使用思路

- 将matt-pocock技能、Superpowers技能安装完成
- Superpowers技能机制会自动装载使用
- 将归纳总结的matt-pocock技能使用指引加入Claude Code全局、项目级规则文档中

## Claude Code操作

- 项目级：在项目根目录里添加[AGENTS.md](./AGENTS.md)文件，并在[CLAUDE.md](CLAUDE.md)文件首行添加`@AGENTS.md`引用
- 全局级：在`~/.claude/`目录下添加[AGENTS.md](./AGENTS.md)文件和[CLAUDE.md](CLAUDE.md)文件首行添加`@AGENTS.md`引用
