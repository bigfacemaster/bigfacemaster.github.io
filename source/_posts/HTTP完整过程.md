---
title: HTTP完整过程
date: 2016-12-03 23:59:39
tags: HTTP
category: 基础知识
---
# HTTP完整过程
## 一. 域名解析
1. 浏览器自身的DNS缓存；
2. 如果浏览器没有，查找系统；
3. hosts文件；
4. DNS的系统调用；
5. Net、 BIOS、 Name、 Cache;
6. WINS服务器；
7. 广播查找；
8. LMHOSTS文件；

## 二. 发起TCP三次握手
 user-Agent------------------->(TCP)----------------->WEB程序、<br/>
 Client<----------------------------------------------------->Server <br/>
 closed------->(SYN=1, ACK = 0, seq = x) --------->Lister<br/>
 SYN-Send(SYN=1, ACK=1,seq=y,ack=y+1)<-->SYN-RCVD<br/>
 ESTAB-LISHED<------------>(Form:SYN;ACK=1, seq=x+1,ack=y+1)ESTAB-LISHED<br/>
 (ACK=0:确认号无效，SYN=1:连接请求)
## 三. 建立TCP连接后发起的http请求
get: 完整请求一个资源；<br/>
HEAD: 仅请求相应首部；<br/>
POST: 提交表单；<br/>
PUT: （webdav）上传；<br/>
DELETE: (webdav)删除； <br/>
OPTIONS: 返回请求的资源所支持的方法的方法；<br/>
TRACE: 追求请求的资源的所支持的方法的方法；<br/>
URI: Uniform Resource Identifier 统一资源标识符；<br/>
URL: Uniform Resource Locator 统一资源定位符；<br/>
URN: Uniform Resource Name 统一资源名称；<br/>
(URL && URN) 都属于URI
### 请求协议
  1. Request Header:请求协议头部信息; <br/>
  2. Accept: 告诉服务器端，接受那些MIME类型；<br/>
  3. Accept-Encoding: 接受哪些压缩方式的文件； <br/>
  4. Accept-Language: 告诉服务器能够发送哪些语言；<br/>
  5. Connection: 告诉服务器支持keep-alive特性；<br/>
  6. Cookie: 每次请求时都会携带上Cookie以方便服务器端识别是否时同一个客户端； <br/>
  7. Host: 用来标识请求服务器上的那个虚拟主机； <br/>
  8. user-Agent: 用户代理，一般指浏览器或者wget&&；<br/>
  9. 条件请求头部: If-Modified-Since: 文件更新，再次请求，发送；Authorization:客户端提供给服务器的认证消息；<br/>

## 四. 服务器端效应HTTP请求，浏览器得到heml代码
### 1. 状态码：信息性状态码
1xx: 100， 101；<br/>
2XX: 成功状态码 200：OK；<br/>
3XX: 冲顶小状态码 301：永久重定向，Location响应首部的值行为当前URL，因此为隐藏重定向；302：临时重定向，显示重定向，Location响应首部的值为新的URL；304：Not Modified 未修改，比如本地缓存的资源文件和server对比，无修改返回304状态码，无需请求，直接使用本地资源；<br/>
4XX：客户端错误状态码 404：Not Found，请求的URL资源不存在；
5XX: 服务器端错误状态码： 500：Internal Server Error 服务器内部错误；502 Bad Gateway 前面代理服务器练笔不到后端的服务时出现； 504： Gateway Timeout，代理能联系到后端的服务器，但后端的服务器在规定的时间内灭没有给代理服务器响应；<br/>
### 2. 响应头信息 Response Header
Connection: 使用Keep-alive特性；<br/>
Content-Encoding: 使用××方式对资源压缩；<br/>
Content-type: MIME类型为html/..类型，字符集是UTF-8；<br/>
Date: 响应的日期；<br/>
Server: 使用的WEB服务器；<br/>
Transfer-Ecoding: Chunked，分块传输编码，是http中的一种数据传输机制，允许http由网页服务器发送给客户端应用的数据可以分成多个部分，分块传输编码只能在http协议1.1中提供；Vary，头域值制定了一些请求头域，告诉下游代理是使用缓存响应还是原始服务器请求；X-pingback：向外部发出引用信息；
### 3.缓存 Cache
一个使用缓存Cache的站点会监听客户端发送的请求，并保存服务器的回响，若有另外一个使用相同URL发送请求，它能够使用以前保存的文件，无需再次请求，这样可以减少延迟与降低网络负载；
#### 浏览器缓存Cache： HTTP协议定义的缓存机制
Expires策略：Expires是web服务器响应小心头字段，在响应http请求时告诉服务器的过期时间前浏览器可以直接从浏览器缓存取数据，无需再次请求；<br/>
Cache-control策略：Cache-control与Expires作用相同，指明当前资源的有源期，控制浏览器是否直接从浏览器缓存取数据还是重新发送到服务器取数据;<br/>
http协议头Cache-control：<br/>
public：响应可被任何缓存区缓存；<br/>
private: 对于单个用户的整个或部分响应消息，不能被共享缓存处理，这允许服务器仅仅猫叔当用户的部分想一个个消息，此响应消息对其他的用户请求无效；<br/>
no-cache: 表示请求或者响应不能缓存；<br/>
no-store: 用于防止重要的信息被五一的发布，在请求消息中发送将是的请求和响应消息都不能使用缓存；<br/>
max-age: 指示客户机可以接收生存期不大于制定时间(秒)的响应；<br/>
min-fresh: 指示客户机可以接收响应时间不小于当前时间加上制定时间的响应; <br/>
max-stable: 指示客户机可以接收超出超时期间的响应消息，如果制定max-stable消息的值，那么客户机可以接收超出超时期指定值之内的响应消息；<br/>
last-stable: 标示这个响应资源的最后修改时间；<br/>
If-Modified-Since: 当资源过期时，发现资源有last-stable声明，向server请求带上If-Modified-Since请求时间，对最后时间对比；<br/>
Etag/If-None-Match: Etag，web服务器响应请求时，告诉浏览器当前资源在服务器的唯一标识；If-None-Match: 资源过期，发现资源具有Etag声明，则再次向web服务器请求时带上头If-None-Match(Etag值)；Web服务器收到请求后发现有头If-None-Match则与被请求后资源的相应校验串进行对比，决定返回200/304；Last-Modified与Etag可一起使用，服务器优先验证ETag，一只的情况下，才会继续对比Last-Modified,最后才决定是否返回304.<br/>
