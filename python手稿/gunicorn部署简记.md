gunicorn部署简记

1、安装

`pip3 install gunicorn`

2、在项目文件夹下创建gunicorn_conf.py文件

`import multiprocessing`

`bind = '0.0.0.0:8080'`

`workers = multiprocessing.cpu_count()*2+1`

`daemon = true` #设置守护进程

`timeout = 60` #超时设置，默认30s

`#访问日志和错误日志设置`

`accesslog = './logs/acess.log'`

`errorlog = './logs/error.log'`

3、运行gunicorn

	test3.wsgi -c gunicorn_conf.py
	
4、在setting.py文件下添加
	
	STATIC_ROOT = os.path.join(BASE_DIR,'static_root')
	
5、在项目目录下新建文件夹static_root

6、在命令行运行：
	
	python3 manage.py collectstatic
	
7、在项目urls.py中修改：

`url(r’^static/(?P<path>.*)$’, serve, {‘document_root’: os.path.join(BASE_DIR, ‘’)}),`
	
改为：
	 
`url(r’^static/(?P<path>.*)$’, serve, {‘document_root’: STATIC_ROOT}),`  