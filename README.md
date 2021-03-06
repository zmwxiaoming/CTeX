CTeX Maintenance Plan  
====
如何自动编译：  

1. 下载 MiKTeX: [32-bits](http://mirrors.ctan.org/systems/win32/miktex/setup/basic-miktex-2.9.5872.exe):[64-bits](http://mirrors.ctan.org/systems/win32/miktex/setup/basic-miktex-2.9.5872-x64.exe)
2. 安装 MiKTeX: 安装时选择「Only for: %USER%」
3. 将整个安装目录下的文件，复制到 `./install/Full/MiKTeX`
4. 将整个 `./install/Full/` 目录下的文件，移动到 `./install` 下；注意 `./install/Full` 目录本身不可删除（但可以为空）
5. 双击 `./CTeX_Build.exe` 准备编译，勾选 `1`/`3` 复选框，`4`/`5` 按需选择
6. 点击 `install` 开始编译。
7. 到 output 目录下找到输出文件  

![qq20160220-0 2x](https://cloud.githubusercontent.com/assets/3348485/13194540/0ed7ca38-d7d0-11e5-8c3e-827134e34c3f.png) 

如何手工编译:  
0. 下载并安装 NSIS 3.0b3  
1. 下载启用 Advance Log 的 NSIS 3.0b3 （即覆盖进 NSIS 安装目录） http://prdownloads.sourceforge.net/nsis/nsis-3.0b3-log.zip?download   
2. 把本 repo 中 libs\external\Textreplace.zip 中的内容解压到 NSIS 程序目录下  
3. 执行以下命令： `makensis.exe /INPUTCHARSET UTF8 /OUTPUTCHARSET UTF8 /DDEBUG filename.nsi`  
4. 若需详细编译过程可使用 /V4 开关，但是会严重影响编译速度  
5. 若需发布则去掉 /DDEBUG 开关，并 install\Full 下面的文件夹移动到 install 下，删除所有的dummy.txt

目前已完成：  
- [x] 所有脚本UTF-8化  
- [x] 包含最新版的 Ghostview 和 GSView  
- [x] 加入 WinEdt 10.0，并问作者要到了授权
- [x] 重绘图标（偷懒不加上 CTeX 字样了）
- [x] 重绘安装包的 Banner    
- [x] 重建目录结构（现在的 install 目录即要被打包的文件，但为了加快打包测试速度所有目录都是空的，真正的文件都在 Full 目录下，正式打包时移动即可）  
- [x] 在工作目录中包含一个最小化的 _自编译版_ NSIS ，打开了长字符串和日志支持，只保证可以正确编译本项目。
- [x] Patch WinEdt（加入 CTeX_Tools 菜单以及一些工具）
- [x] 加入MiKTeX 的必要部分（<https://github.com/Harry-Chen/CTeX/blob/master/required_packages.txt>） 
- [x] 测试 CJK 是否可以使用 
- [x] 解决 zhmCJK 无法使用的问题
