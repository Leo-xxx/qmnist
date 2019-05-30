## MNIST数据集重生！测试图片增加到6万张，LeCun点赞

关注前沿科技 [量子位](javascript:void(0);) *今天*

##### 晓查 发自 凹非寺 量子位 出品 | 公众号 QbitAI

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtAaRgRp2HLm7kBnp1KiazNn7Z5uciaKEC3drvxjuWBwmkUwBbFROX0WDiaN0iakD9myLbA2VUC9t033lw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

MNIST数据集是图像分类领域的基准测试之一，用于0~9手写数字图像分类任务，包含6万张训练图像和1万张测试图像。它已经有20多年的历史了。

但是官方测试集因为测试集样本太少，MNIST通常被认为不能提供有意义的置信区间。

现在，来自纽约大学两位研究人员给MNIST测试集再增加5万张图片，叫做**QMNIST**，获得校友、也是MNIST发起者LeCun转发。

LeCun给予了这个数据集很高的评价，认为它“重生、恢复、扩展”了MNIST。

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtAaRgRp2HLm7kBnp1KiazNn7vRQbF9z58Mm5cepEOjcHUa3j9zROibcIdCw2MTyorbfZHXuz9vCCkibA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

## 数据集内容

QMNIST扩展数据集包含以下一些文件。

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtAaRgRp2HLm7kBnp1KiazNn77sc1I8icnaPIcOGzKEiaF3EBX06DmaiaFay5FlicJJXGaCAUYhlulUy9YQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

其中，前两个gz压缩文件和标准MNIST数据文件格式相同，不同的是QMNIST包含6万个测试样本。

前10000个QMNIST测试样本与MNIST测试集是逐一匹配的，后50000个示例是根据MNIST用算法重建的数据集。

## 使用方法

QMNIST的GitHub页上提供了Pytorch平台的QMNIST数据加载器，需要将数据集下载至与pytorch.py相同的文件夹下将网络下载选项设置为download=’True’。

它与标准的Pytorch MNIST数据加载器兼容。

```
from qmnist import QMNIST

# the qmnist training set, download from the web if not found
qtrain = QMNIST('_qmnist', train=True, download=True)  

# the qmnist testing set, do not download.
qtest = QMNIST('_qmnist', train=False)

# the first 10k of the qmnist testing set with extended labels
# (targets are a torch vector of 8 integers)
qtest10k = QMNIST('_qmnist', what='test10k', compat=False, download='True')

# all the NIST digits with extended labels
qall = QMNIST('_qmnist', what='nist', compat=False)
```

## 传送门

数据集地址：
https://github.com/facebookresearch/qmnist

论文地址：
https://arxiv.org/abs/1905.10498

— **完** —

**小程序|全类别AI学习教程**

[![img](https://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtDpADEKp9rvicB48XgA8ueVdwNbXM1wibYx0ic2pYicwu3UCU5BM6fpDvbH8c4e9JV3uGvYaWAhvGiaTVQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)](https://mp.weixin.qq.com/s?__biz=MzIzNjc1NzUzMw==&mid=2247522055&idx=3&sn=55dfd3d835142cac653f348749c95ac4&chksm=e8d02075dfa7a963eb8e29c416cbdf564f5eadb0b2a26a0f4a6dab4ab6d008699a321d04dcba&mpshare=1&scene=1&srcid=&key=0aa21025b9197e7f3790fb2f651c7ac91a35348ddaf9b9e531ae3144decec3c93b95eeec7271677df57845140edbadaad6c339f091f375a262041d30bfe7765f844895ac6dae2ab322ee32fe9d3f2567&ascene=1&uin=MjMzNDA2ODYyNQ%3D%3D&devicetype=Windows+10&version=62060833&lang=zh_CN&pass_ticket=p2XlI0Ofbuoae95AXUkwd7Vu8WFUZlqdMgTFTVbfWwGuNeaygo98vk8gYURMnTbY)

**AI社群|与优秀的人交流**



![img](https://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtDcZyEBVM81oW4VRoNAibJWw1qt2Fxv2MINM4SsViaaOsD7exDSlDnoBKicLIXhuZlgPEPrne0p3NqNg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)



**量子位** QbitAI · 头条号签约作者





վ'ᴗ' ի 追踪AI技术和产品新动态



喜欢就点「在看」吧 !













微信扫一扫
关注该公众号