# 使用教程

*说明：本脚本只支持h2.cloud网站，即国内的一加云服务，对于国际版暂不支持。*

程序运行逻辑为使用者使用Chrome或者Firefox登陆网页，进入相册界面后，Python脚本获得该网页的Cookie，代替用户进行照片下载，下载过程共分两步：

1. 获取所有照片的名称和ID
2. 根据ID获取下载链接并保存至本地

## 步骤：

1. 安装Python，并安装下列依赖库
   - aiohttp
   - aiofiles
   - browser_cookie3
   - requests
   - tqdm
2. 使用Chrome或者Firefox打开 [官网](https://cloud.h2os.com/) 登陆账号，进入相册
3. 在程序中修改**browser**变量为相应浏览器（chrome 或 firefox）和**save_dir**变量为相应的值
4. 运行程序即可



## Bug说明

程序运行过程中，偶尔会bug掉，这时候需要重新运行程序，bug的原因大部分是因为Cookie过期，这时候刷新浏览器界面重新登陆即可。如果是其他原因的话，可能是某一个请求失败了，目前程序未实现失败续传功能，所以需要重新运行程序，

但正如第一部分所说，下载总共两个阶段，第一阶段运行结束后，结果会进行持久化保存，所以可以将第一部分的代码注释，直接加载后继续运行第二阶段即可。

![image](https://user-images.githubusercontent.com/58325947/136684172-d1fd2031-c60a-47c7-af13-befbb68426bf.png)
