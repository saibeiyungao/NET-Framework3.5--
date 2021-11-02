## win10 NET Framework3.5安装教程

 

***电脑连互联网***

 

1. 用dotnetfx_cleanup_tool工具清除已安装的net framework，计算机自动重启

  

2. 打开注册表：```win+r``` 输入```regedit```，确定；找到路径

```HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU```，UseWUServer默认值改成0；

 

打开注册表时可直接输入以下代码，可快速定位需要修改的地方

```计算机\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU```

 

3. ```win+r```,输入```services.msc```，打开服务列表，重启Windows Update service；

  

4. NetFx3.cab离线安装包copy到C:\Windows

 

5. 搜索cmd，选择`以管理员身份运行`，在cmd对话框执行如下命令

```dism.exe /online /enable-feature /featurename:NetFx3 /Source:C:\WINDOWS\netfx3.cab```

或者（自动去下载）

```dism.exe /online /enable-feature /featurename:NetFx3 /Source:C:\WINDOWS\microsoft-windows-netfx3-ondemand-package.cab```

 

6. 看到进度条100%并有“操作成功完成”字样，就成功了。重启电脑ok