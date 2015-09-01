这个JAVA的框架主要用于动态的调用WebService.
通常情况下得WS调用都是使用wsdl4j等生成静态的stub存根类,然后再调用webservice.但是这样的局限性很大,比如在流程引擎中,调用的WS可能都是在界面上配置的.这就要求需要我们动态的调用WS,只需要传入一个WSDL地址.然后框架可以自动的分析WSDL,然后动态的生成SOAPMessage,直接发送SOAPConnection调用WS.这样就可以不生成静态的stub存根了.

目前CXF是有类似的实现的.但是我们的项目里面没有使用CXF.因此,为了使用WS的动态调用引入CXF的一大堆东西是划不来的.因此有了这个框架的实现.

目前能支持SOAP1.1和SOAP1.2 主要支持Document/Literal(wrapped).基本上支持80%以上的WebService调用,还有一些因为WSDL不标准等原因,不能自动的解析,需要调用LowLevelInstance来直接拼装SoapElement.

这个框架于2011年开始创建并维护在私有的SVN上,因为现在的项目转向了RestFul的调用,不再使用WebService,以后会停止维护.因此开源出来.仅供有兴趣的人参考.

关于SOAP的标准与解析,可以参考本人的一篇博客: [http://sunxiang0918.cn/2012/09/18/SOAP中Binding的四种样式/](http://sunxiang0918.cn/2012/09/18/SOAP中Binding的四种样式/)