### Docker config


**Spring boot**   

```yml
ENTRYPOINT ["java","-XX:TieredStopAtLevel=1","-XX:MaxRAMPercentage=70","-XX:+UseZGC","-XX:+UseDynamicNumberOfGCThreads","-Xss512k","-XX:SoftMaxHeapSize=64m","-Xmx128m","-XX:ZUncommitDelay=30","-Dspring.main.lazy-initialization=true","","org.springframework.boot.loader.JarLauncher"]
```
