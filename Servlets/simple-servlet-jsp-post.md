## Simple Servlet

####Task:
Write a simple Java servlet and JSP script that prints "Hello, World!" and takes parameter "World" for POST request.

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
            request.setAttribute("par", request.getParameter("par"));
            request.getRequestDispatcher("/hello.jsp").forward(request, response);
      }

}
```
