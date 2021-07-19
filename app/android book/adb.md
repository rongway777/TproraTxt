### ADB OK

#### 组件

三个组件。

- 客户端：	发送命令。
- 守护程序adbd：设备后台**进程**。
- 服务器：	客户端这边的**进程**。TCP端口为：5037 ps-ef | grep adb可以看到。

#### 原理

- 启动某个adb客户端时候，检查有没有服务器进程。没有则开启。端口为**5037**。
  - studio启动的时候会**自动**开启adb服务器进程。
- adb进程会与所有正在运行的设备建立连接（**与adbd端口进行连接**）。扫描端口5555到5585（提供16个模拟器使用）。每个模拟器配两个端口。**一奇（adb连接端口，adbd端口**）一偶（控制台连接，adb devices显示的那个）。
  - 例如模拟器1：控制台：5554。adbd：5555。这两个端口对应的是一个模拟器。
  - 如果外部模拟器（本机上）**不在5555~5585之间**，需要adb connect连接。
  - 连接外部设备（外部电视，手机）。看下面的步骤。
- 连接完成。

#### 通过WIFI连接到设备（android11以及以上版本）

1. 在设备上打开**开发者选项**。
2. 启用**无线调试选项**。
3. 使用**配对码配对设备**。
4. **adb pair ip:port**
5. 输入配对码。
   1. 成功的话显示Successfully paired to 192.168.1.130:37099 [guid=adb-235XY]
6. **adb connect ip:port**
7. 连接完成。

#### adb命令

查看当前连接的设备。**OK**

```
adb devices -l
```

如果发现多个设备 **OK**

```
adb -s 设备号 其他指令
例如：adb -s devices1 install xxx.apk
			 adb -s emulator-5556 push userinfo.txt /storage/emulated/0/Download
```

查看日志 **OK**

```
adb logcat
```

安装APP **OK**

```
adb install xxx.apk 存在的话无法安装
adb install -r xxx.apk 覆盖安装
```

卸载APP **OK**

```
abd uninstall com.xxx.xxx.app  不保留数据
adb uninstall -k com.xxx.xxx.app 保留数据
```

推送数据 **OK**

```
adb push ~/xxx.txt   /storage/emulated/0/MyData
```

拉取数据 **OK**

```
adb pull /storage/xxx.txt ./xx.txt 另存为。否则原文件拉下来。
```

停止adb  **OK**

```
adb kill-serve
```

#### shell命令

进入shell **OK**

```
adb shell
或者adb shell +linux命令
```

 查看所有的app包名 **OK**

```
pm list packages 
```

activity管理器（am）暂时先这样，很复杂Intent。Activity的启动问题。 OK

```
am start com.example.apkdemo/com.example.apkdemo.MainActivity 启动一个app的MainActivity。  
```

软件包管理器（pm）

卸载APP，需要完整的包名。

```
pm uninstall com.xx.xx.xxxx 安装需要apk
```

截图

```
screencap /sdcard/......./xxx.png  截图
to adb:adb pull /sdcard/......./xxx.png ~/图片/xx.png  拉取下来。
```



### emulator

查看所有模拟器 **OK**

```
emulator -list-avds
```

### Logcat

logcat输出到文件

```
adb logcat > log.txt
```

过滤日志输出：

从指定时间开始输出

```
adb logcat -t '07-14 17:25:00.000'
```

过滤

logcat优先级：从低到高。
V：所有的。

D：调试。

I：info信息。

W：警告。

E：错误。

F：严重错误。

S：静默。

1.设置环境变量

.bashrc文件当中配置。
**TAG：priority <space> xx:priority *:S**
priority优先级以下的都会被输出。

```
export ANDROID_LOG_TAGS="SecondActivity:I ApkDemo:I *:S"  
I的话，I W E F S都会被输出。
```

使用

```
adb logcat $ANDROID_LOG_TAGS > xx/xx/log.txt
```

