# Easy Stream English

一款基于 [Rime 输入法](https://rime.im/) 的英文输入方案，魔改自 [Easy English](https://github.com/BlindingDark/rime-easy-en)，由于Easy English不支持用户自定义词库，在保留原有输入体验的基础上，新增对用户自定义词库的支持，并参考雾凇拼音的皮肤对界面进行了美化。

支持**自动补全**与**自动空格**，词库包含约 25 万常用英文词汇和 2.7 万常用英文名，其中针对《纸牌屋》(House of Cards) 人物英文名做了特别优化。

## 特性

- **自动补全**：输入时智能联想补全单词
- **自动空格**：连续输入多个单词时，选词后自动插入空格
- **海量词库**：25 万常用词 + 2.7 万英文名
- **纸牌屋优化**：Frank、Claire、Underwood 等剧中人物名优先联想
- **自定义词库**：支持在 `user_dicts/` 目录下添加个人词库
- **美化皮肤**：基于 [雾凇拼音](https://github.com/iDvel/rime-ice) 的 `purity_of_form_custom` 配色

## 安装

### 前置要求

1. 安装 [Rime 输入法](https://rime.im/)
   - **Windows**：小狼毫 (Weasel)
   - **macOS**：鼠须管 (Squirrel)
   - **Linux**：ibus-rime 或 fcitx5-rime

### 安装步骤

1. 下载本仓库所有文件
2. 切换到Rime输入法，在右下角托盘区右键，点击「用户文件夹」
3. 将下载的文件**覆盖**到用户文件夹中
4. 在右下角托盘区右键「重新部署」




## 自定义词库

项目支持多词库合并，可在 `user_dicts/` 目录下添加或编辑词库：

| 文件 | 说明 |
|------|------|
| `01_custom.dict.yaml` | 个人自定义词汇（如 ChatGPT、GitHub 等） |
| `02_en_names.dict.yaml` | 英文人名词库（2.7 万条） |

词库格式示例：

```yaml
---
name: 01_custom
version: "2026-02-09"
sort: by_weight
...

ChatGPT	chatgpt
OpenAI	openai
```


## 项目结构

```
├── easy_en.schema.yaml      # 输入方案
├── easy_en.dict.yaml        # 主词库（25 万词）
├── easy_en.main.dict.yaml   # 词库合并入口词库配置
├── easy_en.custom.yaml      # 方案自定义
├── default.custom.yaml      # 默认方案列表
├── weasel.custom.yaml       # 小狼毫（Windows）皮肤
├── weasel.yaml              # 小狼毫配置
├── squirrel.yaml            # 鼠须管（macOS）皮肤
├── user_dicts/              # 自定义词库目录
│   ├── 01_custom.dict.yaml
│   └── 02_en_names.dict.yaml
└── lua/
    └── easy_en.lua          # Lua 扩展脚本
```

## 致谢

- [Easy English](https://github.com/BlindingDark/rime-easy-en) - 原项目
- [Rime](https://rime.im/) - 中州韵输入法引擎
- [雾凇拼音](https://github.com/iDvel/rime-ice) - 皮肤参考
- [ECDICT](https://github.com/skywind3000/ECDICT) - 词库数据来源

- [funNLP](https://github.com/fighting41love/funNLP/tree/master/data/%E4%B8%AD%E8%8B%B1%E6%97%A5%E6%96%87%E5%90%8D%E5%AD%97%E5%BA%93/English_Names_Corpus) - 2.7万英文名数据来源



## 许可证

[LGPL-3.0](LICENSE)
