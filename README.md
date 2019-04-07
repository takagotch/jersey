### jersey
---
https://jersey.github.io/

```
<dependency>
  <groupId>jakarta.ws.rs</groupId>
  <artifactId>jakarta.ws.rs-api</artifactId>
  <version>2.1.5</version>
  <scope>provided</scope>
</dependency>

<dependency>
  <groupId>org.glassfish.jersey.containers</groupId>
  <artifactId>jersey-container-servlet</artifactId>
  <version>2.28</version>
</dependency>
<dependency>
  <groupId>org.glassfish.jersey.core</groupId>
  <artifactId>jersey-client</artifactId>
  <version>2.28</version>
</dependency>
```

```java
// https://jersey.github.io/documentation/latest/jaxrs-resources.html
package org.glassfish.jersey.examples.hellowrold;

import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.Produces;

@Path("helloworld")
public class HelloWorldResource {
  public static final String CLICHED_MESSAGE = "Hello World!";
@GET
@Produces("text/plain")
  public String getHello() {
    return CLICHED_MESSAGE;
  }
}

@Path("/users/{username}")
public class UserResource {
  
  @GET
  @Produces("text/xml")
  public String getUser(@PathParam("username") String userName) {
  }
}

@PUT
public Response putContainer() {
  System.out.println("PUT CONTAINER " + container);
  
  URI uri = uriInfo.getAbsolutePath();
  Container c = new Container(container, uri.toString());
  
  Response r;
  if (!MemoryStore.MS.hasContainer(c)) {
    r = Response.created(uri).build();
  } else {
    r = Response.noContent().build();
  }
  
  MemoryStore.MS.createContainer(c);
  return r;
}

@Path("/myResource")
@Produces("text/plain")
public class SomeResource {
  @GET
  public String doGetPlainText() {
  }
  
  @GET
  @Produces("text/html")
  public String doGetAsHtml() {
  }
}

```
