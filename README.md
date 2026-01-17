# 说明（精简版）

这是一个精简版的 Rime 输入法配置，仅包含 **墨奇万象+小鹤双拼·鹤形** 方案。

墨奇万象通过拼写运算实现小鹤双拼+鹤形辅助码的组合。词库使用基于[雾凇拼音](https://github.com/iDvel/rime-ice)的[白霜词库](https://github.com/gaboolic/rime-frost)，支持4万字。

## 主要特性

- **唯一方案**：`moqi_wan_flypy` - 墨奇万象+小鹤双拼·鹤形
- **辅助输入**：
  - `ab` 引导笔画输入（hspnz=横竖撇捺折）
  - `az` 引导部件组字
  - `aw` 引导英文输入
  - `ac` 引导自造词
- **词库**：`moqi_wan.extended.dict.yaml` 包含基础词库、扩展词库和细胞词库
- **快捷功能**：
  - 超级简拼：1-3码时按 Tab/`/`/`.` 自动上屏对应字词
  - 计算器：V 模式
  - 日期时间：date/time/week/datetime/timestamp
  - 大写数字：R 开头
  - Unicode：U 开头
  - 符号输入：`/fh`
- **显示控制**：
  - `Ctrl+P` 切换拆分字形显示
  - `Ctrl+L` 切换完整拆分显示
  - `Ctrl+E` 切换汉英互译

## 配置说明

- 词库文件：`moqi_wan.extended.dict.yaml`
- 默认关闭用户词库（固定词频），可在 `moqi_wan_flypy.schema.yaml` 中设置 `enable_user_dict: true` 开启
- 自定义词：编辑 `cn_dicts_common/user.dict.yaml` 或使用 `ac` 引导造词
- 辅助码显示：通过 `translator/spelling_hints` 调整

## 安装方法

下载本仓库的压缩包 Code - Download ZIP，解压到对应平台的 Rime 配置目录：

- **Windows**：`%APPDATA%\Rime`
- **macOS**：
  - [鼠须管](https://github.com/rime/squirrel)：`~/Library/Rime`
  - [fcitx5-mac](https://github.com/fcitx-contrib/fcitx5-macos)：`~/.local/share/fcitx5/rime`
- **Linux**：
  - [fcitx5-rime](https://github.com/fcitx/fcitx5-rime)：`~/.local/share/fcitx5/rime`
  - fcitx5 flatpak 版：`~/.var/app/org.fcitx.Fcitx5/data/fcitx5/rime`
  - [ibus-rime](https://github.com/rime/ibus-rime)：`~/.config/ibus/rime`
- **Android**：
  - [fcitx5-android](https://github.com/fcitx5-android/fcitx5-android)：`/Android/data/org.fcitx.fcitx5.android/files/data/rime`
  - [同文](https://github.com/osfans/trime)：`/rime`
- **iOS**：[仓输入法](https://github.com/imfuxiao/Hamster)

使用 git 管理（推荐）：
```bash
# macOS 示例
cd ~/Library
git clone --depth 1 https://github.com/gaboolic/rime-shuangpin-fuzhuma Rime
# 更新时
cd ~/Library/Rime && git pull
```

安装后请在输入法中执行"重新部署"。

## 输入演示

## 输入演示

基本输入、辅助码、笔画部件等功能演示（图片路径已精简，如需查看请参考原仓库）。

## 高级功能

### 超级简拼
1-3码时按 Tab/`/`/`.` 自动上屏对应字词，不与空格上屏单字冲突。

### 飞键（可选）
在 `moqi_wan_flypy.schema.yaml` 的 `speller/algebra` 中添加：
```yaml
- derive/^([yh])j/$1q/    # yj hj 可打 yq hq
- derive/^qx/qw/          # qx 可打 qw
```

### 模糊音（可选）
使用 `derive` 规则实现平翘舌音互转、前后鼻音互转等。

## 鸣谢

- [雾凇拼音](https://github.com/iDvel/rime-ice) - 配置参考
- [白霜词库](https://github.com/gaboolic/rime-frost) - 词库来源
- [小鹤双拼](https://gitee.com/functoreality/rime-flypy-zrmfast) - 配置参考
- [魔然](https://github.com/ksqsf/rime-moran) - 配置参考
- [rime-radical-pinyin](https://github.com/mirtlecn/rime-radical-pinyin) - 部件组字
- [声笔输入法](https://github.com/sbsrf/sbsrf) - Lua 脚本参考

---

**注意**：这是精简版配置，仅保留核心功能。完整版请访问原仓库其他分支。
