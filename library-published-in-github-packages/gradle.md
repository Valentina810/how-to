# Инструкция по подключению библиотеки, опубликованной на github packages для gradle

### 1. Добавить репозиторий в build.gradle.kts:

```groovy
repositories {
        maven {
            url = uri("https://maven.pkg.github.com/valentina810/http-request-converter-to-curl")
                credentials {
                    username = project.findProperty("gpr.user") as String? ?: System.getenv("GITHUB_ACTOR")
                    password = project.findProperty("gpr.token") as String? ?: System.getenv("GITHUB_TOKEN")
                }
        }
}
```

### 2. Добавить саму зависимость:

```groovy
dependencies {
        implementation("com.github.valentina810:http-request-converter-to-curl:${project.findProperty("http-request-converter-to-curl.version")}")
}
```

### 3. Настроить учетные данные

Добавьте ваши учетные данные в файл gradle.properties:

```groovy
gpr.user=your_github_login
gpr.token=your_github_token
```

Или настройте переменные окружения:
```groovy
GITHUB_ACTOR (github_login)
GITHUB_TOKEN (github_token)
```

### 4. Как создать токен

Токен создается в профиле в [настройках](https://github.com/settings/tokens).  
Для доступа к GitHub Packages, токен должен иметь права на **read:packages** и **repo**.
