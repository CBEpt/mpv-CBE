# mpv-CBE  
这是一个面向小白的mpv整合包~！ 我也是小白！Always learning!   
不敢保证功能都是稳定的奥，不过比potplayer内置渣渣滤镜什么的强多了，并不用复杂设置，解压即用，开源，mvtools法一键倍帧，免费，不需要SVP4（当然也可以往上加，自己研究）
# 第一次使用  
建议把压缩包里面所有东西解压到如C:/mpv  
修改任何配置, 请编辑mpv目录下的```portable_config/mpv.conf```  
修改任何快捷键关联, 请编辑mpv目录下的```portable_config/input.conf```，推荐使用[Notepad3](https://www.rizonesoft.com/downloads/notepad3/)进行编辑，更加可视化，有颜色指示  
特性：  
- 一键倍帧  
- 动漫一键去锯齿，简单来讲就是清晰化，采用anime4k着色器实现  
- 截取适合pt发布用途的png截图，以及gif，默认发送到桌面
  
# 此包创造之源
- 本mpv win 基础包来源于dyphire的mpv构建：[dyphire/mpv_config](https://github.com/dyphire/mpv-winbuild)下的[release](https://github.com/dyphire/mpv-config/releases)下的2023.02.12 mpv整合包：[mpv_config-latest.7z](https://github.com/dyphire/mpv-config/releases/download/mpv_config-latest/mpv_config-latest.7z)  
- 根据[hooke007的滤镜安装教程](https://hooke007.github.io/unofficial/mpv_start.html#vapoursynth)  
下载了[MPV_lazy的mvtools倍帧vpy脚本](https://github.com/hooke007/MPV_lazy/blob/main/portable_config/vs/mvtools_2x.vpy)  
以及下面的三个包  
![image](https://user-images.githubusercontent.com/103420806/214845172-bdfe743a-e733-439f-ade6-18dc23f9b189.png)  
解压到了mpv文件夹，实现了倍帧功能。  
- portable_config配置文件夹跟随 [dyphire / mpv-config](https://github.com/dyphire/mpv-config)的最新commit, 只修改了快捷键，如下：  

# 快捷键指南
基于[dyphire的mpv-config](https://github.com/dyphire/mpv-config)修改了一些快捷键关联
- 2是滤镜：倍帧（记忆方法：2倍于原帧数，所以是ctrl+2)，关闭：再按一次2  
- 4是着色器：动漫抗锯齿（记忆方法：Anime4K里面有个4，所以ctrl+4)，关闭：再按一次4  
- TAB，就是你大写锁上面的那个键，打开osc文件浏览器（基本选择什么文件，操作都不依赖鼠标）
- a, audio, 打开osc音轨列表
- s, subtitle，打开osc字幕轨列表
- c, chapter，打开osc章节列表（视频含有章节才有效奥），另外HOME是上一个章节，END是下一个章节
- d, directory/定位，打开当前播放文件的目录
- w指定gif开始截取的地方，W指定结束的地方（注意是大W，先按一下键盘上的大写锁Capslock），然后CTRL+W(注意这里我修改为还是大W）截取gif。目前建议截取不带字幕的gif.
- l, 即last，在打开mpv显示黑界面的时候用，可以快速回到上一次播放的文件及进度
- b, 老板键? 快速最小化
- q, quit, 一键退出
- r字幕下移，t字幕上移，j字幕缩小，k字幕放大，```，``` ```。```逐帧前后进，↑为前进一分钟，↓为后退一分钟，←为回退五秒，→为前进五秒
- ```[```  速度-0.1x,   ``` ]```速度+0.1x


# 一些设置的修改指南
基于[dyphire的mpv-config](https://github.com/dyphire/mpv-config)修改了一些设置  
- mpv窗口默认不置顶, 修改请找到mpv目录下的```portable_config/mpv.conf```，功能分区里```title=```这一行加上```${?ontop==yes:📌}```  
- 默认设备是双声道，执行动态映射下混，如果你用的是5.1/7.1，请到mpv目录下```portable_config/mpv.conf```里面找到这一行，  
audio-channels=stereo                 # <默认值auto-safe|auto|layouts|stereo>，如果双声道系统播放多声道影片时有的声道声音没出现，尝试强制设定为双声道  
进行修改，将```stereo```修改为```7.1,5.1,stereo```, mpv将自动寻找适配到7.1或5.1  
- 小白请这样更改解码方式  
用记事本打开mpv目录下的```portable_config/mpv.conf```  
找到这一行：```hwdec=nvdec-copy```  
更改```hwdec=```后面的值，以指定应使用的硬件视频解码API：  
软解请改为```no```，硬解建议使用```auto-copy```或```d3d11va-copy```。10系以上N卡建议使用```nvdec-copy```，图灵架构及之后的N卡使用nvdec-copy时可硬解yuv444  
- 还修改了状态栏的标题以及uosc, 懒得写怎么改回去了，很简单，自己发现吧
- mpv汉化教程指南：https://hooke007.github.io/
# dev分支
可能会推送一些奇奇怪怪的东西。
