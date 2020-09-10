```java
// spring boot 构建版本时记得替换原有的jar包，替换为源码jar，不是可执行jar。
```

```xml
<!--在要打包的项目pom添加插件-->

<plugins>
    <plugin>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-maven-plugin</artifactId>
    </plugin>
    <plugin>
        <artifactId>maven-deploy-plugin</artifactId>
        <configuration>
            <altDeploymentRepository>
           		internal.repo::default::file://${project.build.directory}/mvn-repo/repository
            </altDeploymentRepository>
        </configuration>
    </plugin>
</plugins>

```

```xml
<!--引入-->
<!-- raw.githubusercontent.com 可能国内无法访问  自行修改 hosts 文件 -->
<!-- 贴个目前能用的 151.101.108.133   --2020.09.10 -->


<dependency>
    <groupId>cn.ingrun</groupId>
    <artifactId>utils</artifactId>
    <version>0.0.1-SNAPSHOT</version>
</dependency>

<repositories>
    <repository>
        <id>github-maven-repository</id>
        <url>https://raw.githubusercontent.com/ingRun/github-maven-repository/master/repository</url>
    </repository>
</repositories>
```

