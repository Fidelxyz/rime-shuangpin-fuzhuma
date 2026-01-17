# Copilot Instructions - Rime 墨奇万象配置（精简版）

## 项目概述
这是一个精简版的 **Rime 输入法引擎**配置仓库，仅包含 `moqi_wan_flypy`（墨奇万象+小鹤双拼·鹤形）方案。

## 核心架构

### 方案文件
- `moqi_wan_flypy.schema.yaml` - 唯一的输入方案，小鹤双拼+鹤形辅助码
- `moqi.yaml` - 公共配置（通过 `__include` 引用）
- `moqi_speller.yaml` - 双拼编码转换规则

### 依赖方案
- `radical_flypy` - 部件组字（az引导）
- `stroke` - 笔画输入（ab引导，Rime内置）
- `easy_en` - 英文输入（aw引导）

### 词库系统
- **主词典**：`moqi_wan.extended.dict.yaml` 引用 `cn_dicts/` 下的全拼词库
- 格式：`字<TAB>拼音<TAB>权重`（全拼格式，由 speller 转换为双拼）
- `cn_dicts_cell/` - 细胞词库（领域词库）
- `cn_dicts_common/` - 通用词库

### Lua 扩展（lua/ 目录）
- `calculator.lua` - 计算器（V模式）
- `date_translator.lua` - 日期时间
- `pro_comment_format.lua` - 辅助码注释显示
- `sbxlm/key_binder.lua` - 正则按键绑定

### OpenCC 转换（opencc/ 目录）
- `moqi_chaifen.json` - 拆分字形显示
- `chinese_english.json` - 汉英互译
- `martian.json` - 火星文

## 重要引导前缀
| 前缀 | 功能 |
|------|------|
| `ab` | 笔画输入（hspnz=横竖撇捺折） |
| `az` | 部件组字 |
| `aw` | 英文输入 |
| `ac` | 自造词 |
| `V` | 计算器 |

## 测试方法
修改后需在 Rime 输入法中"重新部署"验证功能。
