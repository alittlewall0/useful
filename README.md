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



https://mirrors.aliyun.com/pypi/packages/80/2a/58f8078744e0408619c63148f7a2e8e48cf007e4146b74d4bb67c56d161b/torch-1.7.0-cp36-cp36m-manylinux1_x86_64.whl 

http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/linux-64/pytorch-1.3.1-cuda100py36h53c1284_0.conda

https://shapenet.cs.stanford.edu/media/indoor3d_sem_seg_hdf5_data.zip

https://shapenet.cs.stanford.edu/media/modelnet40_normal_resampled.zip

https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.2.39/10.2_20200724/cudnn-10.2-linux-x64-v8.0.2.39.tgz


deep learning for image and point cloud  in autonomous
https://software-download.microsoft.com/sg/Win8.1_Chinese(Simplified)_x64.iso?t=c1a76927-9873-476b-96fd-1a754d0eae49&e=1608887209&h=d5acaa32e3e4edfb00238b56f10e1c94

https://www.ptc.com/cn/products/creo/trial/free-trial-sign-up?email=shiqiang%40zhejianglab.edu.cn


https://docs.nvidia.com/jetson/l4t-multimedia/mmapi_build.html


https://blog.csdn.net/heyijia0327/article/details/82855443#t19

https://www.corvin.cn/651.html

https://docs.nvidia.com/jetson/l4t-multimedia/l4t_mm_v4l2_cam_cuda_group.html


https://blog.csdn.net/qq_39201531/article/details/108362042


https://yongqi.blog.csdn.net/article/details/108898577


https://drive.google.com/u/0/uc?export=download&confirm=2-bt&id=1lcUUxF8mJgZ_e-tZhP1XNQtTBuC-R0zr


https://zhuanlan.zhihu.com/p/124958578


--2021-03-01 16:47:50--  http://carla-assets.s3.amazonaws.com/20201222_232b876.tar.gz
http://pubs.doc.ic.ac.uk/survey-mcts-methods/survey-mcts-methods.pdf



'''
#include <arpa/inet.h>
#include <netinet/in.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <sys/socket.h>
#include <unistd.h>

#define BUFF_LEN 10240
#define DEBUG 0
int main(int argc, char** argv) {
  if (argc != 4) {
    printf("Usage:%s [ip] [port] [path eg:raw.txt]\n", argv[0]);
    return -1;
  }
  char* ip = argv[1];
  int port = atoi(argv[2]);
  printf("Listening... ...\n");
  // 输出txt
  FILE* stream;
  stream = fopen(argv[3], "a");

  //创建套接字
  int serv_sock = socket(AF_INET, SOCK_STREAM, IPPROTO_TCP);

  //将套接字和IP、端口绑定
  struct sockaddr_in serv_addr;
  memset(&serv_addr, 0, sizeof(serv_addr));   //每个字节都用0填充
  serv_addr.sin_family = AF_INET;             //使用IPv4地址
  serv_addr.sin_addr.s_addr = inet_addr(ip);  //具体的IP地址
  serv_addr.sin_port = htons(port);           //端口
  bind(serv_sock, (struct sockaddr*)&serv_addr, sizeof(serv_addr));
#if DEBUG
  unsigned long ip = inet_addr("127.0.0.1");
  printf("%ld\n", ip);
#endif
  
  //进入监听状态，等待用户发起请求
  listen(serv_sock, 20);
  
  char buf[10240];

  //接收客户端请求
  struct sockaddr_in clnt_addr;
  socklen_t clnt_addr_size = sizeof(clnt_addr);
  while (1) {
    int clnt_sock =
        accept(serv_sock, (struct sockaddr*)&clnt_addr, &clnt_addr_size);
    

    //接受数据
    int count = read(clnt_sock, buf, sizeof(buf) - 1);
    if (count == -1) {
      printf("recieve data fail!\n");
      continue;
    }

    printf("recv num : %d\n", count);
    for (int i = 0; i < count; i++) {
      fprintf(stream, "%x", buf[i]);
    }
    close(clnt_sock);
    fprintf(stream, "\n");
  }

  //关闭套接字
  close(serv_sock);

  // 关闭输出文件
  fprintf(stream, "\n\n\n");
  fclose(stream);
  return 0;
}
'''


01 "lng":121.0366557,"lat":30.5821057
02 "lng":121.0374223,"lat":30.5809405
03 "lng":121.0384973,"lat":30.5791863
04 "lng":121.0397703,"lat":30.5770236


https://blog.csdn.net/xuan196/article/details/117230922
