# github-
由于在使用vscode上关联github撞了好多坑，比如提交速度慢和同步推送失败等等问题，此次做一次总结让小伙伴避免掉坑

#首先是关于git.ignore文件的配置问题：因为我们提交的vscode代码中有很配置下载的相关包比如node_modules文件还有解析处理的dist文件夹或者是package-lock.json(这个是在下载devDependencies自动生成的文件)这三个是我们不需要提交的文件，尤其是node_modules文件夹下的文件，非常庞大。这是我们就需要在git.ignore文件中配置好。
#第一种方法（全局配置）：一般在c盘的用户(user)文件夹中,如果你没有git.ignore这个文件就自己新建一个，在里面进行以下配置：
.DS_Store
package-lock.json
node_modules/
dist/
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Editor directories and files
.idea
.vscode
*.suo
*.ntvs*
*.njsproj
*.sln

#mycjh
yarn.lock
mock
bak
(上面是关于vscode的一些配置)还有idear的配置如下：
# Compiled class file
*.class
# Log file
*.log
# BlueJ files
*.ctxt
# Mobile Tools for Java (J2ME)
.mtj.tmp/
# Package Files #
*.jar
*.war
*.nar
*.ear
*.zip
*.tar.gz
*.rar
# virtual machine crash logs, see 
http://www.java.com/en/download/help/error_hotspot.xml
hs_err_pid*
.classpath
.project
.settings
target
.idea
*.iml
以上相关的配置按照你的需要写上。
#第二种方法：vscode本地配置：
打开vscode -> 设置 -> 扩展 -> Git -> Repository Scan lgnored Folders(在这里写上需要忽略提交的文件夹以及文件后缀名如：**/node_modules，**/package-json) -> 确定。
