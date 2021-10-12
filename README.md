# EasyWordPressDockerImage

## 最大上传文件等参数的修改

默认的wordpress镜像文件上传只有2M，本镜像进行了修改。

```ini
file_uploads = On
memory_limit = 500M
upload_max_filesize = 500M
post_max_size = 500M
max_execution_time = 600
```

可修改 <uploads.ini> 自定义相关值

## 启动镜像

### 不需要支持 SSL 证书的情况

1. 运行命令启动 `docker-compose up -d `

### 需要支持 SSl 证书的情况

1. 申请 SSL 证书(不会的同学请自行搜索教程，下载Apache格式的)，会获得两个文件，一个是证书文件(第一行为`-----BEGIN CERTIFICATE-----`)，一个是私钥文件(第一行为`-----BEGIN RSA PRIVATE KEY-----`)
2. 将证书文件和私钥文件的内容分别填入到 `docker/wordpress/ssl.crt` 和 `docker/wordpress/ssl.key` 中
3. 运行命令启动 `docker-compose -f docker-compose.ssl.yml up -d  --build `





