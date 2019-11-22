
##### 1.修改httpd.conf配置文件。修改端口号


```
Listen 80
可修改为其他不占用的端口号
```
###### 2.修改项目路径。首先在`<IfModule alias_module>`标签下增加
```
 Alias /davidWeb/ "C:/david/davidwebs/" 
```
###### 3.然后在`<IfModule alias_module>`同级目录下增加目录
```
<Directory "C:/david/davidwebs">  
    AllowOverride All  
    Options Indexes FollowSymLinks Includes ExecCGI  
    Require all granted  
</Directory>  
```
###### 4.重新启动`http://ip:端口号/davidWeb`即可看到自己的项目文件。