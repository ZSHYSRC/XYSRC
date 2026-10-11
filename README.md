v1.0.2版本后增加了.xhtml扩展名文件识别，并更新了规则库。<br>
此次更新并未更新整体代码结构、规则库结构，主要是通过删除规则库中冗余规则策略、增加规则库中识别webshell规则，实测扫描速度已能够达到355个文件/秒。<br>
误报率和漏报率已得到优化，在完成软件更新后，让多个AI生成 免杀的webshell，然后进行查杀，已都能够识别。也收集了一些常见的webshell进行测试，都能够识别。<br>

# 巡隐WEBSHELL扫描软件<br>
支持检测语言的脚本包括PHP、ASP、JSP、Others（包括Python/Perl/CGI/ColdFusion等）<br>
windows 64位选择xy-Windows.zip<br>
linux 64位选择 xy-Linux.zip<br>
mac 64位选择 xy-macOS.zip<br>

# 使用方法:./xy-linux-amd64 [选项] <扫描路径>  <br>

选项:  <br>
  -h                          &nbsp;&nbsp;&nbsp;&nbsp;显示此帮助信息<br>
  -v                          &nbsp;&nbsp;&nbsp;&nbsp;详细输出模式<br>
  -r                           &nbsp;&nbsp;&nbsp;&nbsp;递归扫描子目录（默认启用，使用 -r=false 禁用）<br>
  -d FILE                   &nbsp;&nbsp;&nbsp;&nbsp;指定数据库文件<br>
  -o DIR                    &nbsp;&nbsp;&nbsp;&nbsp;指定输出目录(默认: 程序所在目录)<br>
  -name NAME         &nbsp;&nbsp;&nbsp;&nbsp;指定输出文件名(同时作用于--txt/--html/--unthreat)<br>

示例:  <br>
  国际惯例使用前先赋权，例如 chmod 777 xy-linux-amd64<br>
  Linux版使用命令示例：<br>
  ./xy-linux-amd64 -v /var/www                    &nbsp;&nbsp;&nbsp;&nbsp;(生成详细结果的txt报告)<br>
  ./xy-linux-amd64 --html --txt /var/www     &nbsp;&nbsp;&nbsp;&nbsp;(生成HTML报告和txt报告)<br>


  Windows命令行版使用命令示例：<br>
  xy-amd64.exe D:\webshell		       &nbsp;&nbsp;&nbsp;&nbsp;(生成report.txt、report.html)<br>
  xy-amd64.exe -v D:\webshell                       &nbsp;&nbsp;&nbsp;&nbsp;(生成详细结果的report.txt、report.html)<br>

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
  <br><br>
  <img src="linux%E6%89%AB%E6%8F%8F%E7%A4%BA%E6%84%8F%E5%9B%BE3.png" width="700" alt="linux拓扑示意图3">
</p>

# 说明<br>
非Windows 版本采用了嵌入数据库db，没有需要维护的常驻服务，仅仅是独立的可执行文件。<br>

Windows 版本不再将数据库内嵌打包进 EXE。下载后会得到 EXE 程序与 db 文件夹，请将 EXE 和**整个 db 文件夹放在同一目录**运行，请勿删除 db 文件夹及内部数据库文件，删除后程序无法正常工作。
本次取消内嵌数据库，是为降低杀毒软件误报概率。**注：程序仍使用 garble 混淆编译，仍存在被杀毒软件误报的可能性。**

# 杀毒软件误报说明<br>
## 产生误报原因<br>
本项目使用两项技术：<br>
1. garble：Go语言代码混淆工具，会重写程序控制流、混淆符号，用于保护编译后的程序逻辑；<br>
2. 内嵌静态数据库db：将db数据库文件直接打包嵌入可执行二进制内。<br>

以上特征和杀毒静态扫描库中恶意样本特征相似，**可能会引发杀毒软件误报（false positive）**。<br>
> 本项目使用混淆仅用于保护程序业务逻辑，**并非用于规避安全检测、制作恶意程序**。<br>
