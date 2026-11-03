# voices/

按角色（speaker）分目录的声音参考样本。

```
voices/
  <speaker>/
    README.md                       角色卡
    <speaker>_<source>_ref_*.wav    参考音频
    <speaker>_<source>_ref_*.md     同名元数据
```

## 元数据 `.md` 必填字段

| 字段 | 说明 |
|---|---|
| id | 与文件主干同名，全局唯一 |
| 文件 | 实际文件名 |
| 角色 | 角色名，与目录 README 一致 |
| 语言 | BCP-47，如 `zh-CN` |
| 时长 | 秒，两位小数 |
| 采样率 | Hz |
| 声道 / 位深 | 如 `1（mono）` / `16 bit PCM` |
| 大小 | 字节数 |
| sha256 | 完整哈希，用于校验 |
| 逐字稿 | **与音频逐字对应**，TTS 会把它当先验 |
| 推荐参数 | 针对该样本验证过的参数 |
| 直链 | raw 与 jsDelivr 两条 |
| 调用示例 | 可直接复制的请求体 |

## 校验

```bash
sha256sum voices/<speaker>/*.wav     # 与 .md 里记录的 sha256 对比
```
