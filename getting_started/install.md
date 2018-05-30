# 快速入门
* install pecl_swoole
* install easyswoole framework

install pecl_swoole
----
1. 源码编译前置条件: 
* php version>=7.1, pecl_swoole version >=1.9.23 or >= 2.1.0
* install pecl_pcntl
* 编译步骤
2. 编译
* git clone https://github.com/swoole/swoole-src/releases
* phpize
* ./configure
* make && make install
3. 修改php.ini
4. 验证
php --ri=swoole


install easyswoole framework
----
* composer create-project easyswoole/app easyswoole_demo
* cd easyswoole_demo
* php easyswoole start
* 验证：ps -ef |grep easyswoole






