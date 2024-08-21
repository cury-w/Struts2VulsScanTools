# Struts2全版本漏洞检测工具 by:ABC_123

注：此工具用于漏洞检测，而非漏洞利用，严禁用于非法用途。

**ABC_123也录制了关于Struts2全版本漏洞检测工具的系列使用教程，欢迎关注我的B站号（希水涵一讲堂）：**

[https://www.bilibili.com/video/BV1MCWWeNEi8/](https://www.bilibili.com/video/BV1MCWWeNEi8/)

<a href="https://www.example.com" target="_blank">点击这里访问示例网站</a>


大家好，我是ABC_123。在2016年时，很多Java开发的网站都是基于Struts2框架的，当时Struts2框架不断爆出各种漏洞，很多工具检测不准确，因而给安全人员、研发人员带来了很大麻烦。为了解决这个问题，ABC_123研发了这款工具，尽可能使这款工具简单容易上手，哪怕对Struts2漏洞完全不懂的新手，也能快速找到Struts2漏洞并进行修复。

注：此前一直在内部流传从未公开，但在一两年前，其它公众号平台已经把工具提供下载了，考虑到工具现在的危害已经大大降低，而且很多朋友害怕公开的工具捆绑有后门，因此本人还是在github上公布原版的下载吧，大家可以作为一个漏洞研究的工具使用。

![a111](https://github.com/abc123info/Struts2VulsScanTools/assets/143333826/73c828b8-5a49-4743-813c-9e48db8fe75b)


1、点击“检测漏洞”，会自动检测该URL是否存在S2-001、S2-005、S2-009、S2-013、S2-016、S2-019、S2-020/021、S2-032、S2-037、DevMode、S2-045/046、S2-052、S2-048、S2-053、S2-057、S2-061、S2相关log4j2十余种漏洞。

2、“批量验证”，（为防止批量geshell，此功能已经删除，并不再开发）。

3、S2-020、S2-021仅提供漏洞扫描功能，因漏洞利用exp很大几率造成网站访问异常，本程序暂不提供。

4、对于需要登录的页面，请勾选“设置全局Cookie值”，并填好相应的Cookie，程序每次发包都会带上Cookie。

5、作者对不同的struts2漏洞测试语句做了大量修改，执行命令、上传功能已经能通用。

6、支持GET、POST、UPLOAD三种请求方法，您可以自由选择。（UPLOAD为Multi-Part方式提交）

7、部分漏洞测试支持UTF-8、GB2312、GBK编码转换。

8、每次操作都启用一个线程，防止界面卡死。

警告：该工具为漏洞自查工具，仅用来扫描及验证网站存在的Struts2漏洞，并可以协助管理员修复网站漏洞，也可用作授权的渗透测试，但严禁用于非授权的渗透测试、严禁用于攻击他人网站、严禁用于非法途径，否则后果自负。

更新历程：
==========================================
2024.06.10 新增S2 Log4j2漏洞的完整利用过程。

2024.06.09 新增S2-052、S2-053漏洞的手工利用功能。

2024.06.08 新增添加多个http消息头的功能，以应对JWT、HttpBasic等鉴权字段的场景。

2024.06.07 更正添加请求头有多余空格的bug。

2024.06.06 修正User-Agent: Java/1.8.0_181的流量特征。

2024.06.05 更正S2-048漏洞的检测逻辑。

2024.06.05 大幅度更改判断漏洞存在与否的关键字，将Top、123、webpath、88888888等替换为随机字符。

2024.06.01 解决Struts2 XSS漏洞检测bug。

2024.05.23 解决S2-045-2检测payload极端情况下误报问题。

2023.07.30 解决mac系统兼容性问题，解决软件界面在不同jdk下大小显示不一样问题。

2023.07.20 对每一个文本输入框添加右键撤销功能。

2023.07.19 对所有文本框输入框添加右键复制、粘贴、全选、删除功能。解决Mac系统的兼容性问题。

2023.02.18 新增一条检测Struts2调试模式的语句。

2022.08.12 修正漏洞检测逻辑，修复bug。

2022.06.15 优化S2-061检测逻辑，加入插入点设置。

2022.06.08 重点优化log4j2漏洞探测功能，更正检测payload错误。

2022.05.30 优化检测payload中content参数与网站正常应用参数重合，造成的误报问题。

2022.05.23 加入S2-061/S2-062漏洞检测与执行命令功能。

2022.05.01 界面整体改版，加入部分AWT组件。

2022.02.10 对部分编辑框添加右键菜单，包括粘粘、剪切、复制功能，解决mac系统下无法使用快捷键问题。

2022.02.09 对Struts2框架Log4j2漏洞调试分析，选择2种成功率较高的poc进行漏洞测试。

2022.02.08 新增对Struts2框架Log4j2漏洞的检测，需要人工查看DNS日志判断漏洞是否存在。

2022.01.21 新增一条payload检测Struts2框架是否开启调试模式。

2021.11.12 新增两条检测paylaod，检测S2-045及S2-046。

2021.10.29 修正扫描debug模式代码执行漏洞的bug，提升准确度。优化代码，程序大小控制在100k左右。

2021.09.16 新增一条payload检测Struts2新版本在调试模式开启时，造成的代码执行漏洞(暂不提供exp，手工利用时，请注意绕过沙盒限制)。

2021.06.16 新增一条payload检测S2-048。

2021.06.15 修正base64编码二进制文件功能，修正编码结果存在换行的bug。

2021.05.26 更新两个绕waf的s2-045、s2-046的payload。

2021.05.24 更新S2-016执行命令语句，感谢outmansec提供payload。

2021.05.24 修正列目录功能的各种payload语句及bug。

2021.05.23 重写HTTP发包模块，每个检测payload提供网页响应码结果。

2021.05.02 优化s2-016、s2-032、s2-019、s2-032漏洞的检测payload。

2021.04.28 部分关键字unicode编码及脏数据，增加部分新的检测语句。

2021.04.26 部分关键字采用 随机数替换，以绕过流量检测。

2021.04.25 新增并优化S2-061检测功能，此漏洞利用条件苛刻，暂未提供漏洞利用功能。

2021.04.20 优化S2-057检测逻辑，新增执行命令功能；

2021.04.20 重新编排检测payload顺序，高危且常见的漏洞优先检测；更新发现漏洞着色功能。

2021.04.17 优化S2-017的payload重定向判断逻辑。

2021.04.03 修复界面ui错误。

2021.04.01 修复https代理bug,修复流异常。

2021.03.31 修复流异常错误导致抓取不到response结果。

2021.03.28 修复connection: close错误，修复界面ui错误。

2020.03.18 修复struts2-016执行命令的错误

2019.03.25 修复http发包中的null错误、异常捕获问题。

2019.03.21 修复若干个小bug，发布18.06版本。

2018.08.26 增加S2-057漏洞检测功能。

2017.09.15 改进S2-052漏洞检测功能，增加准确率，影响范围有限。

2017.09.11 增加S2-052、S2-053漏洞检测功能，影响范围有限。

2017.07.07 增加S2-048漏洞检测功能。

2017.05.11 此工具删除过waf功能。永久删除“批量扫描功能”，并不再研发此功能。

2017.05.09 增加Socks5代理、列目录、S2-045/046上传shell、对二进制文件的base64编码等功能。

2017.04.27 修复S2-016命令执行bug，对各种漏洞的测试语句进行修正。

2017.04.25 重写GET、POST、UPLOAD发包模块，解决部分bug。

2017.03.21 增加Struts2-046漏洞测试。

2017.03.07 增加Struts2-045漏洞测试。

2017.01.03 增加UPLOAD模式绕过WAF功能,原理以上传文件方式提交数据包。

2017.12.28 修复Struts2-016中文乱码问题（选择GBK编码即可）。

2016.08.01 增加Struts2-DevMode漏洞测试。

2016.06.28 增加Struts2-037漏洞测试功能。

2016.05.05 完成首个测试版。

