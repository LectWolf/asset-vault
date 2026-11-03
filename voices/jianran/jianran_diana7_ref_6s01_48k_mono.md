# jianran_diana7_ref

| 字段 | 值 |
|---|---|
| id | `jianran_diana7_ref` |
| 文件 | `jianran_diana7_ref_6s01_48k_mono.wav` |
| 角色 | 嘉然 Diana（`jianran`） |
| 语言 | zh-CN |
| 时长 | 6.01 s |
| 采样率 | 48000 Hz |
| 声道 | 1（mono） |
| 位深 | 16 bit PCM |
| 大小 | 577,398 字节 |
| sha256 | `acd1195b2f7b989d373c419e2debed65221a8be83c7cd42844c3ab711080c731` |
| 来源 | 公开渠道语音片段（原文件名 `嘉然_Diana_7_真实参考音频.wav`） |
| 授权 | 仅个人测试用，版权归原权利人，见 [NOTICE.md](../../NOTICE.md) |

## 逐字稿

> 对，没错，刚刚就是嘉然激情推荐歌曲，因为真的很可爱，是近期听到的比较可爱的一首音乐。

必须与音频**逐字对应**，作为 VoxCPM2 的 `prompt_text_value`；写错字会明显拉低相似度。

## 推荐参数（VoxCPM2）

| 参数 | 值 |
|---|---|
| `use_prompt_text` | `true` |
| `prompt_text_value` | 上面的逐字稿 |
| `cfg_value` | `2.0` |
| `dit_steps` | `10` |
| `do_normalize` | `true` |
| `denoise` | `false` |

## 直链

- raw：`https://raw.githubusercontent.com/LectWolf/asset-vault/main/voices/jianran/jianran_diana7_ref_6s01_48k_mono.wav`
- jsDelivr：`https://cdn.jsdelivr.net/gh/LectWolf/asset-vault@main/voices/jianran/jianran_diana7_ref_6s01_48k_mono.wav`

## 调用示例

直接给 URL，服务端会自己下载（`path` 必须是 URL，只给 `url` 字段会报错）：

```json
{
  "data": [
    "要合成的文本",
    "",
    {
      "path": "https://cdn.jsdelivr.net/gh/LectWolf/asset-vault@main/voices/jianran/jianran_diana7_ref_6s01_48k_mono.wav",
      "url": "https://cdn.jsdelivr.net/gh/LectWolf/asset-vault@main/voices/jianran/jianran_diana7_ref_6s01_48k_mono.wav",
      "orig_name": "jianran_diana7_ref_6s01_48k_mono.wav",
      "meta": {"_type": "gradio.FileData"}
    },
    true,
    "对，没错，刚刚就是嘉然激情推荐歌曲，因为真的很可爱，是近期听到的比较可爱的一首音乐。",
    2.0, true, false, 10, "user"
  ]
}
```

对应 `POST https://voxcpm.modelbest.cn/gradio_api/call/generate`。
