## ファイル作成目的

デペンデンシーボットが出たときにの解決手順のメモ

## 場所

https://github.com/mari2t/MySchedule/security/dependabot

#### ![Dependabot_alerts_20240910.png](/Github/Dependabot_alerts/Dependabot_alerts_20240910.png "Dependabot_alerts_20240910.png")

## やったこと

1. 最新バージョンに更新  
   npm update braces vite
2. 依存関係確認  
   npm audit
3. 互換性を壊さない範囲で脆弱性のあるパッケージを安全なバージョンに更新  
   npm audit fix
4. 下記の結果を確認。解決。  
   found 0 vulnerabilities
