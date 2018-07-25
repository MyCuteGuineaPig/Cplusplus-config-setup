## Install Goole Protobuf



### __1. Install CMake__, </br> 
Go to CMake Download [https://cmake.org/download/](https://cmake.org/download/) 
下载Binary Distribution Installer

<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture.PNG" width="700" height="350">

下载之后打开 选择 add Cmake to the system PATH for current / all users
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/screenshot_cmake01.png" width="400" height="300">

安装后之后点cmake Gui 就可以使用了

### __2. Download & Install Google Protobuf__ , 
[参考](https://blog.csdn.net/qing666888/article/details/79137963) </br> 
<ol><li>
Go to CMake Download [https://github.com/google/protobuf/releases/tag/v3.6.0](https://github.com/google/protobuf/releases/tag/v3.6.0) </br> 
选择cpp.zip，下载，之后解压</br> 

<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/20180123115438747.png" width="470" height="270">

</li><li>打开第一步装好的GUI 如下图先选择folder</br>
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/20180123123624043.png" width="470" height="450">

</li><li>第三步的时候注意选择visual studio 15 2017</br>
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/20180123123851718.png" width="400" height="270">

</li><li>点击Finish后进行参数配置。可以配置生成为动态库工程</br>
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/20180123141331970.png" width="490" height="330">


</li><li>装好之后，会生成一个带sln 和很多VC++ project的文件在文件夹中</br>
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture2.PNG" width="480" height="230">

</li></ol>
### __3. Compile protobuf.sln__
[参考](https://www.youtube.com/watch?v=Vs-nTZb7oj8) </br> 
<ol><li>在生成的文件夹里打开protobuf.sln,  然后build libprotobuf, libprotoc, protoc
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture3.PNG" width="480" height="230">

</li><li>build成功后，会在debug里面有个protoc.exe生成</br>
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture4.PNG" width="480" height="230">

</li></ol>
