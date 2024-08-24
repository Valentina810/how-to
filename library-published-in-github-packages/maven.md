# Инструкция по подключению библиотеки, опубликованной на github packages для maven
### 1. Добавить в pom.xml в секцию <repositories>:
```xml
    <repositories>
        <repository>
            <id>github</id>
            <url>https://maven.pkg.github.com/valentina810/http-request-converter-to-curl</url>
            <releases>
                <enabled>true</enabled>
            </releases>
            <snapshots>
                <enabled>true</enabled>
            </snapshots>
        </repository>
    </repositories>
```
### 2. Добавить саму зависимость:
```xml
  <dependencies>
        <dependency>
            <groupId>com.github.valentina810</groupId>
            <artifactId>http-request-converter-to-curl</artifactId>
            <version>${http-request-converter-to-curl.version}</version>
        </dependency>
  </dependencies>
```
### 3. Настроить учетные данные
Для этого  нужно добавить ваши учетные данные в файл **~/.m2/settings.xml**. Если такого файла нет, его нужно создать. Вот пример содержимого с данными УЗ github:
```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 https://maven.apache.org/xsd/settings-1.0.0.xsd">

    <servers>
        <server>
            <id>github</id>
            <username>your_github_login</username>
            <password>your_github_token</password>
        </server>
    </servers>
</settings>
```
### 4. Как создать токен
Токен создается в профиле в [настройках](https://github.com/settings/tokens).  
Для доступа к GitHub Packages, токен должен иметь права на **read:packages** и **repo**.
