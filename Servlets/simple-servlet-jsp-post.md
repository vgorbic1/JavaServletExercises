## Simple Servlet

####Task:
Write a simple Java servlet and JSP script that prints anything that it takes from parameter "word" via POST request.

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

      protected void doPost(HttpServletRequest request, HttpServletResponse response)
                  throws ServletException, IOException {
            request.setAttribute("word", request.getParameter("word"));
            request.getRequestDispatcher("/hello.jsp").forward(request, response);
      }

}
```
```
<%@ page language="java" contentType="text/html; charset=ISO-8859-1" pageEncoding="ISO-8859-1"%>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="ISO-8859-1">
<title>Hello</title>
</head>
<body>
<form action="hello.do" method="post">
  <input type="text" name="w" />
  <input type="submit" value="Submit" />
</form>
${word}
</body>
</html>
```
