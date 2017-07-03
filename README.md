# jenkins-jmeter-ant
## jenkins
构建 >> 执行shell >> ant build.xml  
构建后 >> publish HTML reports  
## jmeter
修改 jmeter.properties 文件  
jmeter.save.saveservice.output_format=xml  
jmeter.save.saveservice.response_message=true  
添加自己想要显示的数据  
需要将${jmeterhome}/extras/ant-jmeter-1.1.1.jar文件拷贝到${anthome}/lib目录下  
## HTML报告支持css
系统管理 >> 脚本命令行 >> System.setProperty("hudson.model.DirectoryBrowserSupport.CSP", "")
