## Simple Servlet

####Task:
Write a simple Java servlet that prints "Hello, World!" to the browser.

####Given code:
```java
package com.sample;
import java.io.IOException;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

/* Write your code here */

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
public class helloServlet extends HttpServlet {

	  protected void doGet(HttpServletRequest request, HttpServletResponse response)
			      throws ServletException, IOException {
		    response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        out.println("Hello, World!");
    }
    
}
```
