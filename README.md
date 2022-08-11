# Comandos Uteis Maven

### Indicando qual a VM que será utilizada no projeto:

```
  <properties>
    <maven.compiler.target>1.8</maven.compiler.target>
    <maven.compiler.source>1.8</maven.compiler.source>
  </properties>
```


### Gerando .jar do projeto:
```
 <build>
    <plugins>      
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-jar-plugin</artifactId>
        <version>3.0.2</version>
        <configuration>
          <archive>
            <manifest>
              <mainClass>${my.mainClass}</mainClass>
              <addClasspath>true</addClasspath>
              <classpathPrefix>lib</classpathPrefix>
            </manifest>
          </archive>
        </configuration>
      </plugin>
    </plugins>
  </build>
```

#### No exemplo acima, não é indicado a class main, ela pode ser inserida no pom, ou até indicada na compilição atraves do comando: 
```  
  mvn install -D my.mainClass=br.com.enviorede.SuaClasseMain
```