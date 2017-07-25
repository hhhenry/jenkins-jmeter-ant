# jenkins-jmeter-ant
接口测试 + HTML 报告模版  

## jenkins
系统配置 >> Enable BUILD_TIMESTAMP  
job构建 >> 执行shell >> ant build.xml  
job构建后 >> publish HTML reports  >>  index pages >> TestReport${BUILD_TIMESTAMP}.html

## jmeter
修改 jmeter.properties 文件  
jmeter.save.saveservice.output_format=xml  
jmeter.save.saveservice.response_message=true  
添加自己想要显示的数据  
需要将${jmeterhome}/extras/ant-jmeter-1.1.1.jar文件拷贝到${anthome}/lib目录下  
使用brew安装ant的话，一般是在/usr/local/Cellar/下

## HTML报告支持css
安装插件：Startup Trigger、Groovy  
新建一个job，该job专门用于Jenkins启动时执行的配置命令  
在Build Triggers模块下，勾选Build when job nodes start  
在Build模块下，Add build step->Execute system Groovy script，在Groovy Script中输入配置命令，System.setProperty("hudson.model.DirectoryBrowserSupport.CSP", "")。
