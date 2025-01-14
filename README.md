# RLJP-CLOUD-FIREBASE

CloudRun のコンテナの CDN として使うやつ
https://firebase.google.com/docs/hosting/full-config?hl=ja#rewrites

## 設定

```json
{
  "hosting": {
    "rewrites": [
      {
        "source": "/**",
        "run": {
          "serviceId": "aaaabbbcccc",
          "region": "asia-northeast1",
          "pinTag": true
        }
      }
    ]
  }
}
```

## 説明

- source: このパターンに一致するすべてのリクエストがリライトの対象になる
- serviceId: リダイレクト先の Cloud Run の ID
- region: Cloud Run がデプロイされているリージョン
- pinTag: 特定のバージョンのサービスをピン留めする

例：https://serviceTag---serviceId-an.a.run.app/

## Deploy

```
firebase deploy --only hosting
```

https://firebase.google.com/docs/hosting/cloud-run?hl=ja&authuser=0
