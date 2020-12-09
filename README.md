# useful
https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/linux-64/mkl-2020.2-256.conda
https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/linux-64/bottleneck-1.3.2-py37heb32a55_1.conda

channels:
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
  - defaults
show_channel_urls: true

CUDA
https://www.nvidia.com/en-us/geforce/drivers/
https://developer.download.nvidia.com/compute/cuda/10.2/Prod/local_installers/cuda_10.2.89_440.33.01_linux.run

3. 通过互联网总结学习线性方程组 Ax=b 的求解方法,回答以下问题:(2 分)
(1)对于该类问题,你都知道哪几种求解方法?
(2)各方法的优缺点有哪些?分别在什么条件下较常被使用?
4. 简答题,开放性答案:设计里程计与激光雷达外参标定方法。(2 分)
我们一般把传感器内自身要调节的参数称为内参,比如前面作业中里程计模型的两轮间距与两个轮子的半
径。把传感器之间的信息称为外参,比如里程计与激光雷达之间的时间延迟,位姿变换等。请你选用直接
线性方法或基于模型的方法,设计一套激光雷达与里程计外参的标定方法,并回答以下问题:
(1)你设计的方法是否存在某些假设?基于这些假设下的标定观测值和预测值分别是什么?
(2)如何构建你的最小二乘方程组求解该外参?
