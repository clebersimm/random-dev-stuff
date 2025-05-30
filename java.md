# Java

## Spring   

### Spring boot

Use JDK 21 or higher   

```yml
ENTRYPOINT ["java","-XX:TieredStopAtLevel=1","-XX:MaxRAMPercentage=70","-XX:+UseZGC","-XX:+UseDynamicNumberOfGCThreads","-Xss512k","-XX:SoftMaxHeapSize=64m","-Xmx128m","-XX:ZUncommitDelay=30","-Dspring.main.lazy-initialization=true","","org.springframework.boot.loader.JarLauncher"]
```
-XX+UseZGC: use Z gen garbage collector https://wiki.openjdk.org/display/zgc/Main   
-Xss: "Set the stack size for Java thread" https://eclipse.dev/openj9/docs/xss/

Example running on local machine, the ZGC give back to the OS the memory:   
![memory_usage](https://github.com/clebersimm/random-dev-stuff/assets/5503854/3009d32c-9f38-4cf6-8a3c-2c42b32fa2fd)


## Tools

### Sdkman  

"The Software Development Kit Manager"   
https://sdkman.io/
