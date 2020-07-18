# SpringCore-JDBC
-------------------------config.xml--------------



<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns:context="http://www.springframework.org/schema/context"
	xmlns:p="http://www.springframework.org/schema/p"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans.xsd
    http://www.springframework.org/schema/context
    http://www.springframework.org/schema/context/spring-context.xsd">

	<bean
		class="org.springframework.jdbc.datasource.DriverManagerDataSource"
		name="dataSource" p:driverClassName="com.mysql.jdbc.Driver"
		p:url="jdbc:mysql://localhost/world" p:username="root"
		p:password="password-1">
	</bean>

	<bean class="org.springframework.jdbc.core.JdbcTemplate"
		name="jdbcTemplate" p:dataSource-ref="dataSource" />

	<bean
		class="com.sai.spring.springjdbc.employee.dao.impl.EmployeeDaoImpl"
		name="employeedao">
		<property name="jdbcTemplate">
			<ref bean="jdbcTemplate" />
		</property>
	</bean>
</beans>
