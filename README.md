# サボろうとするとメンターが現れる Chrome 拡張機能

## デモ

![https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F305510%2Ff44f217a-8c49-da04-0f45-508405e0cb51.gif?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&w=1400&fit=max&s=5d8b68e9f8d5fd043faa2b0218b498dc](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F305510%2Ff44f217a-8c49-da04-0f45-508405e0cb51.gif?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&w=1400&fit=max&s=5d8b68e9f8d5fd043faa2b0218b498dc)

## 使い方

### Chromeへの追加

1.Chrome の「設定」→「拡張機能」
2.デベロッパーモードをオン
3.「パッケージ化されていない拡張機能を読み込む」でディレクトリを選択
4.スイッチを有効にする

### ブロックするサイトの変更

`manifest.json`の`content_scripts -> matches`から変更できます

```json:manifest.json
  "content_scripts": [
        {
            "matches": ["https://twitter.com/*",
                        "https://www.youtube.com/*",
                        "https://www.yahoo.co.jp/*"],
            "exclude_globs": ["https://www.youtube.com/watch?v=IZmYn4ObRJc"],
            "match_about_blank": true,
            "js": ["script.js"],
            "run_at": "document_start"
        }
    ]
```

## 製作者情報

[サボろうとするとメンターが現れる Chrome 拡張機能 - Qiita](https://qiita.com/watatakahashi/items/97243299abd9354f3614)

[https://twitter.com/takawata0](https://twitter.com/takawata0)
