---
layout: post
title: Deepin中安装配置ChromeDriver
categories: Deepin
description: Deepin安装ChromeDriver
keywords: Deepin, ChromeDriver
---

## Deepin中安装配置ChromeDriver

### 查看当前的Chrome版本信息
在谷歌浏览器地址栏中输入`chrome://version/`可以查看当前的Chrome信息：
```
Google Chrome：	62.0.3202.62 (正式版本) （64 位）
修订版本：	9da914b118cb0d10d715ccc4ad20575a0305a304-refs/branch-heads/3202@{#700}
操作系统：	Linux
JavaScript：	V8 6.2.414.32
Flash：	29.0.0.113 /home/wenbin/.config/google-chrome/PepperFlash/29.0.0.113/libpepflashplayer.so
用户代理：	Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.3202.62 Safari/537.36
命令行：	/usr/bin/google-chrome-stable --flag-switches-begin --flag-switches-end
可执行文件路径：	/opt/google/chrome/google-chrome
个人资料路径：	/home/wenbin/.config/google-chrome/Default
其他变体：	c134752e-b8b72c88  
                ..............
```

| chromedriver版本 | 支持的Chrome版本 |
| -------------- | :---------: |
| v2.34          |   v61-63    |
| v2.33          |   v60-62    |
| v2.32          |   v59-61    |
| v2.31          |   v58-60    |
| v2.30          |   v58-60    |
| v2.29          |   v56-58    |
| v2.28          |   v55-57    |
| v2.27          |   v54-56    |
| v2.26          |   v53-55    |
| v2.25          |   v53-55    |
| v2.24          |   v52-54    |
| v2.23          |   v51-53    |
| v2.22          |   v49-52    |
| v2.21          |   v46-50    |
| v2.20          |   v43-48    |
| v2.19          |   v43-47    |
| v2.18          |   v43-46    |
| v2.17          |   v42-43    |
| v2.13          |   v42-45    |
| v2.15          |   v40-43    |
| v2.14          |   v39-42    |
| v2.13          |   v38-41    |
| v2.12          |   v36-40    |
| v2.11          |   v36-40    |
| v2.10          |   v33-36    |
| v2.9           |   v31-34    |
| v2.8           |   v30-33    |
| v2.7           |   v30-33    |
| v2.6           |   v29-32    |
| v2.5           |   v29-32    |
| v2.4           |   v29-32    |


### 下载对应的Chromedriver版本
下载地址：
```
http://npm.taobao.org/mirrors/chromedriver/
```

### 配置
将下载来的ChromeDriver解压，得到一个ChromeDriver文件
我们只需要将ChromeDriver文件放到``/uer/bin/``路径下
```
sudo cp chromedriver /usr/bin/
```
### 测试安装是否成功
编写py文件写入以下代码：
```
from selenium import webdriver

driver = webdriver.Chrome()
driver.get("https://www.baidu.com")
```
运行之后，如果能过弹出Chrome页面，就说明安装成功：
![](../images/Chrome.png)
