# 云打印数据接口API

## 一、业务对象接口
### 非云打印模板的磨盒打印

```
设置打印参数服务
```

## 接口说明

```
设置打印参数服务
```

```
通过设计打印参数服务，用户可以设置打印机，设置打印参数等。
```

## 接口URI

接口访问的URI

```
生产环境:
https://print.yonyoucloud.com
测试环境：
http://172.20.8.30:8891
URI地址：
/printbox/mobile/html/printSettings.html 
```

## 请求方式

```
GET（SELECT）：打开打印设置页。
```

## 请求参数

需要管理员进行租户与盒子的序列号绑定才能正常使用。

| 参数 | 参数类型 |是否必须| 说明 |
| --- | --- | :--- | :--- |
| tenantId | String | Y | 租户信息,登录的企业租户 |
| userid | String | Y | 用户唯一值，设置默认时用 |
| fileURL | String | Y | 打印的文件URL |
| printer | String | N | 扫码打印时才需要把扫码值填入 |

## 返回参数

```
返回一个设置页面的HTML
```
### 云打印模板的磨盒打印

```
设置打印参数服务
```

## 接口说明

```
设置打印参数服务
```

```
通过设计打印参数服务，用户可以设置打印机，设置打印参数等。
```

## 接口URI

接口访问的URI

```
生产环境:
https://print.yonyoucloud.com
测试环境：
http://172.20.8.30:8891
URI地址：
/ sdk的虚拟目录/print /preview.html 
```

## 请求方式

```
GET（SELECT）：打开打印预览页。
```

## 请求参数

需要管理员进行租户与盒子的序列号绑定才能正常使用。

| 参数 | 参数类型 |是否必须| 说明 |
| --- | --- | :--- | :--- |
| tenantId | String | Y | 租户信息,登录的企业租户 |
| printcode | String | Y | 打印的模板编码 |
| serverUrl | String | Y | 业务系统取数的URL |
| params | String | Y | 业务系统取数URL的参数，是个JSON对象 |
| sendType | String | Y | 默认为2 |
| print_token | String | Y | 默认为Y0hKcGJuUmZkRzlyWlc0PQ== |

## 返回参数

```
返回一个设置页面的HTML
```

### 保存业务对象

<table> 
 <tbody> 
  <tr> 
   <td> <p> <a><span>接口类型</span></a> </p> </td>
   <td colspan="3"> <p> <span>POST</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口名称</span> </p> </td>
   <td colspan="3"> <p> <span>保存业务对象bo</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>url</span> </p> </td>
   <td colspan="3"> <p> <span>/rest/bomanage/saveBo</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口说明</span> </p> </td>
   <td colspan="3"> <p> <span>保存业务对象</span> </p> </td> 
  </tr> 
  <tr> 
   <td rowspan="2"> <p> <span>输入值类型</span> </p> </td>
   <td> <p> <span>参数名称</span> </p> </td>
   <td> <p> <span>参数类型</span> </p> </td>
   <td> <p> <span>参数说明</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>boStr</span> </p> </td>
   <td> <p> <span> String</span> </p> </td>
   <td> <p> <span>业务对象json串（见附件sfexpressBO.js）</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值类型</span> </p> </td>
   <td colspan="3"> <p> <span>Json串</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值范例</span> </p> </td>
   <td colspan="3"> <p> <span>{"saveResult", saveResult}</span> </p> </td> 
  </tr> 
 </tbody> 
</table> 
### 更新业务对象

<table> 
 <tbody> 
  <tr> 
   <td> <p> <span>接口类型</span> </p> </td>
   <td colspan="3"> <p> <span>POST</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口名称</span> </p> </td>
   <td colspan="3"> <p> <a><span>更新业务对象bo</span></a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>url</span> </p> </td>
   <td colspan="3"> <p> <span>/rest/bomanage/updatebo</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口说明</span> </p> </td>
   <td colspan="3"> <p> <span>更新业务对象</span> </p> </td> 
  </tr> 
  <tr> 
   <td rowspan="3"> <p> <span>输入值类型</span> </p> </td>
   <td> <p> <span>参数名称</span> </p> </td>
   <td> <p> <span>参数类型</span> </p> </td>
   <td> <p> <span>参数说明</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>boStr</span> </p> </td>
   <td> <p> <span> String</span> </p> </td>
   <td> <p> <span>业务对象json串</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>pk_bo</span> </p> </td>
   <td> <p> <span>String</span> </p> </td>
   <td> <p> <span>业务对象PK</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值类型</span> </p> </td>
   <td colspan="3"> <p> <span>Json串</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值范例</span> </p> </td>
   <td colspan="3"> <p> <span>{"updateResult", true}</span> </p> </td> 
  </tr> 
 </tbody> 
</table> 

### 删除业务对象

<table> 
 <tbody> 
  <tr> 
   <td> <p> <span>接口类型</span> </p> </td>
   <td colspan="3"> <p> <span>POST</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口名称</span> </p> </td>
   <td colspan="3"> <p> <span>删除业务对象bo</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>url</span> </p> </td>
   <td colspan="3"> <p> <span>/rest/bomanage/deleteBo</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口说明</span> </p> </td>
   <td colspan="3"> <p> <span>删除业务对象</span> </p> </td> 
  </tr> 
  <tr> 
   <td rowspan="2"> <p> <span>输入值类型</span> </p> </td>
   <td> <p> <span>参数名称</span> </p> </td>
   <td> <p> <span>参数类型</span> </p> </td>
   <td> <p> <span>参数说明</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>pk_bo</span> </p> </td>
   <td> <p> <span> String</span> </p> </td>
   <td> <p> <span>业务对象PK</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值类型</span> </p> </td>
   <td colspan="3"> <p> <span>Json串</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值范例</span> </p> </td>
   <td colspan="3"> <p> <span>{"deleteResult", deleteResult}</span> </p> </td> 
  </tr> 
 </tbody> 
</table> 

## 二、模板接口

### 复制模板

<table> 
 <tbody> 
  <tr> 
   <td> <p> <span>接口类型</span> </p> </td>
   <td colspan="3"> <p> <span>POST</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口名称</span> </p> </td>
   <td colspan="3"> <p> <span>复制模板</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>url</span> </p> </td>
   <td colspan="3"> <p> <span>/rest/printTemplate/copytemByPk</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口说明</span> </p> </td>
   <td colspan="3"> <p> <span>复制模板</span> </p> </td> 
  </tr> 
  <tr> 
   <td rowspan="4"> <p> <span>输入值类型</span> </p> </td>
   <td> <p> <span>参数名称</span> </p> </td>
   <td> <p> <span>参数类型</span> </p> </td>
   <td> <p> <span>参数说明</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>pk_template</span> </p> </td>
   <td> <p> <span>String</span> </p> </td>
   <td> <p> <span>模板pk</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>templatecode</span> </p> </td>
   <td> <p> <span>String</span> </p> </td>
   <td> <p> <span>模板code</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>templatename</span> </p> </td>
   <td> <p> <span>String</span> </p> </td>
   <td> <p> <span>模板名称</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值类型</span> </p> </td>
   <td colspan="3"> <p> <span>Json串</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值范例</span> </p> </td>
   <td colspan="3"> <p> <span>{"copyMsg": true}</span> </p> </td> 
  </tr> 
 </tbody> 
</table> 

### 批量定制模板

<table> 
 <tbody> 
  <tr> 
   <td> <p> <span>接口类型</span> </p> </td>
   <td colspan="3"> <p> <span>POST</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口名称</span> </p> </td>
   <td colspan="3"> <p> <a><span>批量定制模板</span></a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>url</span> </p> </td>
   <td colspan="3"> <p> <span>/rest/printTemplate/copymultiprint</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口说明</span> </p> </td>
   <td colspan="3"> <p> <span>批量定制模板</span> </p> </td> 
  </tr> 
  <tr> 
   <td rowspan="2"> <p> <span>输入值类型</span> </p> </td>
   <td> <p> <span>参数名称</span> </p> </td>
   <td> <p> <span>参数类型</span> </p> </td>
   <td> <p> <span>参数说明</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p></p> </td>
   <td> <p></p> </td>
   <td> <p></p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值类型</span> </p> </td>
   <td colspan="3"> <p> <span>Json串</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值范例</span> </p> </td>
   <td colspan="3"> <p> <span>{"copyMsg":“定制成功”,”copyResult”:true}</span> </p> </td> 
  </tr> 
 </tbody> 
</table> 

### 删除模板

<table> 
 <tbody> 
  <tr> 
   <td> <p> <a><span>接口类型</span></a> </p> </td>
   <td colspan="3"> <p> <span>POST</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口名称</span> </p> </td>
   <td colspan="3"> <p> <span>删除模板</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>url</span> </p> </td>
   <td colspan="3"> <p> <span>/rest/printTemplate/deleteprint</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口说明</span> </p> </td>
   <td colspan="3"> <p> <span>删除模板</span> </p> </td> 
  </tr> 
  <tr> 
   <td rowspan="2"> <p> <span>输入值类型</span> </p> </td>
   <td> <p> <span>参数名称</span> </p> </td>
   <td> <p> <span>参数类型</span> </p> </td>
   <td> <p> <span>参数说明</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>pk_template</span> </p> </td>
   <td> <p> <span> String</span> </p> </td>
   <td> <p> <span>模板pk</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值类型</span> </p> </td>
   <td colspan="3"> <p> <span>Json串</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值范例</span> </p> </td>
   <td colspan="3"> <p> <span>{"delresult":true}</span> </p> </td> 
  </tr> 
 </tbody> 
</table> 

### 查询租户下所有的模板

<table> 
 <tbody> 
  <tr> 
   <td> <p> <span>接口类型</span> </p> </td>
   <td colspan="3"> <p> <span>POST</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口名称</span> </p> </td>
   <td colspan="3"> <p> <span>查询租户下所有模板</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>url</span> </p> </td>
   <td colspan="3"> <p> <span>/rest/printTemplate/queryBytatent</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口说明</span> </p> </td>
   <td colspan="3"> <p> <span>查询租户下所有模板</span> </p> </td> 
  </tr> 
  <tr> 
   <td rowspan="2"> <p> <span>输入值类型</span> </p> </td>
   <td> <p> <span>参数名称</span> </p> </td>
   <td> <p> <span>参数类型</span> </p> </td>
   <td> <p> <span>参数说明</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>tetantId</span> </p> </td>
   <td> <p> <span> String</span> </p> </td>
   <td> <p> <span>租户id</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>返回值类型</span> </p> </td>
   <td colspan="3"> <p> <span>JsonArray</span> </p> </td> 
  </tr> 
 </tbody> 
</table> 

