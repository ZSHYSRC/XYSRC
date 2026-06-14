# 巡隐WEBSHELL扫描软件<br>
windows 64位选择xy-windows-amd64.zip<br>
linux 64位选择 xy-linux-amd64<br>
mac 64位选择 xy-darwin-amd64<br>

# 使用方法: webshell-detector [选项] <扫描路径>  <br>

选项:  <br>
  -o, --output FILE       将报告输出到文件  <br>
  -v, --verbose           详细输出模式  <br>
  -h, --help              显示此帮助信息  <br>
  --generic-rules         启用通用规则检测  <br>
  --html-report           生成HTML报告  <br>
  --no-threat             输出无威胁报告到单独文件  <br>

示例:  <br>
  ./xy-linux-amd64 -v --show-score --html-report -o report.txt --no-threat /var/www  <br>
  xy-amd64.exe -v --show-score --html-report -o report.txt --no-threat D:\webshell  <br>

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
