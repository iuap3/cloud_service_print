# 系统架构

云打印是pass平台，各个系统如云审批，建筑，友人才等sass应用调用云打印服务时，云打印为各个sass应用创建单独的数据库，存储各个sass应用的数据。同时，sass应用注册时，云打印会为每一个sass应用颁发一个证书，saas应用通过调用sdk访问云打印的服务。

 
![](/articles/print/4-/images/image19.png)