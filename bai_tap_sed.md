# Bài tập về `sed`
>### **File mẫu**
```
# vi filethuchanh.conf
```
```
# Configuration for sending metrics to InfluxDB
[[outputs.influxdb]]
  ## The full HTTP or UDP URL for your InfluxDB instance.
  ##
  ## Multiple URLs can be specified for a single cluster, only ONE of the
  ## urls will be written to each interval.
  # urls = ["unix:///var/run/influxdb.sock"]
  # urls = ["udp://127.0.0.1:8089"]
  # urls = ["http://127.0.0.1:8086"]

  ## The target database for metrics; will be created as needed.
  ## For UDP url endpoint database needs to be configured on server side.
  # database = "telegraf"

  ## The value of this tag will be used to determine the database.  If this
  ## tag is not set the 'database' option is used as the default.
  # database_tag = ""

  ## If true, no CREATE DATABASE queries will be sent.  Set to true when using
  ## Telegraf with a user without permissions to create databases or when the
  ## database already exists.
  # skip_database_creation = false

  ## Name of existing retention policy to write to.  Empty string writes to
  ## the default retention pol
  
  # # Read metrics about network interface usage
# [[inputs.net]]
#   ## By default, telegraf gathers stats from any up interface (excluding loopback)
#   ## Setting interfaces will tell it to gather these explicit interfaces,
#   ## regardless of status.
#   ##
#   # interfaces = ["eth0"]
#   ##
#   ## On linux systems telegraf also collects protocol stats.
#   ## Setting ignore_protocol_stats to true will skip reporting of protocol metrics.
#   ##
#   # ignore_protocol_stats = false
#   ##
.  Only takes effect when using HTTP.
  # retention_policy = ""

  ## Write consistency (clusters only), can be: "any", "one", "quorum", "all".
  ## Only takes effect when using HTTP.
  # write_consistency = "any"

  ## Timeout for HTTP messages.
  # timeout = "5s"

  ## HTTP Basic Auth
  # username = "telegraf"
  # password = "metricsmetricsmetricsmetrics"

# # Read metrics about network interface usage
# [[inputs.net]]
#   ## By default, telegraf gathers stats from any up interface (excluding loopback)
#   ## Setting interfaces will tell it to gather these explicit interfaces,
#   ## regardless of status.
#   ##
#   # interfaces = ["eth0"]
#   ##
#   ## On linux systems telegraf also collects protocol stats.
#   ## Setting ignore_protocol_stats to true will skip reporting of protocol metrics.
#   ##
#   # ignore_protocol_stats = false
#   ##
```
> Thay thế dòng `# urls = ["http://127.0.0.1:8086"]` bằng dòng mới `urls = ["http://192.168.69.69:8086"]`
- Sử dụng lệnh :
    ```
    # sed -i 's/# urls = \["http:\/\/127.0.0.1\:8086"\]/urls = \["http:\/\/192.168.69.69\:8086"\]/g' filethuchanh.conf 
    ```
    <img src=https://i.imgur.com/v2xw8br.png>

> Thay dòng `# [[inputs.net]]` bằng dòng `[[inputs.net]]`
- Sử dụng lệnh :
    ```
    # sed -i 's/# \[\[inputs.net\]\]/\[\[inputs.net\]\]/g' filethuchanh.conf
    ```
    <img src=https://i.imgur.com/uhb7mcI.png>

> Thay dòng `# username = "telegraf"` bằng dòng `username = "nguoidung@hocchudong.com"`
- Sử dụng lệnh :
    ```
    # sed -i 's/# username = "telegraf"/username = "nguoidung@hocchudong.com"/g' filethuchanh.conf
    ```
    <img src=https://i.imgur.com/oWqtEyL.png>

> Thay dòng `# password = "metricsmetricsmetricsmetrics"` bằng dòng `password = "Matkhau@ok$#`
- Sử dụng lệnh :
    ```
    # sed -i 's/# password = "metricsmetricsmetricsmetrics"/password = "Matkhau@ok$#/g' filethuchanh.conf
    ```
    <img src=https://i.imgur.com/uRJVZM1.png>