# 工商在线和离线爬虫系统
项目研发时间：2016年
## 项目介绍
在线和离线公用的是一同框架，和解析业务，区别在于，在线爬虫而外提供了一个web服务用于接受在线post过来的网络链接
而离线则是定时搜索mongodb的url进行爬取，并进行解析根据需要写入到mongodb或者mq中
## 背景介绍
本项目爬取的是16-17年国家企业信用信息公示系统的38个子站点的数据（每个省份有可能会对应多个网站），并对数据解析放到mongodb中

# 目录及文件介绍
- base dirctory
    - gsxt_base_worker.py 所有爬取类的超类，定义了爬取的步骤
    - parse_base_worker.py 所有解析网页类的超类，定义了解析的步骤
    - task_base_work.py 根据需要启动离线或者在线任务
- common 
    一些无关业务的工具类，包括mongodb，mqclient的封装
- config
    - conf.py 数据库或者服务的地址
    - *.conf 用于配置需要启动的类别，所有的任务（爬取和解析）
- task 
    - 所有站点的爬取类
- parser
    - 所有站点的解析类别
