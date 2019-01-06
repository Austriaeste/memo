# memo

excel とかで取得することも考えたが、動線を切り替える事を考慮してこちらを選んだ
powershell を立ち上げて下記のコマンドを入力する
紙copi にフォーマットを作成しておく

# 当日日付を取得
Get-Date -UFormat "(%m/%d)"

# 前日日付を取得
[DateTime]::Today.AddDays(-1).ToString('MM/dd')
---

DateTime を[]で囲うとフォントが大きくなるのを何とかしたい。。。

---
#　もしくは cmd で下記をベタ打ち

@echo off
::今日の日付を取得
set yy=%date:~0,4%
set mm=%date:~5,2%
set dd=%date:~8,2%
echo 今日は、%yy% (%mm%/%dd%)です。

::1日前の日付を計算する
set /a dd=%dd%-1
set dd=00%dd%
set dd=%dd:~-2%
set /a ymod=%yy% %% 4
if %dd%==00 (
if %mm%==01 (set mm=12&& set dd=31&& set /a yy=%yy%-1)
if %mm%==02 (set mm=01&& set dd=31)
if %mm%==03 (set mm=02&& set dd=28&& if %ymod%==0 (set dd=29))
if %mm%==04 (set mm=03&& set dd=31)
if %mm%==05 (set mm=04&& set dd=30)
if %mm%==06 (set mm=05&& set dd=31)
if %mm%==07 (set mm=06&& set dd=30)
if %mm%==08 (set mm=07&& set dd=31)
if %mm%==09 (set mm=08&& set dd=31)
if %mm%==10 (set mm=09&& set dd=30)
if %mm%==11 (set mm=10&& set dd=31)
if %mm%==12 (set mm=11&& set dd=30)
)
echo 昨日は、%yy% (%mm%/%dd%)です。

echo.
pause
