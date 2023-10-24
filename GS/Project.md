1. 翻译后的字串导入
Jenkins -> General -> import translate string -> build
2. resource增加的字串导入
Jenkins -> Android -> Update_Resource -> build

2. 发版
    1. 写release notes
    2. 打tag
    3. 
Dashboard
Garmin_Sports_Mobile
Android
Test_GSM_Android_Linux

3. 发布libs
先添加 apply from:"../c3upload.gradle"
在gradle里面的build文件下点击assemble
在publishing文件下点击publish

