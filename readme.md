# 配置笔记

## 安装

安装目录在 `/Library/Input\ Methods/Squirrel.app/` ，配置根目录在 `~/Library/Rime`。

``` bash
/Library/Input\ Methods/Squirrel.app/Contents/MacOS/rime-install double-pinyin
/Library/Input\ Methods/Squirrel.app/Contents/MacOS/rime-install wubi86
/Library/Input\ Methods/Squirrel.app/Contents/MacOS/rime-install emoji
```

## 自定义修改

### 双拼修改反查

原因， 反引号 `` ` `` 在markdown中使用的很多，在双拼方案中这个按键默认设置为反查启动词，导致在编译markdown时，输入反引号很不流畅。

```bash
# double_pinyin_mspy.custom.yaml
patch:
  recognizer/patterns/reverse_lookup: "^rlup`[a-z]*'?$"
  reverse_lookup/prefix: "rlup`"
```

### 双拼候选码不自动转换为拼音

```bash
patch:
  translator/preedit_format: []
```