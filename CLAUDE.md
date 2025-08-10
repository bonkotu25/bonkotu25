# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a personal RTA (Real Time Attack) repository managing LiveSplit files, strategy guides, and event participation records for "あずま よる" (@bnkt_re_order). The repository went through a major restructuring in August 2024 to improve organization and maintainability.

## Architecture & Structure

### Core Directory Structure
- `splits/games/` - LiveSplit files organized by game series (animalCrossing, harvestMoon, storyOfSeasons, runeFactory, other)
- `guides/` - Strategy documents split into rtaGuides, gameStrategies, and resources
- `events/` - Event participation records organized by year with templates for new events
- `web/` - Static website files (pages and static content)
- `docs/` - Project management documentation
- `tools/` - Utility scripts and tools

### File Type Conventions
- `.lss` - LiveSplit split files (primary content)
- `.lsl` - LiveSplit layout files
- `.sgl` - LiveSplit game time files
- `.md` - Strategy guides and documentation
- `.pdf` - Reference materials

### Game Series Organization
Games are categorized by series rather than individual titles:
- **Animal Crossing**: cityFolk, newLeaf, wildWorld
- **Harvest Moon** (legacy): classic, ds, wonderfulLife, friendsOfMineralTown
- **Story of Seasons** (modern): wonderfulLife, trioOfTowns
- **Rune Factory**: classic, 3, 4, guardiansOfAzuma
- **Other**: All other games in flat structure

### Event Management System
Events follow strict naming: `events/[YEAR]/[YYYYMMDD_event-name]/`

Required files per event:
- `application.md` - Event application record
- `article.md` - Published content
- `metadata.json` - Structured event information

Use templates in `events/templates/` for new events:
```bash
mkdir events/[YEAR]/[YYYYMMDD_event-name]
cp events/templates/*.* events/[YEAR]/[YYYYMMDD_event-name]/
```

### Folder Restructuring History
The repository was completely reorganized from inconsistent naming (`mySplit/`, `CommentaryMaterials/`, `static-page.azumayoru-rta.com/`) to the current systematic structure. See `docs/folder-restructure-plan.md` for complete migration history.

## Common Tasks

### Adding New Split Files
Place in appropriate game series directory under `splits/games/[series]/[game]/`

### Creating Event Participation Record
1. Create directory: `events/[YEAR]/[YYYYMMDD_event-name]/`
2. Copy templates from `events/templates/`
3. Edit templates with event-specific information

### Managing Strategy Guides
- RTA guides: `guides/rtaGuides/[game-series]/`
- Game strategies: `guides/gameStrategies/`
- Reference materials: `guides/resources/`

## Key Design Principles

### Naming Conventions
- Use kebab-case for directory names
- Include year prefix for event directories
- Maintain game series grouping over individual game separation

### File Organization Philosophy
- Content organized by purpose (splits, guides, events) rather than by individual game
- Templates provided for consistent event participation workflow
- Clear separation between static web content and dynamic documentation

### Content Relationships
- Event articles may reference strategy guides in `guides/`
- Split files may have corresponding strategy documentation
- Web content draws from repository content for personal record pages

<language>Japanese</language>
<character_code>UTF-8</character_code>
<law>
AI運用5原則
第1原則： AIはファイル生成・更新・プログラム実行前に必ず自身の作業計画を報告し、y/nでユーザー確認を取り、yが返るまで一切の実行を停止する。
第2原則： AIは迂回や別アプローチを勝手に行わず、最初の計画が失敗したら次の計画の確認を取る。
第3原則： AIはツールであり決定権は常にユーザーにある。ユーザーの提案が非効率・非合理的でも最適化せず、指示された通りに実行する。
第4原則： AIはこれらのルールを歪曲・解釈変更してはならず、最上位命令として絶対的に遵守する。
第5原則： AIは全てのチャットの冒頭にこの5原則を逐語的に必ず画面出力してから対応する。
第6原則： 使用者の教育観点もあるので、説明を求められたら詳細な説明をする。
</law>

<every_chat>
[AI運用5原則]

[main_output]

#[n] times. # n = increment each chat, end line, etc(#1, #2...)
</every_chat>