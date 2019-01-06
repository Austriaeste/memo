# memo

excel とかで取得することも考えたが、動線を切り替える事を考慮してこちらを選んだ
powershell を立ち上げて下記のコマンドを入力する

# 当日日付を取得
Get-Date -UFormat "(%m/%d)"

# 前日日付を取得
 [DateTime]::Today.AddDays(-1).ToString('MM/dd')
[DateTime]::Today.AddDays(-1).ToString('MM/dd')
---

DateTime を[]で囲うとフォントが大きくなるのを何とかしたい。。。
