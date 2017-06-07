# 云打印数据接口API

## 一、业务对象接口

1、保存业务对象

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

2、更新业务对象

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

3、删除业务对象

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

4、复制模板

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

5、批量定制模板

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

6、删除模板

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

7、查询租户下所有的模板

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

