深度学习框架，其中主要包括Theano、TensorFlow、Keras、Caffe、Caffe2、Torch7、Pytorch、CNTK、MXNet、Leaf、DeepLearning4、Lasaagne、Neon等。

| 框架       | 机构      | 支持语言                              |
| ---------- | --------- | ------------------------------------- |
| TensorFlow | Google    | Python/C++/Go/Java/JavaScript         |
| PyTorch    | Facebook  | Python                                |
| Keras      | Fchollet  | Python                                |
| MXNet      | DMLC      | Python/C++/R/JuliaScala/Go/JavaScript |
| CNTK       | Microsoft | C++/C#                                |

## TensorFlow

官方地址：www.tensorflow.org

中文文档：www.tensorflow.org/tutorials

GitHub：www.github.com/tensorflow

## Keras

中文文档：https://keras.io/zh

GitHub：http://github.com/keras-team

## Pytorch

官方资料：https://pytorch.org

英文文档：https://pytorch.org/tutorials

GitHub：https://github.com/pytorch

## Microsoft CNTK

官方资料：https://microsoft.com/en-us/cognitive-toolkit

英文文档：https://www.microsoft.com/en-us/cognitive-toolkit.features/model-gallery/?filter=Tutorial

GitHub：https://github.com/Microsoft/CNTK

## MXNet

官方资料：https://mxnet.apache.org

英文文档：https://mxnet.apache.org/version.master/tutorials/index.html

GitHub：https://github.com/apache/incubator-mxnet

## requests

官方资料：https://www.Python-requests.org/en/master

英文文档：https://cn.Python-requests.org/zh_CN/latest

GitHub：https://github.com/requests/requests



@Python中常用的解析库lxml库、BeautifulSoup库、JSON库等

### lxml 

lxml库支持HTML和XML的解析，还支持XPath（XML Path Language，XML路径语言）解析方式。

GitHub：https://github.com/lxml/lxml

官方资料：https://lxml.de

PyPI：https://pypi.org/project/lxml

```python
pip3 install lxml #install
import lxml		 #import
```

### BeautifulSoup

能将HTML的标签文件解析成树形结构，从而方便获取指定标签的对应属性。

官方资料：https://www.crummy.com/software/BeautifulSoup/bs4/doc

中文文档：https://www.crummy.com/software/BeautifulSoup/bs4/doc.zh

PyPI：https://pypi.org/project/beautifulsoup4

```python
pip3 install beautifulsoup4	  #install
from bs4 import BeautifulSoup #import
```



URI包括URL和URN。

URI-Uniform Resource Identifier，统一资源标识符

URL-Uniform Resource Locator，统一资源定位符

URN-Uniform Resource Name，统一资源名称



HTTP-Hyper Text Transfer Protocol，超文本传输协议，使用TCP，广泛版本为HTTP 1.1

HTTPS-Hyper Text Transfer Protocol over Secure Socket Layer，在HTTP协议下加入SSL层。主要作用分为两种：一种是建立一个信息安全通道来保证数据传输的安全性；另一种是确认网站的真实性。使用HTTPS协议的网站，都可以通过单击浏览器地址栏的锁头标志来查看网站认证之后的真实信息，也可以通过CA机构颁发的安全签章来查询。

|          | HTTP     | HTTPS                            |
| -------- | -------- | -------------------------------- |
| CA证书   | 不需要   | 需要，切免费证书少，需要一定费用 |
| 传输     | 明文传输 | 具有安全性的SSL加密传输          |
| 端口     | 80       | 443                              |
| 连接状态 | 无状态   | 加密传输、身份认证               |

HTTP的优缺点

| 优点                                                         | 缺点                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| 使用HTTPS协议可认证用户和服务器，确保数据正确发送到客户端和服务端 | 费时，使页面加载延长近50%                                    |
| 确保数据的完整性                                             | 缓存不如HTTP高效，增加数据开销和功耗，甚至影响安全措施       |
| 目前现下架构下最安全的解决方案，虽非绝对安全，大幅增加了中间人攻击的成本 | SSL证书需要钱，功能越强大费用越高                            |
|                                                              | SSL证书需要绑定IP，同一IP上不能绑定多个域名，IP资源有限（是否支持IPv6？） |

HTTP流程：

```sequence
浏览器->服务器: 1.建立TCP连接
浏览器->服务器: 2.Web浏览器向Web服务器发送请求命令
浏览器->服务器: 3.Web浏览器发送请求头信息
Note right of 服务器: 请求头信息包括user-agent、host等自身信息，\n最后发送一个空请求代表请求头信息发送完毕\n如果是POST请求，则会继续发送请求体
服务器->浏览器: 4.Web服务器应答
服务器->浏览器: 5.Web服务器发送应答头信息
服务器->浏览器: 6.Web服务器向Web浏览器发送数据\n 以Content-Type应答头信息所描述的格式\n发送用户所请求的实际数据
服务器->浏览器: 7.Web服务器关闭TCP连接\n一旦Web服务器向Web浏览器发送了请求数据，\n它就要关闭TCP连接
```

HTTP 1.0协议定义了3种请求方法：GET、POST和HEAD

HTTP 1.1协议新增了5种请求方法：OPTIONS、PUT、DELETE、TRACE和CONNECT。

| 方法    | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| GET     | 请求指定的页面信息，并返回实体主体                           |
| HEAD    | 类似于GET请求，但返回的响应中没有具体的内容，用于获取报头    |
| POST    | 向指定资源提交数据进行处理请求（如提交表单或上传文件）。数据被包含在请求体中。POST请求可能会导致新资源建立和/或已有资源的修改 |
| OPTIONS | 允许客户端查看服务器的性能                                   |
| PUT     | 从客户端向服务器端传送的数据取代指定的文档内容               |
| DELETE  | 请求服务器删除指定的页面                                     |
| TRACE   | 回显服务器收到的请求，主要用于测试或诊断                     |
| CONNECT | HTTP/1.1协议中预留给能够将连接改为管道方式的代理服务器       |

GET和POST对比

| 对比项           | GET                                                          | POST                                                         |
| ---------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 后退/刷新        | 无害                                                         | 数据会被重新提交（浏览器应该告知用户数据会被重新提交）       |
| 书签             | 可收藏为书签                                                 | 不可收藏为书签                                               |
| 历史             | 能缓存                                                       | 不能缓存                                                     |
| 编码类型         | application/x-www-form-urlencoded                            | application/x-www-form-urlencoded或multipart/form-data，为二进制数据使用多重编码 |
| 历史             | 参数保存在浏览器历史中                                       | 参数不会保存在浏览器历史中                                   |
| 对数据长度的限制 | 有限制，当发送数据时，GET方法向URL中添加数据；URL的长度是受限制的（URL的最大长度一般是2000~8000个字符） | 无限制                                                       |
| 对数据类型的限制 | 只允许ASCII字符                                              | 无限制，也允许二进制数据                                     |
| 安全性           | 与POST相比，GET的安全性较差，因为其所发送的数据是URL的一部分（在发送密码或其他敏感信息时不要使用GET） | POST比GET更安全，因为参数不会被保存在浏览器历史或Web服务器日志中 |
| 可见性           | 数据在URL中对所有人都是可见的                                | 数据不会显示在URL中                                          |

各浏览器的请求长度限制

| 浏览器/服务器               | URL长度限制（字符数） |
| --------------------------- | --------------------- |
| Google Chrome               | 8182                  |
| Microsoft Internet Explorer | 2083（2K+35）         |
| Firefox                     | 65535                 |
| Opera                       | 19000                 |
| Safari                      | 80000                 |
| Apache（Server）            | 8192                  |
| Microsoft IIS               | 16384                 |



### 请求头

| Header          | 解释                                                         | 示例                                                  |
| --------------- | ------------------------------------------------------------ | ----------------------------------------------------- |
| Accept          | 指定客户端能够接受的内容类型                                 | Accept: text/plain、text/html                         |
| Accept-Charset  | 浏览器可以接受的字符编码集                                   | Accept-Charset: iso-8859-5                            |
| Accept-Encoding | 指定浏览器可以支持的Web服务器返回内容压缩编码类型            | Accept-Encoding：compress、gzip                       |
| Accept-Language | 浏览器可接受的语言                                           | Accept-Language: en、zh                               |
| Connection      | 表示是否需要持久链接（HTTP/1.1协议默认进行持久连接）         | Connection: keep-alive                                |
| Host            | 指定请求的服务器的域名和端口号                               | Host: www.google.com                                  |
| Cookie          | HTTP请求发送时，会把保存在该请求域名下的所有Cookie值一起发送给Web服务器 |                                                       |
| Referer         | 先前网页的地址，当前请求网页紧随其后，即来路                 | Referer: http://www.500.com                           |
| User-Agent      | User-Agent的内容包含发出请求的用户信息                       | User-Agent: Mozilla/5.0 (Windows NT 10.0、Win64、x64) |
| Content-Type    | 请求的实体对应的MIME请求，既可用于请求消息，也可用于响应消息，是规定请求正文内容格式的头部。例如，利用这个头部，可以规定正式的格式为纯文本格式、表单格式、XML格式、JSON格式、图像格式等 | Content-Type: text/html                               |

### 请求体

#### 1.application/x-www-form-urlencoded

最常见的POST提交数据的方式。浏览器的原生form表达，类似

```
POST http://www.example.com HTTP/1.1 Content-Type:
application/x-www-form-urlencoded;charset=utf-8
title=test&sub%5B%5D=1&sub%5B%5D=2&sub%5B%5D=3
```

#### 2. multipart/form-data

常见的POST提交数据的方式，必须让form的enctyped等于multipart/form-data值，示例：

```
POST http://www.example.com HTTP/1.1 
Content-Type:multipart/form-data; boundary=----WebKitFOrmBoundaryrGKCBY7qhFd3TrwA
------WebKitFOrmBoundaryrGKCBY7qhFd3TrwA
Content-Disposition: form-data; name="text"
title
------WebKitFOrmBoundaryrGKCBY7qhFd3TrwA
Content-Disposition: form-data; name="file";filename="chrome.png"
Content-Type: image/png
PNG ... content of chrome.png ...
------WebKitFOrmBoundaryrGKCBY7qhFd3TrwA
```

#### 3.application/json

application/json作为响应头的同时，也可以作为请求头，告诉服务器端消息主体是序列化的JSON字符串。由于JSON规范的流行，除低版本IE外的各大浏览器都原生支持JSON.stringifty，并且服务器端语言也都有处理JSON的函数。

#### 4.text/xml

使用HTTP作为传输协议、XML作为编码方式的远程调用规范。



## Response响应

### 1.响应状态码（Response Status Code）

| 分类 | 描述                                           |
| ---- | ---------------------------------------------- |
| 1**  | 信息，服务器收到请求，需要请求者继续执行操作   |
| 2**  | 成功，操作被成功接收并处理                     |
| 3**  | 重定向，需要进一步操作以完成请求               |
| 4**  | 客户端错误，请求包含语法错误或无法完成请求     |
| 5**  | 服务器错误，服务器在处理请求的过程中发生了错误 |

常见状态码及错误原因详见：http://www.w3school.com.cn/tags/html_ref_httpmessages.asp

### 2. 响应头（Response Headers）

- Date：当前的GMT时间
- Last-Modified：文档的最后改动时间
- Content-Encoding: 文档的编码（Encode）方法。只有在解码之后才可以得到Content-Type头指定的内容类型。利用gzip压缩文档能够显著地减少HTML文档的下载时间。
- Content-Length：表示内容长度。只有当浏览器使用持久HTTP连接时才需要此数据。
- Server：服务器名称。
- Content-Type：表示后面的文档属于什么MIME类型。例如，text/html代表返回HTML文档；application/x-javascript代表返回JavaScript文件；image/jpeg、image/gif、image/png代表返回各种格式的图片。
- Set-Cookie：设置和页面关联的Cookie。
- Expires：指定响应的过期时间，可以使代理服务器或浏览器将加载的内容更新到缓存中。如果需要再次访问，则可以直接从缓存中加载，这样可以降低服务器负载，缩短加载时间。

### 3. 响应体（Response Body）

响应的正文数据都在响应体中。在做爬虫请求的时候网页时，要解析的内容就是响应体。

```python
import time
import datetime
import requests
import json
import os
from bs4 import BeautifulSoup
import operator
import chardet
import re
import lxml
from html.parser import HTMLParser


def get_ssq_data():
    bet_header = {'User-Agent':'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.77 Safari/537.36'}
    url = "https://kaijiang.500.com/shtml/ssq/18121.shtml"

    # phrase 1
    # try:
    #     lottery_req = requests.get(url, headers=bet_header, timeout=10)
    # except:
    #     print("Read time out")
    #     return -1

    # phrase 2
    try:
        try:
            lottery_req = requests.get(url,headers = bet_header, timeout=10)
            lottery_req.encoding = "GB2312"
            # print(lottery_req.text)
        except:
            print("Read time out")
            return -1

        soup = BeautifulSoup(lottery_req.text,'lxml')
        # print(soup)
        tablesoup = soup.find_all("table",attrs={"class":"kj_tablelist02"})
        # print(tablesoup)
        open_rows = tablesoup[0].findAll("div",attrs={"class":"ball_box01"})
        # print(open_rows)

        #获取标签中所有字符串并输出
        open_dates = tablesoup[0].findAll("td",attrs={"class":"td_title01"})
        open_dates_spans = open_dates[0].findAll("span",attrs={"class":"span_right"})
        # print(open_dates_spans[0].get_text())
        open_date = open_dates_spans[0].get_text()
        ssq_open_year = open_date[5:9]
        year_char_index = open_date.index('年')
        month_char_index = open_date.index('月')
        day_char_first_index = open_date.index('日')
        day_char_index = open_date.find('日',day_char_first_index+1)
        ssq_open_month = open_date[year_char_index+1 : month_char_index].zfill(2)
        ssq_open_day = open_date[month_char_index+1: day_char_index].zfill(2)
        # print(ssq_open_year)
        # print(ssq_open_month)
        # print(ssq_open_day)

        # 获取奖金金额和注数
        rows = tablesoup[1].findAll('tr')
        tds_1 = rows[2].findAll('td')
        tds_2 = rows[3].findAll('td')
        first_prize_name = tds_1[0].get_text().strip()
        first_prize_num = tds_1[1].get_text().strip()
        first_prize = tds_1[2].get_text().strip()
        second_prize_name = tds_2[0].get_text().strip()
        second_prize_num = tds_2[1].get_text().strip()
        second_prize = tds_2[2].get_text().strip()
        # print(first_prize_name)
        # print(first_prize_num)
        # print(first_prize)
        # print(second_prize_name)
        # print(second_prize_num)
        # print(second_prize)

        open_tds = open_rows[0].findAll("li")
        red_ball1 = open_tds[0].get_text().strip()
        red_ball2 = open_tds[1].get_text().strip()
        red_ball3 = open_tds[2].get_text().strip()
        red_ball4 = open_tds[3].get_text().strip()
        red_ball5 = open_tds[4].get_text().strip()
        red_ball6 = open_tds[5].get_text().strip()
        blue_ball = open_tds[6].get_text().strip()
        print("open ball:%s,%s,%s,%s,%s,%s,%s"%(red_ball1,red_ball2,red_ball3,red_ball4,red_ball5,red_ball6,blue_ball))

        # coding problem
        # print(lottery_req.status_code)
        # print(lottery_req.text)
        # print(lottery_req.encoding)
        # print(lottery_req.apparent_encoding)
    except Exception as e:
        raise e

if __name__ == '__main__':
    get_ssq_data()
```

#### 3.1 requests库

requests库的参数参考：http://docs.Python-requests.org/zh_CN/latest/user/quickstart.html

```python
requests.get(url,headers = bet_header.timeout=10)
```

- url：获取某个网页的地址。
- timeout：设置超时的时间。可根据网站的数据自行调整。
- header：常用的是user-agent和host，以键对的形式展现出来。

#### 3.2 Header的获取

Chrome开发者工具中，使用最多的3+1个页面，元素（Element）、控制台（Console）、源代码（Sources），另外还有网络（Network）。

- 元素：查看或修改HTML元素的属性、CSS属性、监听事件、断点。
- 控制台：一般用于执行一次性代码，查看JavaScript对象，查看调试日志信息或异常信息。
- 源代码：用于查看页面的HTML文件源代码、JavaScript源代码、CSS源代码。可调试JavaScript，并添加断点。
- 网络：查看header等与网络连接相关的信息。其中XHR为XMLHttpRequest。

## 4 概率论

CDF-Cumulative Distribution Function，累积分布函数

PDF-Probability Density Function，概率密度函数
