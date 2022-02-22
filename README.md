# thinglinks-mqtt-c
开源ThingLinks物联网一体化平台MQTT客户端， 用于 Windows、Linux 和 MacOS 的 MQTT 的 C 客户端库
## 快速入门
### 1. 编译环境及编译链,
        Ubuntu 16 、  GCC
### 2. 编译指令
        make && make install
### 3. 生成的动态库文件以及测试样例执行文件
        build/output           包含libpaho-mqtt3a.so*/libpaho-mqtt3as.so*/libpaho-mqtt3ac.so*
        build/output/samples   包含测试所用的执行文件，可连接mqtt平台、订阅消息、发布消息
### 4. 测试进程paho_cs_pub、paho_cs_sub、paho_c_sub、paho_c_pub 的参数解读
        用法：[topicname] [-t topic] [-c connection] [-h host] [-p port]
       [-q qos] [-i clientid] [-u username] [-P password] [-k keepalive_timeout]
       [-V MQTT-version] [--quiet] [--trace trace-level]
       [-R] [--no-delimiter]
       [--will-topic topic] [--will-payload message] [--will-qos qos] [--will-retain]
       [--cafile filename] [--capath dirname] [--cert filename] [--key filename]
       [--keypass string] [--ciphers string] [--insecure]

          -t（--topic）：要订阅的MQTT主题名称

          -c（--connection）：连接字符串，覆盖主机/端口。

          -h（--host）：要连接的主机。默认值为localhost。

          -p（--port）：要连接的网络端口。默认为1883年。

          -q（--qos）：使用（0、1或2）订阅的MQTT qos。默认值为0。

          -V（--MQTTversion）：MQTT版本（31、311或5）。默认值为311。

          --quiet：不要打印错误消息。

          --trace：打印内部跟踪（“错误”、“最小”、“最大”或“协议”）。

          -i（--clientid）：MQTT客户端id。默认值为paho-cs-sub。

          -u（--username）：MQTT用户名。没有违约。

          -P（--password）：MQTT密码。没有违约。

          -k（-keepalive）：MQTT keepalive超时值。默认值为10秒。

           --delimiter：分隔符字符串。默认值为\n。
           
           --no-delimiter ：不要在消息之间使用分隔符字符串。

          -R（--无保留）：不打印保留的消息。

          --will-topic ：威尔主题连接。没有违约。

          --will-payload：威尔消息。如果设置了will主题，但未设置有效负载，则会设置一条空消息。

          --will retain（将保留）：在will消息上设置保留标志。默认设置为关闭。

          --will qos：will消息qos。默认值为0。

          --cafile：TLS信任库的文件名。

          --capath：包含TLS受信任服务器证书的目录名。

          --cert：包含客户端证书的TLS密钥库的文件名。

          --key：客户端私钥文件。

          --keypass：客户端私钥文件的密码。

          --ciphers：客户机将在运行期间向服务器提供的密码套件列表TLS握手。

           --insecure：不要检查服务器证书是否为公共名称

          --psk：十六进制的预共享密钥（无前导0x）

          --psk-identity：TLS-psk模式的客户端标识字符串。

          --http-proxy：http代理字符串。

         --https-proxy：https代理字符串。
### 5. 测试进程使用实例
       连接mqtt平台，并订阅test主题消息
       paho_cs_sub  -v -h  113.90.145.99 -p 18886  -u smqtt -P smqtt -i 123456 -t test   
       
       连接mqtt平台，并向test主题发送消息，发送的主题消息内容可以通过键盘输入
       paho_cs_pub -v -h 113.90.145.99 -p 18886 -u smqtt -P smqtt -i 12345678 -t test
       
