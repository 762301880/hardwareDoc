# 中文文档

| 名称              | 地址                                                         |
| ----------------- | ------------------------------------------------------------ |
| espressif中文文档 | [link](https://docs.espressif.com/projects/esp-dev-kits/zh_CN/latest/esp32s3/index.html) |
| esp32开发板选型   | [link](https://docs.espressif.com/projects/esp-techpedia/zh_CN/latest/esp-friends/get-started/board-selection.html) |
| 第三方博客        | [link](https://docs.geeksman.com/esp32/Arduino/01.esp32-arduino-intro.html) |



# 开发工具

##  Arduino IDE

到官网下载安装最新版本：
 👉 https://www.arduino.cc/en/software

安装好后打开 Arduino IDE。

### 添加 ESP32 开发板支持

1. 打开菜单：

   ```
   文件 → 首选项（Preferences）
   ```

2. 在「附加开发板管理器网址」中，粘贴以下内容：

   > https://mc.dfrobot.com.cn/thread-324941-1-1.html

   ```
   https://dl.espressif.com/dl/package_esp32_index.json
   https://espressif.github.io/arduino-esp32/package_esp32_dev_index_cn.json
   ```

3. 点击确定后，进入：

   ```
   工具 → 开发板 → 开发板管理器
   ```

4. 搜索 **esp32**，然后点击安装 “**esp32 by Espressif Systems**”。

### 选择你的开发板

安装完成后，在菜单中选择：

```
工具 → 开发板 → ESP32 Arduino → ESP32S3 Dev Module
```

![image-20251106113106026](https://gitee.com/yaolliuyang/blogImages/raw/master/blogImages/image-20251106113106026.png)

然后选择你的串口：

```
工具 → 端口 → COMx（通常会显示你的开发板名）
```

#  开发

## helloworld

> typec插右边那个  上传完毕后
>
> 选择**工具-串口监视器   波特率设置为 115200**  可以看到输出

```php
// 初始化函数，程序上电或复位后只运行一次
void setup() {
  // 初始化串口通信，设置波特率为115200（ESP32-S3常用的通信速率）
  // 波特率需与串口监视器设置一致，否则会出现乱码
  Serial.begin(115200);
  
  // 通过串口发送字符串"Hello, ESP32-S3!"并换行
  // 用于验证串口通信是否正常，也可作为程序启动的标志
  Serial.println("Hello, ESP32-S3!");
}

// 主循环函数，setup()执行完毕后会无限重复运行此函数内的代码
void loop() {
  // 延时10毫秒（1秒=1000毫秒）
  // 注释中提到"this speeds up the simulation"是指在仿真环境中
  // 适当的短延时可以避免程序过度占用仿真资源，让仿真更流畅
  delay(10); 
}
```

