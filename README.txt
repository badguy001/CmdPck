此插件解决PL/SQL Developer中COMMAND窗口执行创建大的PACKAGE时非常慢的问题

使用方法：

1.将cmdPck.dll文件拷贝到PL/SQL Developer安装目录的PlugIns文件夹里面，需要重启PL/SQL Developer才会加载插件

2.(可选)创建编辑%USERPROFILE%/cmdpck/config.ini文件配置.pck文件存放的路径，例如.pck文件存放在d:/pck，则文件的内容为 d:/pck
没有配置的话，默认文件夹为C:/pckdir

3.将.pck文件放在第2步配置的文件夹内（默认文件夹为C:/pckdir）

4.在COMMAND窗口执行下面命令
plugin cmdpck pck的文件名(不包含文件夹名字)

5.PL/SQL Developer会自动打开pck文件(以PROGRAM窗口打开)，并执行它


例如:
1).没有配置%USERPROFILE%/cmdpck/config.ini文件，没有此文件或者此文件内容为空的
        plugin cmdpck abc.pck   -->   则插件会以porgram窗口打开C:/pckdir/abc.pck文件，并执行
        plugin cmdpck 20220308/abc.pck   -->  则插件会以porgram窗口打开C:/pckdir/20220308/abc.pck文件，并执行


1).%USERPROFILE%/cmdpck/config.ini文件内容为D:/pck
        plugin cmdpck abc.pck   -->   则插件会以porgram窗口打开D:/pck/abc.pck文件，并执行
        plugin cmdpck 20220308/abc.pck   -->  则插件会以porgram窗口打开D:/pck/20220308/abc.pck文件，并执行
