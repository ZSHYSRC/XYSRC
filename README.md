# 巡隐WEBSHELL扫描软件<br>
windows 64位选择xy-Windows.zip<br>
linux 64位选择 xy-Linux.zip<br>
mac 64位选择 xy-macOS.zip<br>

# 使用方法:./xy-linux-amd64 [选项] <扫描路径>  <br>

选项:  <br>
  -h                          显示此帮助信息<br>
  -v                          详细输出模式<br>
  -r                           递归扫描子目录（默认启用，使用 -r=false 禁用）<br>
  -d FILE                   指定数据库文件<br>
  -o DIR                    指定输出目录(默认: 程序所在目录)<br>
  -name NAME         指定输出文件名(同时作用于--txt/--html/--unthreat)<br>

示例:  <br>
  国际惯例使用前先赋权，例如 chmod 777 xy-linux-amd64<br>
  Linux版使用命令示例：<br>
  ./xy-linux-amd64 -v /var/www                    (生成详细结果的txt报告)<br>
  ./xy-linux-amd64 --html --txt /var/www     (生成HTML报告和txt报告)<br>


  Windows命令行版使用命令示例：<br>
  xy-amd64.exe D:\webshell		       (生成report.txt、report.html)<br>
  xy-amd64.exe -v D:\webshell                       (生成详细结果的report.txt、report.html)<br>

## windows扫描示意图
<p align="center">
  <img src="windows%E6%89%AB%E6%8F%8F%E7%A4%BA%E6%84%8F%E5%9B%BE1.png" width="700" alt="windows拓扑示意图1">
  <br><br>
  <img src="windows%E6%89%AB%E6%8F%8F%E7%A4%BA%E6%84%8F%E5%9B%BE2.png" width="700" alt="windows拓扑示意图2">
  <br><br>
  <img src="windows%E6%89%AB%E6%8F%8F%E7%A4%BA%E6%84%8F%E5%9B%BE3.png" width="700" alt="windows拓扑示意图3">
</p>

---

## linux扫描示意图
<p align="center">
  <img src="linux%E6%89%AB%E6%8F%8F%E7%A4%BA%E6%84%8F%E5%9B%BE1.png" width="700" alt="linux拓扑示意图1">
  <br><br>
  <img src="linux%E6%89%AB%E6%8F%8F%E7%A4%BA%E6%84%8F%E5%9B%BE2.png" width="700" alt="linux拓扑示意图2">
</p>

# 说明<br>
1）windows版采用了加载外部数据库db，因此需要将db目录与主程序放在同一目录中<br>
2）linux版和mac 采用了嵌入数据库db，直接运行主程序即可；由于是嵌入数据库db，因此执行时会产生临时db文件，执行完成后会自动将生成的临时文件删除，因此如果安装了杀毒软件可能会产生安全告警。
