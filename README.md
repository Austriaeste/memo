# memo

powershell を立ち上げて下記のコマンドを入力する
===================================
# 当日日付を取得
Get-Date -UFormat "(%m/%d)"

# 前日日付を取得
[DateTime]::Today.AddDays(-1).ToString('MM/dd')
===================================
