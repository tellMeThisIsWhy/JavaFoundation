### SpringMVC搭环境
___
#### 一、WEB.xml文件的配置
1. **设置<servlet>标签**
设置<servlet-name>、<servlet-class>、<init-param>、<load-on-startup>
>     <servlet> 
>         <servlet-name>SpringMVCDispatcherServlet</servlet-name> 
>         <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class> 
>         *<!-- 配置初始化参数，用于读取 SpringMVC 的配置文件 -->* 
>         <init-param> 
>             <param-name>contextConfigLocation</param-name> 
>             <param-value>classpath:SpringMVC.xml</param-value>
>         </init-param> 
>         *<!-- 配置 servlet 的对象的创建时间点：应用加载时创建。 取值只能是非 0 正整数，表示启动顺序 --> *
>         <load-on-startup>1</load-on-startup>
>     </servlet> 
2. __设置<servlet-mapping>标签__
设置<servlet-name><url-pattern>标签
>     <servlet-mapping> 
>         <servlet-name>SpringMVCDispatcherServlet</servlet-name> 
>         <url-pattern>/</url-pattern>
>     </servlet-mapping>
3. **设置<filter>、<filter-mapping>解决中文乱码**
设置<filter-name>、<filter-class>、<init-param>
>	<filter>
>		<filter-name>characterEncodingFilter</filter-name>
>		<filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
>		<init-param>
>			<param-name>encoding</param-name>
>			<param-value>UTF-8</param-value>
>		</init-param>
>	</filter>

设置<filter-name>、<url-pattern>
>	<filter-mapping>
>		<filter-name>characterEncodingFilter</filter-name>
>		<url-pattern>/*</url-pattern>
>	</filter-mapping>

#### 二、springMVC.xml文件的配置
1. 设置扫描controller注解
>	<context:component-scan base-package="cn.itcast">
>		<context:include-filter type="annotation"
>		expression="org.springframework.stereotype.Controller"/>
>	</context:component-scan>
2. 配置视图解析器（）
to be continue!
