# ShanHuPV

ShanHuPV 是一款完全模拟浏览器行为的流量测试工具，旨在为你的网站增加 IP、浏览量和点击量。它采用 Chrome 103.0.5060.53 驱动模拟真人访问，支持批量同时运行和自定义 IP 代理池。

## 功能

- **模拟真人访问**：通过模拟浏览器行为，每次访问使用不同的设备ua和ip，增加网站的真实访问量。
- **自定义代理池**：支持使用 HTTP 或 SOCKS5 代理来访问网站，保护隐私并避免被封禁。
- **线程与访问控制**：支持自定义线程数、访问时长、网页刷新频率和点击链接次数。
- **显示浏览器窗口**：可选择显示可视化执行，方便调试和监控。

## 安装依赖

在使用之前，请确保已经安装以下 Python 依赖：

pip install PyQt5
pip install colorama
pip install psutil
pip install selenium
使用方法
usage: shanhupv.py [-h] [-t T] [-s S] [-r R] [-a A] -u U [--eye] {http,socks5}
参数说明：

{http,socks5}: 代理类型 (支持 http 或 socks5)
optional arguments:

-h, --help: 显示帮助信息并退出
-t T: 线程数 (1-999)
-s S: 访问时间 (1-999) 秒
-r R: 每个网页刷新次数 (0-999)
-a A: 每个网页点击链接数 (0-999)
-u U: 链接 URL，必须指定，并且后面跟上代理类型
--eye: 显示浏览器窗口可视化执行
示例：
python shanhupv.py -t 10 -s 60 -r 5 -a 3 -u http://example.com http
此命令会使用http代理文件，启动 10 个线程，同时执行任务，访问 http://example.com，每次访问 60 秒，刷新网页 5 次，随机点击网站内 3 个链接。

其他：
附带图形界面gui：shanhupvgui.py，无需输入任何指令
