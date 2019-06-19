##  **Django+uwsgi+Nginx**

### **一、确保Django项目能在本地运行**

1、在pycharm，或者python环境Django项目能够启动并且能够浏览器访问

```python
python3 manage.py runserver   #默认启动项

python3 manage.py runserver 9000    #当端口被占用时，可以指定端口

python3 manage.py runserver 0.0.0.0:8000   #监听ip
```



#### **二、安装uwsgi，安装nginx**

​	**1、安装uwsgi**

pip安装

​	`pip install uwsgi`

源码安装

​	`tar zxvf uwsgi-2.0.9.tar.gz`

​	`cd uwsgi-2.0.9`	 #cd 到解压后的目录

​	`make`  #执行make安装

​	安装后检查一下是否成功

​	`uwsgi --version`  #查看uwsgi版本

​	**2、安装nginx**

​	`brew install nginx`  #也可gz包安装

gz包安装

```
cd /usr/local/src                       #进入到安装目录
tar -zxvf nginx-1.1.10.tar.gz           #解压gz包，tar -zxvf gz包路径 加文件名
cd nginx-1.1.10                         #进入解压后的文件夹
./configure                             #编译
make                                    #安装
make install
```

### **三、编写uwsgi.ini文件**

```python
[uwsgi]

# Django-related settings
#http=127.0.0.1:8111       #配置http时uwsgi可以单独使用
socket= 127.0.0.1:8111

# the base directory (full path)
chdir= /Users/admin/Desktop/项目1/代码/GuLiEdu

# Django s wsgi file
module= GuLiEdu.wsgi:application
#wsgi-file= GuLiEdu/wsgi.py:application
# process-related settings
# master允许主线程存在
master= true

# maximum number of worker processes 开启的进程数量
processes= 4
threads=4  #配置线程数量
# ... with appropriate permissions - may be needed
# chmod-socket    = 664
# clear environment on exit自动清理环境
vacuum= true
#静态文件
#static-map= /Users/admin/Desktop/项目1/代码/GuLiEdu/static
#daemonize=/data/log/uwsgi/app.log   #输出日志文件
```



### **四、测试uwsgi**

`uwsgi —ini uwsgi.ini` 浏览器进行访问

### **五、测试nginx**

`./nginx`	启动

访问本地ip加默认端口8080

出现welcome to nginx

### 六、配置nginx

```
server {
    listen 8080;
    server_name www.wenxi.xin 　　　　#这个是什么都无所谓，只是一个名称标记，虫师说他的要写成ip，这个应该不用，因为这个就相当于server ID,写入log
    charset UTF-8;
    client_max_body_size 75M;
    location / {

        include uwsgi_params;　　　　　　#加载uwsgi
        uwsgi_pass 127.0.0.1:8111;     #是uwsgi 启动的socket端口， 即 uwsgi.ini 中的socket，应该也可以生成个socket文件，然后访问这个文件！
        uwsgi_read_timeout 5;
        # First attempt to serve request as file, then
        # as directory, then fall back to displaying a 404.

    }
    location /static {　　　　　　　　　　#指定静态文件的别名，这个和Apache差不多

        expires 30d;
        autoindex on; 
        add_header Cache-Control private;
        alias /app/mysit/static/;

        }
#如果有media，再加一项别名就行

　　　 #　location /media/ {
      #     　　alias  /home/yixiang/Practice/Python/nginx_django/test_project/media/;
      # 　　 }

}
```



### **七、部署完成**

`nginx restart` 重启nginx

访问ip
