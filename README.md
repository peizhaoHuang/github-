# vscode使用github的注意事项
由于在使用vscode上关联github撞了好多坑，比如提交速度慢和同步推送失败等等问题，此次做一次总结让小伙伴避免掉坑

#首先是关于git.ignore文件的配置问题：因为我们提交的vscode代码中有很配置下载的相关包比如node_modules文件还有解析处理的dist文件夹或者是package-lock.json(这个是在下载我们项目需要用的devDependencies时自动生成的文件)，这三个相关文件一般是我们不需要提交的文件，尤其是node_modules文件夹下的文件，非常庞大。这是我们就需要在git.ignore文件中配置好。

# 配置有两种方法：
#第一种方法（全局配置）：一般在c盘的用户(user)文件夹中,如果你没有git.ignore这个文件就自己新建一个，在文件中写入git.ignore文件中的配置(外面上传的git.ignore文件)，里面以及对idear项目中一些文件进行上传github忽略配置和vscode项目进行配置。
#第二种方法：vscode本地配置：
打开vscode -> 设置 -> 扩展 -> Git -> Repository Scan lgnored Folders(在这里写上需要忽略提交的文件夹以及文件后缀名如：**/node_modules，**/package-json) -> 确定。
# 关于代码管理器提交慢的问题
打开vscode -> 设置 -> 扩展 -> Git -> Use Editor As Commit Input(取消勾选即可)。
# 提交时出现提交失败
原因：由于没有配置信任的服务器HTTPS验证。默认，cURL被设为不信任任何CAs，就是说，它不信任任何服务器验证。
可以通过在项目文件夹下打开git Bash命令面板，输入：git config --global http.sslVerify false 回车
以上就是我在使用vscode中进行github提交所遇到的问题，希望对您有所帮助！
