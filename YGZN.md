### 在Ubuntu安装使用mosquitto
- sudo apt-get install mosquitto   安装mosqitto
- sudo apt-get install libmosquitto-dev  安装mosquitto开发包
- sudo apt-get install mosquitto-clients 安装mosquitto客户端
- sudo service mosquitto status  查询mosquitto是否正确运行
### 本机测试
- mosquitto_sub -h localhost -t "mqtt"-v  打开一个终端，执行以下命令订阅主题"mqtt"
- mosquitto_pub -h localhost -t "mqtt"-m "Hello MQTT"   打开另外一个终端，发布消息到主题 “mqtt”
### 网络测试（test.mosquitto.org）
- 从test.mosquitto.org订阅所有主题，任何人发布的任何消息你都可以收到，你会看到大量有趣消息滚动在你的屏幕上。
- mosquitto_sub -h test.mosquitto.org -t "#" -v  发布消息
- mosquitto_sub -h test.mosquitto.org -t "msg_only_from_me" -v  订阅特定主题
- mosquitto_pub -h test.mosquitto.org -t "msg_only_from_me" -m "My cat is Luna" 另外一个终端上发布消息到特定主题，消息"My cat is Luna"应该会显示在上一个终端上




- test.mosquitto.org 支持加密和不加密MQTT消息模式，也支持用TCP或者Websocket作为承载，可以通过wireshark抓包来观察不同的包格式.
