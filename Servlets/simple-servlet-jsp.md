## Simple Servlet

####Task:
Write a simple Java servlet that prints "Hello, World!" from a separate JSP file.

####Given code:
```java
package com.sample;
import java.io.IOException;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
```
```html
<%@ page language="java" contentType="text/html; charset=ISO-8859-1" pageEncoding="ISO-8859-1"%>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="ISO-8859-1">
<title>Hello</title>
</head>
<body>

</body>
</html>
```
####Possible Solution:
```java
package com.sample;
import java.io.IOException;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet(urlPatterns = "/hello.do")
public class loginServlet extends HttpServlet {

	  protected void doGet(HttpServletRequest request, HttpServletResponse response)
			      throws ServletException, IOException {
		    request.getRequestDispatcher("/hello.jsp").forward(request, response);
	  }

}
```
```html
<%@ page language="java" contentType="text/html; charset=ISO-8859-1" pageEncoding="ISO-8859-1"%>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="ISO-8859-1">
<title>Hello</title>
</head>
<body>
Hello, World!
</body>
</html>
```
