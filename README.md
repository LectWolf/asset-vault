# asset-vault

通用资源仓库：存放需要稳定外部直链的二进制资产（音频参考样本、图片等）。
不参与任何应用的构建，只用 git 做版本化存储，用 raw / jsDelivr 当 CDN。

## 目录

```
voices/                 音频参考样本（声音克隆、TTS 参考音）
  <speaker>/            按角色分目录，一个角色一个 README + 若干资产
```

## 命名规范

`<speaker>_<source>_<role>_<duration>_<sr>_<channels>.<ext>`

| 段 | 含义 | 例 |
|---|---|---|
| speaker | 角色 slug，小写 ASCII | `jianran` |
| source | 采集批次 / 出处 | `diana7` |
| role | `ref` 参考音频、`sample` 试听、`raw` 未处理原始 | `ref` |
| duration | 时长（秒），小写 s 连接两位小数 | `6s01` |
| sr | 采样率 | `48k` |
| channels | `mono` / `stereo` | `mono` |

示例：`voices/jianran/jianran_diana7_ref_6s01_48k_mono.wav`

每个音频必须配一份**同名 `.md`**，写清逐字稿、音频参数、sha256、来源与授权；
新增资产后同步更新 [CATALOG.md](CATALOG.md)。

## 直链

GitHub raw：

```
https://raw.githubusercontent.com/LectWolf/asset-vault/main/voices/<speaker>/<file>
```

jsDelivr（国内访问更快，推荐给服务端 / TTS 用）：

```
https://cdn.jsdelivr.net/gh/LectWolf/asset-vault@main/voices/<speaker>/<file>
```

jsDelivr 有缓存，发布后要立刻生效可以打一次刷新：

```
https://purge.jsdelivr.net/gh/LectWolf/asset-vault@main/voices/<speaker>/<file>
```

## 新增资产流程

1. 按命名规范改名，放进 `voices/<speaker>/`
2. 补同名 `.md`，字段见 [voices/README.md](voices/README.md)
3. 在 [CATALOG.md](CATALOG.md) 增加一行
4. `git add . && git commit -m "add: <id>" && git push`

## 授权

见 [NOTICE.md](NOTICE.md)。仓库内音频仅用于个人测试与研究，版权归原权利人所有。
