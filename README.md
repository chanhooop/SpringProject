## Spring Project

### π« Context

    1. μμ μμ
    2. μ¬μ© ν΄
    3. μμ , λ³΄μ μ¬ν­
    4. ν₯ν λ°μ  κ³ν

#### 1. μμ μμ

<br/>
<br/>

[JSP PROJECT](https://github.com/jasper-oh/JSP_WebProject) λ₯Ό μ§ννλ©΄μ Maintanece μ Performance λ₯Ό ν₯μ μν¬ νμμ±μ λκ»΄ κ°μΈ μ μΌλ‘ νλ‘μ νΈλ₯Ό μ§ν

<br/>
<br/>

#### 2. μ¬μ© ν΄

<br/>
<br/>

[![Java Badge](https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=java&logoColor=black)](http://java.com/)
[![Eclipse Badge](https://img.shields.io/badge/Eclipse-2C2255?style=for-the-badge&logo=eclipse&logoColor=white)](http://eclipse.org/)
[![Spring Badge](https://img.shields.io/badge/Spring_MyBatis-04ff00?style=for-the-badge&logo=spring&logoColor=white)](http://spring.io/)
[![Tomcat Badge](https://img.shields.io/badge/Apache_Tomcat-CB9F18?style=for-the-badge&logo=Apache&logoColor=white)](http://spring.io/)

<br/>
<br/>

#### 3. μμ , λ³΄μ μ¬ν­

<br/>
<br/>

π κΈ°μ‘΄μ MVC model μ μ΄μ©νμ¬

    Model -> Dao

    View -> JSP

    Controller -> Controller

μ¬μ©νμ¬ μμμ νμμ΅λλ€. νμ§λ§ μμμ μλ£νκ³ , νμλ€κ³Ό λ¦¬λ·°λ₯Ό ν κ²°κ³Ό μ¬λ¬ μλ¬μ¬ν­μ΄ λ°κ²¬λμμ΅λλ€. κ·Έμ€μ λͺκ°μ§λ₯Ό μ΄κ±°νμλ©΄,

1οΈβ£ κ²°μ  λ°©μμ μμ΄μ get λ°©μμ μ¬μ©ν΄μ Modeling μ΄ μ§νλμ΄ λ³΄μμμ μ¬λ¬ λ¬Έμ κ° λ°κ²¬λμμ΅λλ€.<br/>
2οΈβ£ μ½λλμ΄ λ§κ³ , db μ μ°κ²°λλ λΆλΆμμ λ§μ λ°μ΄ν°λ₯Ό κ΄λ¦¬ ν  κ²½μ°μ νΌν¬λ¨Όμ€κ° λλ¦¬κ² λ°νλλ νμμ λ°κ²¬νμμ΅λλ€.

μμ μ¬ν­μ ν΄κ²°ν  λ°©λ²μ μ°Ύκ³  μΆμ΄ μ¬λ¬ λ¦¬μμΉλ₯Ό ν΅ν΄ Spring MVC μ MyBatis λ₯Ό μ¬μ©νκ² λλ€λ©΄ νΌν¬λ¨Όμ€ ν₯μ λ° μ μ§λ³΄μμλ μ©μ΄ ν κ² κ°μ κ°μΈμ μΌλ‘ μμμ μ§ν νκ² λμμ΅λλ€.

λ³΄νΈμ μΌλ‘ DAO λΆλΆκ³Ό Controller λΆλΆμ μμ ν΄ λκ° κ²μ΄λ©°, μ΄ λΆλΆμ μμ ν΄ λκ°κ³Ό λμμ λ³΄μμ μΈ μΈ‘λ©΄μμλ ν₯μ μμΌ λκ° μμ μλλ€.

#### 4. ν₯ν λ°μ  κ³ν

μ€μ λ‘ μλΉμ€λ₯Ό λ°°ν¬ν¨μ λ°λΌ νΈλμ­μ κ΄λ¦¬λ₯Ό μ§νν  μμ μλλ€.

κΈ°μ‘΄μ μμ λ°©μκ³Όλ λ€λ₯΄κ² Spring MVC λ‘ κ°μ νμ¬ μ μ§λ³΄μλ₯Ό μννκ² μμν  μ μλλ‘ λ§λ€ μμ μ΄κΈ° λλ¬Έμ μ΄μ λ°μμ λΉ λ₯΄κ² λ°μνμ¬ κ°μ λ μΉμ λ§λ€ μ μμκ±°λΌ μμλ©λλ€.

#### 5. κΈ°μ΄ Setting μ¬ν­

<br/>
<br/>

```XML
    <!-- Pom.xml -->
    <!-- JDBC -->
    <dependency>
    	<groupId>org.springframework<groupId>
    	<artifactId>spring-jdbc</artifactId>
    	<version>4.1.4.RELEASE</version>
    </dependency>

	<!-- myBatis -->
	<dependency>
		<groupId>org.mybatis</groupId>
		<artifactId>mybatis</artifactId>
		<version>3.2.8</version>
	</dependency>
	<dependency>
	    <groupId>org.mybatis</groupId>
	    <artifactId>mybatis-spring</artifactId>
	    <version>1.2.2</version>
	</dependency>

    <!-- servlet-context.xml -->
    <beans:bean name="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
		<beans:property name="driverClassName" value="com.mysql.cj.jdbc.Driver"/>
		<beans:property name="url" value="jdbc:mysql://localhost:3306/*Personal Schema Name*?serverTimezone=Asia/Seoul&amp;characterEncoding=utf8&amp;useSSL=false"/>
		<beans:property name="username" value="*ID*"/>
		<beans:property name="password" value="*PW*"/>
	</beans:bean>
	<beans:bean name="sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">
		<beans:property name="dataSource" ref="dataSource"/>
		<beans:property name="mapperLocations" value="classpath:com/*Personal Root*/*.xml" />
	</beans:bean>
	<beans:bean name="sqlSession" class="org.mybatis.spring.SqlSessionTemplate">
		<beans:constructor-arg index="0" ref="sqlSessionFactory" />
	</beans:bean>



```
