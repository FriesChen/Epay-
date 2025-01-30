易支付2024年12月份新版
安装环境
1.php>=8.0
2.sql 不限
3.可用内存>=1G

开始安装：
访问http://你的域名/install

安装完成：
默认账号密码
admin
123456

伪静态
location / {
 if (!-e $request_filename) {
   rewrite ^/(.[a-zA-Z0-9\-\_]+).html$ /index.php?mod=$1 last;
 }
 rewrite ^/pay/(.*)$ /pay.php?s=$1 last;
 rewrite ^/api/(.*)$ /api.php?s=$1 last;
 rewrite ^/doc/(.[a-zA-Z0-9\-\_]+).html$ /index.php?doc=$1 last;
}
location ^~ /plugins {
  deny all;
}
location ^~ /includes {
  deny all;
}
