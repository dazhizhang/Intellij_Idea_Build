# Intellij_Idea_Build
https://blog.csdn.net/xuemengrui12/article/details/74984731


自己在实际工作中的需要，使用Idea打包项目为可执行的jar包，网上找了好多文章但总是不成功，多次尝试后终于跑通，所以记录下来，希望可以帮助各位

步骤：
1. 选中Java项目工程名称，在菜单中选择 File->project structure... (快捷键Ctrl+Alt+Shift+S)。

2. 在弹出的窗口中左侧选中"Artifacts"，点击"+"选择jar，然后选择"from modules with dependencies"。

3. 在配置窗口中配置"Main Class"。

4.配置“Directory for META-INF/MAINFEST.MF”，此项配置的缺省值是：D:\Intellij\SeriesPublish\src\main\java，需要改成：D:\Intellij。如果不这样修改，打成的jar包里没有包含META-INF/MAINFEST.MF文件，这个应该是个IDEA的BUG（参考：http://stackoverflow.com/questions/15724091/how-to-run-a-jar-file-created-using-intellij-12），配置完成后如下图所示，点击OK进入下一步。我个人建议选择“extract to the target JAR”，这样所有依赖的jar包都会放在生成的jar包中。

5. 完成后，点击OK，Apply等按钮，回到IDEA的主菜单，选择“Build - Build Artifacts”下的“Build”或者“Rebuild”即可生成最终的可运行的jar，在D:\Intellij\SeriesPublish\out\artifacts\SeriesPublish_jar下面找到生成的目标jar，可以看到META-INF/MAINFEST.MF文件被正确包含，内容也正确。

好了，大功告成
参考：
http://bglmmz.iteye.com/blog/2058785
http://blog.csdn.net/xiao257/article/details/52981891
http://www.cnblogs.com/blog5277/p/5920560.html
————————————————
版权声明：本文为CSDN博主「爆米花9958」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/xuemengrui12/java/article/details/74984731
