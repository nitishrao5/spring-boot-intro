## **unit testing**
| Testing Type        | Tools Used          | Purpose |
|---------------------|--------------------|---------|
| **Unit Testing**    | `MockMvc`, `JUnit`, `Mockito` | Tests **controllers** without running the server |
| **Integration Test** | `TestRestTemplate`, `MockMvc` | Tests **multiple layers** (Controller + Service + DB) |
| **Database Test**   | `H2`, `Testcontainers` | Tests **repository layer** with an actual DB |
| **E2E Test**        | `RestAssured`, `Postman` | Simulates real HTTP requests |

## **Acutator**
| Feature | Configuration |
|---------|--------------|
| **Enable Actuator** | Add `spring-boot-starter-actuator` dependency |
| **Expose Endpoints** | `management.endpoints.web.exposure.include=*` |
| **View Metrics** | `/actuator/metrics`, `/actuator/health` |
| **Secure Endpoints** | Add `spring-boot-starter-security` |
| **Integrate Prometheus** | Add `micrometer-registry-prometheus` |
| **Create Custom Endpoints** | Use `@Endpoint` annotation |

## **Improve performance**
| Optimization Area   | Techniques |
|--------------------|------------|
| **Startup Time**   | Lazy loading, disabling unused auto-configurations |
| **Memory Usage**   | JVM tuning, GraalVM native compilation |
| **Database**       | Connection pooling, indexing, query optimization, caching |
| **API Performance** | Gzip compression, pagination, async processing |
| **Logging & Monitoring** | Reduce logging, use Actuator, enable tracing |
| **Deployment** | Docker, Kubernetes scaling, HPA |
| **Concurrency** | Tomcat thread pool tuning, ExecutorService |

### **Different Scopes of Spring Beans**

In Spring, a **bean scope** defines the lifecycle and visibility of a bean within the Spring container. Spring provides **six** types of bean scopes:

| Scope | Description | Usage |
|--------|------------|--------|
| **singleton** | A single instance per Spring container (default scope) | Shared across all requests |
| **prototype** | A new instance is created every time it is requested | Useful for stateful beans |
| **request** | A new bean instance is created for each HTTP request | Web applications |
| **session** | A new bean instance is created for each HTTP session | Session-based user data |
| **application** | A single instance is shared across the entire application | Application-wide storage |
| **websocket** | A new bean instance is created for each WebSocket session | WebSocket communication |

