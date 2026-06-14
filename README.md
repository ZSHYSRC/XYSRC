巡隐WEBSHELL扫描软件  <br>
windows 64位选择xy-windows-amd64.zip  <br>
linux 64位选择 xy-linux-amd64  <br>
mac 64位选择 xy-darwin-amd64  <br>

使用方法: webshell-detector [选项] <扫描路径>  <br>

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


说明<br>
1）windows版采用了加载外部数据库db，因此需要将db目录与主程序放在同一目录中<br>
2）linux版和mac 采用了嵌入数据库db，直接运行主程序即可；由于是嵌入数据库db，因此执行时会产生一个临时文件，执行完成后会自动将生成的临时文件删除，因此如果安装了杀毒软件可能会产生安全告警。
