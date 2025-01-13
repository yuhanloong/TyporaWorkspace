# 1.WebClient

调用第三方接口利器

- RestTemplate：阻塞同步，已过时
- WebClient：响应式异步，正在推广

与 RestTemplate 相比，WebClient 有如下优势：

- 非阻塞，Reactive 的，并支持更高的并发性和更少的硬件资源。
- 提供利用 Java8 lambdas 的函数 API。
- 支持同步和异步方案。
- 支持从服务器向上或向下流式传输。

依赖：

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-webflux</artifactId>
</dependency>
```

```java
/**
 * create方式 - get请求
 * 获取所有记录
 */
@Test
void test_01() {
    WebClient webClient = WebClient.create("http://localhost:8080");
    Map<String, Object> requestResultMap = webClient
            .get()
            .uri("/user")
            .retrieve()
            .bodyToFlux(Map.class)
            .blockFirst();
    System.out.println("code：" + requestResultMap.get("code"));
    System.out.println("msg：" + requestResultMap.get("msg"));
    System.out.println("data：" + requestResultMap.get("data"));
}

/**
 * create方式 - get请求
 * 根据 id 获取记录
 */
@Test
void test_02() {
    WebClient webClient = WebClient.create("http://localhost:8080");
    Map<String, Object> requestResultMap = webClient
            .get()
            .uri("/user/1")
            .retrieve()
            .bodyToFlux(Map.class)
            .blockFirst();
    System.out.println("code：" + requestResultMap.get("code"));
    System.out.println("msg：" + requestResultMap.get("msg"));
    System.out.println("data：" + requestResultMap.get("data"));
}

/**
 * create方式 - post请求
 * 添加记录
 */
@Test
void test_03() {
    WebClient webClient = WebClient.create("http://localhost:8080");
    // 请求参数
    User user = new User();
    user.setName("aaa");
    user.setAge(18);
    Map<String, Object> requestResultMap = webClient
            .post()
            .uri("/user")
            .bodyValue(user)
            .retrieve()
            .bodyToFlux(Map.class)
            .blockFirst();
    System.out.println("code：" + requestResultMap.get("code"));
    System.out.println("msg：" + requestResultMap.get("msg"));
    System.out.println("data：" + requestResultMap.get("data"));
}

/**
 * create方式 - put请求
 * 根据 id 修改记录
 */
@Test
void test_04() {
    WebClient webClient = WebClient.create("http://localhost:8080");
    // 请求参数
    User user = new User();
    user.setId("1");
    user.setName("zhangsan2");
    user.setAge(10);
    Map<String, Object> requestResultMap = webClient
            .put()
            .uri("/user")
            .bodyValue(user)
            .retrieve()
            .bodyToFlux(Map.class)
            .blockFirst();
    System.out.println("code：" + requestResultMap.get("code"));
    System.out.println("msg：" + requestResultMap.get("msg"));
    System.out.println("data：" + requestResultMap.get("data"));
}

/**
 * create方式 - delete请求
 * 根据 id 删除记录
 */
@Test
void test_05() {
    WebClient webClient = WebClient.create("http://localhost:8080");
    Map<String, Object> requestResultMap = webClient
            .delete()
            .uri("/user/1")
            .retrieve()
            .bodyToFlux(Map.class)
            .blockFirst();
    System.out.println("code：" + requestResultMap.get("code"));
    System.out.println("msg：" + requestResultMap.get("msg"));
    System.out.println("data：" + requestResultMap.get("data"));
}
```

