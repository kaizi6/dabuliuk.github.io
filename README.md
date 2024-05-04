# xiaokai.github.io
连接之前先做好准备工作:
1、电脑USB可以正常识别；2、手机需进入开发者选项并打开USB调试功能（手机版本号连续点击即可）；
3、明确scrcpy所在地址并在此地址栏中打开cmd命令提示符（还可使用win+R调出窗口后再去进行路径访问）；
4、确保手机正常连接到adb驱动并可以使用adb来对手机进行调试；
5、数据线具有充电和传输数据两种功能并打开USB调试
上述为准备工作；
有线连接：
在路径下的路径栏中运行cmd，插入数据线并键入scrcpy之后回车即可；
无线连接：
1、先接入数据线并连接到电脑；
2、在源路径栏下进入cmd命令提示符，键入adb tcpip 5555；
当提示restarting in TCP mode port:5555之后第一步准备完成；
3、之后键入adb connect 本机IP:5555；
当提示connected to 本机IP:5555（connected 这里指连接到....)之后即可或restarting in TCP mode port: 5555时；
4、拔掉数据线输入scrcpy回车即可；
常见问题：
当键入scrcpy后提示ERROR: Multiple (2) ADB devices:
ERROR:     -->   (usb)   本地连接识别码      device  手机型号
ERROR:     --> (tcpip)   本机IP:端口        device  手机型号
ERROR: Select a device via -s (--serial), -d (--select-usb) or -e (--select-tcpip)
ERROR: Server connection failed（连接失败提示）时：
第一种方法为：拔掉手机数据线再次进行连接即可连接到无线连接；
（如第一种方法行不通）使用第二种方法：（根据命令行提示可以得出-d为单独连接USB设备；-e为单独连接局域网
连接）想无线传输可以采用scrcpy-e来实现，反之想通过USB连接可以采用scrcpy-d来实现，前提需要看明白自己连接的渠道到底是哪一个；
（如果先用USB连接，但是接入之后还是不可用）使用第三种方法：（删除adb设备）USB连接电脑，手机网络关闭之后
用scrcpy测试是否为不可使用，当提示不可使用时键入adb devices来检测当前连接连接adb设备状态当提示：
List of devices attached
本地连接识别码 device（在线）
本机IP:端口     offline（离线）之后键入adb kill-server(关闭服务器）等待，当再次出现命令提示行时，成功关闭服务器，可以自己再次输入adb devices来验证是否关闭服务器，再次进行scrcpy运行即可顺利运行





如有侵权请联系作者删除
作者：3420713723
