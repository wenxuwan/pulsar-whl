# pulsar-whl

下载pulsar源代码：

https://github.com/wenxuwan/pulsar

这是包含了tuya内部实现的仓库。修复了源代码的几个问题。下面的这个issue是源代码也有的问题。

https://github.com/apache/pulsar/issues/6724

本地编译docker image：

    1.cd pulsar/pulsar-client-cpp/docker
    //第二步编译images的时候有两个参数可以制定python版本支持下面这几个版本cp27-cp27m/  cp27-cp27mu/ cp35-cp35m/  cp36-cp36m/  cp37-cp37m/  cp38-cp38/
    2.docker build --build-arg PYTHON_VERSION=3.7 --build-arg PYTHON_SPEC=cp37-cp37m . 
    
编译代码：
    1.启动container， 然后进入container环境，执行build-wheel-file-within-docker.sh，最后会在/pulsar/pulsar-client-cpp/python/wheelhouse/目录下生成最终的文件。
    
安装whl包：
    在自己的linux环境里面用对应的pip版本安装生成的whl文件即可。
    e.g:
        pip3.7 install pulsar_client-2.6.0-cp37-cp37m-manylinux1_x86_64.whl
