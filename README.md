## Install Goole Protobuf & RabbitMQ C++ Client



### __1. Install CMAKE__ </br> 
Go to CMake Download [https://cmake.org/download/](https://cmake.org/download/) 
下载Binary Distribution Installer

<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture.PNG" width="700" height="350">

下载之后打开 选择 add Cmake to the system PATH for current / all users
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/screenshot_cmake01.png" width="400" height="300">

安装后之后点cmake Gui 就可以使用了

### __2. Download & Install Google Protobuf__ [参考](https://blog.csdn.net/qing666888/article/details/79137963) </br> 
[Go to CMake Download](https://github.com/google/protobuf/releases/tag/v3.6.0)
<ol type = "a"><li>. 选择cpp.zip，下载，之后解压</br> 

<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/20180123115438747.png" width="470" height="270">

</li><li>打开第一步装好的GUI 如下图先选择folder</br>
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/20180123123624043.png" width="470" height="450">

</li><li>第三步的时候注意选择visual studio 15 2017</br>
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/20180123123851718.png" width="400" height="270">

</li><li>点击Finish后进行参数配置。可以配置生成为动态库工程</br>
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/20180123141331970.png" width="490" height="330">


</li><li>装好之后，会生成一个带sln 和很多VC++ project的文件在文件夹中</br>
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture2.PNG" width="480" height="230"></li></ol>

### __3. Compile protobuf.sln__  [参考](https://www.youtube.com/watch?v=Vs-nTZb7oj8) </br> 

<ol type = "a"><li>在生成的文件夹里打开protobuf.sln,  然后build libprotobuf, libprotoc, protoc
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture3.PNG" width="380" height="230">

</li><li>build成功后，会在debug里面有个protoc.exe生成</br>
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture4.PNG" width="400" height="250"></li></ol>

### __4. Generate C++ Protobuf Source Code__  [参考](https://www.youtube.com/watch?v=lM51aOLHiCY) </br> 
a.把上一步debug的所有file 复制到包含.proto的子文件夹</br> 
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture5.PNG" width="380" height="230"></br>
b. 打开cmd, cd现在的文件夹, 再输入protoc -I=. --cpp_out=. A.proto, .代表current directory
```C++
> cd "C:\proto"
> protoc -I=. --cpp_out=. A.proto
或者用
> protoc -I=$SRC_DIR --cpp_out=$DST_DIR $SRC_DIR/addressbook.proto
```
<img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture6.PNG" width="400" height="100">

c. 一个.pb.cc 和一个.pb.h 就会生成在directiory 文件夹里面</br> 
  <img src="https://github.com/beckswu/Cplusplus-notes/blob/master/pic/Capture7.PNG" width="600" height="150">

### __5. Install Rabbitmq C (using vcpkg)__

```
use powershell 

cd "C:\vcpkg"
.\vcpkg install librabbitmq:x86-windows

```

### __6. Install Simple AMQP Client C++__

```
use powershell 

git clone git://github.com/alanxz/SimpleAmqpClient.git
cd SimpleAmqpClient
git submodule init
git submodule update

cd C:\
mkdir simpleamqpclient-build
cd C:\Divisa\simpleamqpclient-build

cmake -DBOOST_ROOT=C:\vcpkg\installed\x86-windows -DBOOST_INCLUDEDIR=C:\vcpkg\installe
d\x86-windows\include\boost -DBOOST_LIBRARYDIR=C:\vcpkg\installed\x86-windows\lib -DRabbitmqc_ROOT=C:\vcpkg\installed\x86-w
indows  -DRabbitmqc_INCLUDE_DIR=C:\vcpkg\installed\x86-windows\include -DRabbitmqc_LIBRARY=C:\vcpkg\packages\librabbitmq_x8
6-windows\lib  C:\SimpleAmqpClient

//需要list path的位置，有可能找不到

```

