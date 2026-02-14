## 全ての画面の透明度を変更する場合は、settings.json の profiles の defaults に追加すれば OK です。

```json
{
  "profiles": {
    "defaults": {
      "opacity": 70,
      "useAcrylic": false
    }
  }
}
```

opacity は透明度の設定で「0」にすると完全に透明になります。
