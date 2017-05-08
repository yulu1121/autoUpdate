# android自动更新

        之前一直在用友盟的自动更新插件，很好用，简单方便，可是无奈10月份要关闭了，好吧，只能自己写一个了。

# android studio导入方式

        compile 'com.sangbo.autoupdate:autoUpdate:1.0.3'
        
# 使用方法
## 基本使用

        CheckVersion.checkUrl = "http://www.xxx.com/api/versiontest.txt";     //定义服务器版本信息
        CheckVersion.update(this);                                            //更新，默认更新不显示处理消息（一般自动更新时使用）
        or
        CheckVersion.update(this,true);                                       //更新，并显示处理结果（Toast提示，一般勇于手动更新时使用）

## 扩展方法

        boolean isRun = CheckVersion.isMinimumRunLimit(this);                 //判断服务器APP版本信息最低运行版本号是否大于当前版本号

# 服务器json信息

        {
            "versionCode": 2,                   //app版本
            "isForceUpdate": 0,                 //是否更新   0：更新 1：不更新
            "preBaselineCode": 0,               //最低运行版本
            "versionName": "1.1.0",             //app版本名称
            "downUrl": "http://xx.apk",         //下载地址
            "md5":"xxxxxxxxx",                  //md5
            "updateLog": "xxx,xxx,xx"           //更新公告
        }
        
        
# 历史版本

## 1.0.5

    MD5文件校验修复（默认全部转为大写进行校验）


## 1.0.4

    增加是否进行更新的功能


## 1.0.3

    增加获取当前版本信息接口
    增加判断服务器APP版本信息最低运行版本号是否大于当前版本号接口

## 1.0.2

    更新okhttp版本
    增加最低运行版本的限制

## 1.0.1

    增加MD5验证

##  1.0.0

    初始提交版本
    