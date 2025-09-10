具体解决方案

1‌.注册表修改法（推荐）‌。

按下Win+R输入regedit打开注册表编辑器。
定位路径：:ml-search-more[HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\AppXSvc]{text="HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\AppXSvc 位置"}
将右侧Start键值从3修改为4‌
重启系统后服务将永久禁用。
‌

2.组件修复方案‌。
部分win10安装后wsappx进程始终占用一个cpu核心问题
部分用户遇到安装特定win10版本后登录到桌面cpu始终有个核心被wsappx进程跑满，查看appx相关日志发现日通有关于VCLibs依赖库缺失的报错导致系统循环初始化appx应用，安装下面的依赖可以解决此问题：

适用于LTSC等无应用商店版本：
下载Microsoft.VCLibs库文件。
通过PowerShell执行：
Add-AppxPackage -Path "Microsoft.VCLibs.140.00_14.0.30704.0_x64__8wekyb3d8bbwe.Appx"
