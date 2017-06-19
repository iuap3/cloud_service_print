# 对接步骤

1、注册服务，颁发证书

Saas应用需要调用打印服务时，由云打印开发人员为saas服务注册，并为saas应用颁发安全证书（这部分暂时由线下完成，后续会有线上注册功能上线）。

2、在saas应用配置文件中配置云打印变量

saas应用调用云打印时，需要在自己的应用配置文件中配置打印的变量print.client.credential.path和print.server.name，加密算法变量UAP.AUTH.ALG和UAP.KDF.PRF，其中print.server.name是调用打印服务的域名或者测试环境中IP地址和端口，print.client.credential.path为安全认证文件存放在saas应用中的路径。示例如下：

![](/articles/print/4-/images/image3.png)



 
3、开发配置maven依赖

saas应用使用sdk调用云打印服务，需要在saas应用的pom.xml文件中添加云打印sdk依赖。


```
<dependency>
<groupId>com.yonyou.iuap</groupId>
<artifactId>iuap.print.client</artifactId>
<version>1.0.1-RC001</version>
</dependency>
```


没有使用maven开发环境的，也可以在用友maven官网http://maven.yonyou.com/
搜索并下载下图所示的版本的jar包，导入到web工程中。

![](/articles/print/4-/images/image4.png)

 

4、添加云打印代理Servlet

在saas应用的web.xml中添加云打印代理servert，确保打印设计器的请求通过代理能够访问到云打印的服务。配置如下：
	

```
<servlet>
		<display-name>PrintDelegateServlet</display-name>
		<servlet-name>PrintDelegateServlet</servlet-name>
		<servlet-class>com.yonyou.iuap.print.client.servlet.PrintDelegateServlet</servlet-class>
	</servlet>
	<servlet-mapping>
		<servlet-name>PrintDelegateServlet</servlet-name>
		<url-pattern>/XXX/printdelegate</url-pattern>
	</servlet-mapping>
```


XXX为saas应用调用云打印服务请求路径（sass应用的服务路径）例如云打印demo环境：

![](/articles/print/4-/images/image5.png)
 

Saas后台服务接口如下：

![](/articles/print/4-/images/image6.png)

 
至此，云打印所有应用环境配置完毕，可以通过云打印API调用打印的服务。

5、保存业务对象

前面提到过，想要打印先需要设计打印模板，设计打印模板又需要变量的支撑，因此首要任务是调用sdk中把saas应用中的业务对象保存到云打印中来。其实总结起来就是一句话，保存业务对象的目的是为了保证新增打印模板时，左侧数据源区域有变量供设计模板时使用。保存好的业务对象在模板设计器中展现如下图所示：

![](/articles/print/4-/images/image7.png)

 
具体的保存业务对象是调用sdk中PrintServer的execPost（）方法，具体API如下：

<table> 
 <tbody> 
  <tr> 
   <td> <p> <span>接口类型</span> </p> </td>
   <td colspan="3"> <p> <span>POST</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>接口名称</span> </p> </td>
   <td colspan="3"> <p> <span>保存业务对象bo</span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span>url</span> </p> </td>
   <td colspan="3"> <p> <span>bomanage/saveBo</span> </p> </td> 
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
   <td> <p> <span>业务对象json串（见sfexpressBO.js）</span> </p> </td> 
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

[sfexpressBO.js](#/cloud_service_print/articles/print/4-/images/sfexpressbo.html)


6、创建模板

保存完业务对象之后，就可以创建打印模板了，创建模板之前，需要saas应用调用sdk以非跨域的方式打开模板设计器界面。以demo工程为例

1）选择业务对象并输入新模板名称

![](/articles/print/4-/images/image9.png)
 
2）点击设计器中新建按钮，打开一个空的html，调用saas后端服务请求云打印的html内容填充到打开的html中去，此时浏览器地址栏中的地址为saas应用的地址，但是打开的却是云打印的设计器，以这样的方式实现非跨域打开云打印设计器（安全问题），demo工程前端示例代码如下:

![](/articles/print/4-/images/image10.png)
 
**注意**：其中tenantId为租户Id，如果为空，说明模板为系统模板，租户不为空，为自定义模板，templateType，按照上面所写即可。同时url中的参数必须包含bocode、type、reportName和tenantId,设计器界面需要这些参数。租户Id为空时，可以传null。

demo工程应用后端示例代码如下：

![](/articles/print/4-/images/image11.png)
 
通过上述代码，打开打印设计器，设计器界面如下：

![](/articles/print/4-/images/image12.png)


 
3）设计打印模板，拖动左侧数据源区域的变量放置在右侧画布上，同时选择控件区各种控件，进行模板数据和样式的设计，具体参照云打印操作手册进行模板设计。网址为
http://www.yyuap.com/page/service/book/iuap_paas_print/index.html#/iuap_paas_print/articles/print/1-/gai_shu.html

4）设计完模板以后，点击保存按钮，把设计好的模板保存到数据库中。示例如下：

![](/articles/print/4-/images/image13.png)

 
7、数据预览打印

保存完打印模板之后，可以使用该模板调用云打印的服务，实现打印功能。云打印使用的回调方式获取打印数据。还是以demo工程为例说明 saas应用调用云打印数据预览打印服务的过程。

1）选择一个设计好的模板，点击预览按钮，如下图所示：

![](/articles/print/4-/images/image14.png)

 
2）通过点击按钮，打开打印预览界面，并把saas数据接口作为参数发送给云打印前端，同样也是以非跨域的方式实现。和新增模板一样，url中拼接的参数是有意义的，必须有tenantId、printcode、serverUrl、params和sendType=2这几个参数（其中printcode是模板code，serverUrl是saas取打印数据接口url，params是saas取数接口参数（sass自己定义），sendType=2表示以第二种取数方式取数）。demo工程前端代码如下所示：

![](/articles/print/4-/images/image15.png)


 
3）后端服务调用sdk打开数据预览界面，在数据预览界面加载过程中会通过saas数据接口参数调用saas取数接口，把打印数据加载到模板中，从而形成的打印数据预览界面。demo工程后端示例代码如下：

![](/articles/print/4-/images/image16.png)


 
saas取数接口数据格式如下所示：



```
{
    "SFExpress":[
        {
            "fromComp":"用友网络科技股份有限公司",
            "fromUser":"马帅",
            "fromAddr":"北京市海淀区北清路68号",
            "fromTelphone":"15965234165",
            "arriveComp":"百度网讯科技有限公司",
            "recipient":"葛宁宁",
            "recipientAttr":"北京市海淀区上地大厦1011",
            "recipientTelphone":"13966587231",
            "detailCare":"",
            "receiver":"996459",
            "sender":"",
            "fromAttrCode":"5",
            "destinationCode":"wegweg",
            "charge":"",
            "count":"1",
            "realWeight":"",
            "freight":"1",
            "payment":"22"
        }
    ]
}
```




 
打开后的打印预览界面如下所示：

![](/articles/print/4-/images/image18.png)

 
点击打印按钮，即可完成打印功能。
