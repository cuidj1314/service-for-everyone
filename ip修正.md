```bash
@echo off
cls
color 0A

@echo off
: acp
echo.
echo ===ipアドレス変更===
echo.
echo ******************************
echo 1:外部インターネットipアドレス（172.16.73.XXX）
echo.
echo ******************************
echo 2:内部インターネットipアドレス（192.xx.xx.xx）
echo.
echo ******************************
echo.
echo.
set/p sel=下記の修正方式を選択してください：
if "%sel%"=="1" goto gaibu
if "%sel%"=="2" goto naibu
echo 上記の選択肢を選択してください。
goto ning

:gaibu
echo 修正中......
netsh interface ip set address name="イーサネット" source=static addr=172.16.73.xxx mask=255.255.255.x gateway=xx.xx.xx.xx gwmetric=1
netsh interface ip set dns name="イーサネット" source=static addr=xxx.xx.x.3
netsh interface ip add dns name="イーサネット" addr=xxx.xx.x.13 index=2 
ipconfig /flushdns
ipconfig /all
echo 修正完了しました！
goto end

:naibu
echo 修正中......
netsh interface ip set address name="イーサネット" source=static addr=172.16.73.xxx mask=255.255.255.x gateway=xx.xx.xx.xx gwmetric=1
netsh interface ip set dns name="イーサネット" source=static addr=xxx.xx.x.3
netsh interface ip add dns name="イーサネット" addr=xxx.xx.x.13 index=2 
ipconfig /flushdns
ipconfig /all
echo 修正完了しました！
goto end


:ning
echo 再度入力してください。
pause
cls 
goto acp

:end
pause
```

