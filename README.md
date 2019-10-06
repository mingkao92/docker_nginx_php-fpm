# docker_nginx_php-fpm


nginx_php-fpm docker镜像，基于dockerhub官方镜像组合，并作部分修改


#### 基础镜像和软件：
* [nginx:1.16-alpine](https://github.com/nginxinc/docker-nginx/blob/0ad6faa0790f423fb239f2b8800dc339d763869a/stable/alpine/Dockerfile)
* [php:7.2-fpm-alpine](https://github.com/docker-library/php/blob/3a546766fdeb873090c7e87c4ec3491841bafb1c/7.2/alpine3.10/fpm/Dockerfile)
* [s6-overlay-v1.22.1.0](https://github.com/just-containers/s6-overlay/releases)


#### 改动：
##### nginx
1. 安装及修改配置后增加冒烟测试
2. 增加fastcgi代理到php-fpm配置
3. 增加vhost示例

##### php-fpm
1. 安装完成及修改配置后增加冒烟测试
2. 对部分指令进行合并/调整顺序处理
3. 开启gd、pdo_mysql、opcache扩展
4. 安装并开启redis、apcu扩展
5. 对部分配置进行修改

##### 其他
1. 换用阿里云软件仓库
2. 设置时区
3. 使用s6-overlay进行进程管理
