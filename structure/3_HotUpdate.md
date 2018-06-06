# Hot Update

* install fswatch
* 编辑fswatch启动脚本
    
    
    cd easyswoole_demo; 
    vim start.sh 
脚本内容：

    #!/bin/bash
    DIR=$1
    
    if [ ! -n "$DIR" ] ;then
        echo "you have not choice Application directory !"
        exit
    fi
    
    php easyswoole stop
    php easyswoole start --d
    
    fswatch $DIR | while read file
    do
       echo "${file} was modify" >> ./Temp/reload.log 2>&1
       php easyswoole reload
    done
* 运行热更新脚本

    
    ./start.sh App/

    