# check-restrain-maven-plugin
maven自定义插件，约束自己项目中禁止引入某些jar包，比如禁止引入fastjson

# 使用方式
## 1
对项目进行install

## 2
在自己的maven setting.xml中配置插件
```
  <pluginGroups>
    <pluginGroup>org.example</pluginGroup>
  </pluginGroups>
```
## 3
在自己的项目中配置插件
```
            <plugin>
                <groupId>org.example</groupId>
                <artifactId>check-restrain-maven-plugin</artifactId>
                <version>1.0-SNAPSHOT</version>
                <configuration>
                    <!-- 需要排除的jar包-->
                    <excludes>
                        <exclude>com.alibaba:fastjson</exclude>
                    </excludes>
                </configuration>
                <executions>
                    <execution>
                        <goals>
                            <goal>check</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
```

