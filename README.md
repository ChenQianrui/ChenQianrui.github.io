# ChenQianrui.github.io
2023年计算机科学与编程入门课程作业

# 计算机科学与编程入门课程第一次作业
## 2210120123 陈芊睿
### 1. 作业1 
词频分析

我选取了自己喜欢的长篇小说《哈利·波特》全集进行动词词频分析，并用柱状图呈现结果，结果选取了频率排名前25的动词，并可通过拖拽滑动条选择显示词语的数量

[作业1链接](https://ChenQianrui.github.io/HP_verb_frequency.html)

### 2. 作业2
中国地图、世界地图

我在网上查找到了2021年中国内地各省的出生率数据，以及2020年世界有石油储备的国家的石油储备量，使用了map类型图标进行展示

[作业2链接1](https://ChenQianrui.github.io/2021年中国各省出生率.html)

[作业2链接2](https://ChenQianrui.github.io/2020石油储量.html)

### 3. 作业3
组合图表

我查询了学校官方数据，得到了我所在专业、我有意向修读双学位的专业，以及北京大学校本部全校2017、2018、2019、2021年的毕业生去向数据，制作成了时间线形式的组合图标，可以叫直观地看出每年毕业生去向的趋势与变化

[作业3链接](https://ChenQianrui.github.io/历年毕业生去向.html)

# 计算机科学与编程入门课程第二次作业
## 2210120123 陈芊睿
### 1. 作业1 
模拟搜索引擎

我使用notepad++以及内嵌css的模式，实现了基于必应搜索引擎的模拟搜索引擎：BirdSearch，并且利用bootstrap5等网页设计工具设计了搜索引擎界面以及按钮、搜索框等元素，绘制了搜索引擎图标。

[作业1链接](https://ChenQianrui.github.io/BirdSearch-搜索引擎模拟.html)

### 2. 作业2
词频分析

我选取了《儒林外史》这部清代作家吴敬梓创作的长篇写实讽刺小说作为分析对象。《儒林外史》全书五十六回，作者以写实主义描绘各类人士对于“功名富贵”的不同表现，一方面真实地揭示人性被腐蚀的过程和原因，从而对当时吏治的腐败、科举的弊端、礼教的虚伪等进行了深刻的批判和嘲讽；一方面热情地歌颂了少数人物以坚持自我的方式所作的对于人性的守护，从而寄寓了作者的理想。这部著作是我最喜欢的清代小说之一，其中的人物性格的刻画也深入细腻，人物形象鲜明。

我运用jieba库对其中的词语进行分词，通过词性筛选功能和仔细查证校对，筛选出其中的11个主要人物：凤鸣岐、杜少卿、鲍廷玺、牛浦、马二、鲍文卿、杜慎卿、萧云仙、老和尚、王胡子、庄征君，以及3类人物群像：和尚、相公和老先生，通过编程获得了人物词频、人物节点、人物连接3个csv文件将他们按照书中的褒贬评价分成4类：褒、中、俗、贬，手动制作了带分类的人物节点csv。之后我按照课上学到的方法分析人物“共现”情况，并使用pyecharts渲染生成“force”类型的关系图。
用本次课学到的网页设计技术，设计一个简单的网页，放置关系图和相关说明


[作业2链接](https://ChenQianrui.github.io/《儒林外史》人物共现分析.html)

# 计算机科学与编程入门课程大作业
## 2210120123 陈芊睿

### 一、选题创意：
我身边有许多亲戚朋友关心股票行情，他们多数定期浏览股票行情网站，通过对比股票交易额、涨跌幅等数据的变化选择有前景的股票进行投资。我认为对于大规模的行情数据，人工浏览记录耗时长、分析能力有限、数据处理难度大，可以通过网络爬虫的形式定时爬取数据，将股票代码、名称、成交量等数据储存并分析，从而更加便捷、直观地看出一定时间之内股票市场的变化趋势，通过分析股票量比找出“潜力股”。
因此，本学期的大作业我计划利用selenium+Python的网络爬虫技术，从周一至周五，在每日开市时间内每间隔10分钟爬取国内A股市场股票成交量排行榜中前160名的股票代码、名称、成交量信息，将数据储存到csv文档中，最后用pandas对数据进行清洗和分析，将结果利用pyecharts图表呈现在网页中。
文档中红色字为我对实操过程中出现的问题的反思和解决方案，也是将设计方案中的理论与实际实践过程的对比。


### 二、数据获取办法：
1.数据获取工具：Selenium库、Python（网络爬虫）
选择理由：
（1）Selenium库操作较为简便，可以通过CSS_SELECTOR、XPATH等方式精准定位元素，有效抓取目标信息；
（2）Selenium运行时会在屏幕上打开相关网页，可以较清晰地看到程序运行的过程，方便获取反馈，对程序进行修正和改进；
（3）Selenium本身为自动化测试工具，可以模拟用户浏览网页的行为，被反爬的概率较低。

2.爬取网站：新浪财经网https://vip.stock.finance.sina.com.cn 和东方财富网http://quote.eastmoney.com/
选择理由：
（1）两个网站国内股民常用的行情网站之一，拥有实时更新的、全面准确的股市数据；
（2）均无需账号登录或下载客户端（优于需要开户的中信证券官网），网页设计较为简洁、数据呈现清晰，程序编写和运行难度不高；尝试爬取后并未出现明显反爬，说明数据公开性较好、连接稳定，且不涉及个人隐私，适合作为爬取网站。
（3）原本我使用新浪财经网作为爬取对象，但是考虑到计算量比需要“前5天平均成交量”这一数据，难以获取，所以得不到准确数据。而东方财富网上面则有实时量比数据，无需自行计算，十分便捷，并且东方财富网的连接更加稳定、爬取更加容易。然而大部分数据仍然是从新浪财经网上获取的，由于没有及时改变爬取对象，所以通过东方财富得到的量比数据十分有限。

3.爬取内容：A股行情排行表前160名的股票所对应的股票代码、股票名称、成交量、当前时间、量比。
实现方法：
（1）无需从网站首页经过工具栏逐层进入，使用“browser.get()”函数，网址为https://vip.stock.finance.sina.com.cn/mkt/#stock_hs_amount，或http://quote.eastmoney.com/center/gridlist.html#hs_a_board。即可进入A股排行表界面。
（2）通过观察页面可知，新浪财经排行表默共有130页，每页显示40个数据，降序排列。排行表上方可以选择每页显示的条数，最多可显示80条，但是需要滚轮操作，否则无法抓取页面全部信息，故选择每页显示40条。考虑到操作简便程度和数据规模，我决定抓取排行表前160名的股票信息，共进行4次翻页操作。若是东方财富，则每页显示20个数据，需进行7次翻页。
（3）通过观察页面，可知排行榜默认排序依据非“成交额”，而点击每列标题可排序，因此在抓取数据之前应该先让selenium点击（新浪财经单击，东方财富双击）名为“成交量/手”的列标题，使得数据按照成交量由高到低排序，再进行抓取。
对于新浪财经网，由于其每页显示的内容较多、人工浏览时需要滚动页面，我发现在爬取时添加滚轮行为browser.execute_script('window.scrollBy(0,90)')能够增大爬取成功的概率，对于东方财富网，由于其每页显示内容较少，且翻页之后不会自动跳转回页面顶部，难以定位元素，故无需进行滚轮操作。
（4）每次读入数据时在计算每只股票的量比，用以衡量股票的相对成交量，反映其当前活跃程度，并将这一数据也同时写入'./股票信息.csv'中。
实际操作过程中发现缺少数据，由于量比=（当前交易量/累计开市时间）/过去5日平均日成交量，计算累计开市时间时难以计算当前时间与固定的开市时间之间的差值，且网站上无法获取5日平均交易量，因此计算时这一数据有误。若更换成东方财富网则可以直接总排行榜中爬取量比信息。
（5）通过单击右键选择“检查”，可查看网页html代码，可以复制所需数据对应的selector路径，使用browser.find_element()函数即可。
当尝试此步骤时，我发现新浪财经对于“股票名称”所对应的名称有反爬机制，当尝试复制路径时，会迅速跳转至其父元素，难以获得准确定位，解决方法：多次尝试，在其自动跳转之前复制路径。另外，东方财富网并无此问题。

4.抓取时长：周一至周五，连续5个工作日；每日上午9：30-11：30、下午13：00-15：00每隔10分钟抓取数据。
实现方法：由于开市时间较短，可以在本地电脑上运行，由于每天上午和下午均运行12次。我原本尝试使用for循环，每次循环结束后用time等待10分钟再进行下一次循环，每天9：30、13：00重启程序。
在实操过程中，我发现由于网站本身的限制，程序很少能够完全爬取160条信息，而是会报错，故循环几乎无法执行，故去掉了循环，改为手动运行，便于发现报错之后再次运行。
理由：
（1）股市交易时间为每周一到周五上午时段9:30-11:30，下午时段13:00-15:00。我所抓取的A股对象属于“沪京深”股票，周六日休市。
（2）在工作日时每间隔10分钟抓取一次能够保证合适的数据量，并且股市每3秒钟刷新一次数据，能够看到数据在一天之内较为细致的的变化趋势；连续抓取5个工作日正好为一个周期，能够较好地看到一周内股票市场的变化趋势，方便数据分析。

5.数据规模：
理论：5（天）*24（次/天）*160（条/次）*6（元素/条）=115200（条）。
实际：约31200条。


### 三、数据分析方法
1.数据处理：
第一次进入页面及每次翻页时构建循环: for i in range(1,41)，在每次循环中分别获取每只股票的代码、中文名称和成交量，其中股票代码与中文名恒不变，将这些信息以逗号分隔写入csv文件中。
最初几次写入数据时用了“w”，导致覆盖写，应该使用“a”模式，追加写。

2.数据保存：“股票信息.csv”，记录爬取的原始数据。“潜力股.csv”记录处理好的数据。

3.数据分析：字典+pandas库
（1）按照{股票名称:累计成交量} 、{股票名称：股票代码}生成两个字典，再将字典合并，用pandas处理、排序（使用df.sort_values(column_name)函数），得到累计成交量降序排列的表格，写成“潜力股.csv”。
（2）再次使用爬虫，将前5名的股票分别在东方财富网上查找，爬取2周只内每日的收盘价。由于其搜索框有反爬机制，即路径中包含的数字随机变化、无法定位。尝试故选用另一种方法：因为“资金流向”数据界面的网址中包含股票代码，故可以利用字符串拼接，将潜力股的代码拼接browser.get('https://data.eastmoney.com/zjlx/'+code+'.html')，从而多次打开不同的网页爬取数据，爬取成功。

4.数据展示：pycharts生成html网页图表：潜力股两周内收盘价.html、潜力股柱状图.html，上传至github个人主页中。
运用组合图表：从数据中选出一周内累计成交额最高的5只股票，作为“潜力股”显示股票名称和股票代码，并且显示其2周之内的收盘价变化折线图。

### 四、问题与局限
（1）实际操作时，我发现两个网站均有一定反爬机制，通常翻一两页就会报错，偶尔能够完整爬取，这也导致了我爬取的数据量达不到理论值。
（2）没有及时获得有效量比数据，单一依靠累计成交量和收盘价，导致结果有局限性。
（3）由于网站反爬原因，无法根据潜力股名称（或代码）获得更详细的数据，导致数据本身不够丰富。
（4）电脑故障，只能借用同学的电脑做最后的数据处理和报告撰写。

[大作业链接1](https://ChenQianrui.github.io/潜力股柱状图.html)

[大作业链接2](https://ChenQianrui.github.io/潜力股两周内收盘价.html)
