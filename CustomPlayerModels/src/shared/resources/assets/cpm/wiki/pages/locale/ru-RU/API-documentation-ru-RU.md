
<a name="cpm-api-documentation"/>

# Документация API CPM
Содержание:
* [Подключение](#setup) ([Версии](#latest-versions))
* [Создание плагина](#create-your-plugin)
* [Клиентский API](#client-api)
* [Общий API](#common-api)


<a name="setup"/>

## Подключение
Добавьте API CPM в сборочный скрипт Gradle (`build.gradle`):  


<a name="manual"/>

### Вручную
Скачайте API из раздела [релизов](https://github.com/tom5454/CustomPlayerModels/releases)
и поместите его в папку разработки мода.  
Добавьте его в файл Gradle

```gradle
dependencies {
	implementation files("CustomPlayerModels-API-${cpm_api_version}.jar");
}
```


<a name="gradle"/>

### Gradle


<a name="repositories"/>

#### Репозитории

```gradle
repositories {
  maven {
    name = "tom5454 maven"
    url = "https://raw.githubusercontent.com/tom5454/maven/main"
  }
}
```


<a name="latest-versions"/>

#### Последние версии
Версия API: ![Индикатор версии API](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-API%2Fmaven-metadata.xml)

| Идентификатор версии Minecraft (фактическая версия MC) | Версия для запуска (Forge) | Версия для запуска (NeoForge) | Версия для запуска (Fabric) | Версия для запуска (Quilt) |
| ----------------- | ----------------------- | -------------------------- | ------------------------ | ----------------------- |
| 26.1 | ![26.1 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-26.1%2Fmaven-metadata.xml) | ![26.1 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-26.1%2Fmaven-metadata.xml) | ![26.1 Fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-26.1%2Fmaven-metadata.xml) | - |
| 1.21.11 | ![1.21.11 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-1.21.11%2Fmaven-metadata.xml) | ![1.21.11 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.21.11%2Fmaven-metadata.xml) | ![1.21.11 Fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.21.11%2Fmaven-metadata.xml) | - |
| 1.21.10 | ![1.21.10 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-1.21.10%2Fmaven-metadata.xml) | ![1.21.10 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.21.10%2Fmaven-metadata.xml) | ![1.21.10 Fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.21.10%2Fmaven-metadata.xml) | - |
| 1.21.8 | ![1.21.8 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-1.21.8%2Fmaven-metadata.xml) | ![1.21.8 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.21.8%2Fmaven-metadata.xml) | ![1.21.8 Fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.21.8%2Fmaven-metadata.xml) | - |
| 1.21.5 | ![1.21.5 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-1.21.5%2Fmaven-metadata.xml) | ![1.21.5 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.21.5%2Fmaven-metadata.xml) | ![1.21.5 Fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.21.5%2Fmaven-metadata.xml) | - |
| 1.21.4 | ![1.21.4 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-1.21.4%2Fmaven-metadata.xml) | ![1.21.4 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.21.4%2Fmaven-metadata.xml) | ![1.21.4 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.21.4%2Fmaven-metadata.xml) | - |
| 1.21.3 | ![1.21.3 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-1.21.3%2Fmaven-metadata.xml) | ![1.21.3 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.21.3%2Fmaven-metadata.xml) | ![1.21.3 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.21.3%2Fmaven-metadata.xml) | - |
| 1.21, (1.21.1) | ![1.21 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-1.21%2Fmaven-metadata.xml) | ![1.21 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.21%2Fmaven-metadata.xml) | ![1.21 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.21%2Fmaven-metadata.xml) | ![1.21 quilt version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Quilt-1.21%2Fmaven-metadata.xml) |
| 1.20.6 | ![1.20.6 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-1.20.6%2Fmaven-metadata.xml) | ![1.20.6 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.20.6%2Fmaven-metadata.xml) | ![1.20.6 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.20.6%2Fmaven-metadata.xml) | Используйте версию Fabric |
| 1.20.4 | ![1.20.4 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-1.20.4%2Fmaven-metadata.xml) | ![1.20.4 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.20.4%2Fmaven-metadata.xml) | ![1.20.4 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.20.4%2Fmaven-metadata.xml) | ![1.20.4 quilt version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Quilt-1.20.4%2Fmaven-metadata.xml) |
| 1.20.2 | ![1.20.2 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModelsLexForge-1.20.2%2Fmaven-metadata.xml) | ![1.20.2 neoforge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.20.2%2Fmaven-metadata.xml) | ![1.20.2 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.20.2%2Fmaven-metadata.xml) | Используйте версию Fabric |
| 1.20, (1.20.1) | ![1.20 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.20%2Fmaven-metadata.xml) | Используйте версию Forge | ![1.20 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.20%2Fmaven-metadata.xml) | ![1.20 quilt version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Quilt-1.20%2Fmaven-metadata.xml) |
| 1.19.4 | ![1.19.4 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.19.4%2Fmaven-metadata.xml) | - | ![1.19.4 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.19.4%2Fmaven-metadata.xml) | Используйте версию Fabric |
| 1.19.3 | ![1.19.3 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.19.3%2Fmaven-metadata.xml) | - | ![1.19.3 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.19.3%2Fmaven-metadata.xml) | Используйте версию Fabric |
| 1.19, (1.19.2) | ![1.19 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.19%2Fmaven-metadata.xml) | - | ![1.19 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.19%2Fmaven-metadata.xml) | Используйте версию Fabric |
| 1.18, (1.18.2) | ![1.18 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.18%2Fmaven-metadata.xml) | - | ![1.18 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.18%2Fmaven-metadata.xml) | Используйте версию Fabric |
| 1.17, (1.17.1) | ![1.17 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.17%2Fmaven-metadata.xml) | - | ![1.17 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.17%2Fmaven-metadata.xml) | - |
| 1.16, (1.16.5) | ![1.16 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.16%2Fmaven-metadata.xml) | - | ![1.16 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.16%2Fmaven-metadata.xml) | - |
| 1.15, (1.15.2) | ![1.15 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.15%2Fmaven-metadata.xml) | - | ![1.15 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.15%2Fmaven-metadata.xml) | - |
| 1.14, (1.14.4) | ![1.14 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.14%2Fmaven-metadata.xml) | - | ![1.14 fabric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-Fabric-1.14%2Fmaven-metadata.xml) | - |
| 1.12.2 | ![1.12 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.12.2%2Fmaven-metadata.xml) | - | - | - |
| 1.10.2 | ![1.10 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.10.2%2Fmaven-metadata.xml) | - | - | - |
| 1.8 | ![1.8 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.8%2Fmaven-metadata.xml) | - | - | - |
| 1.7.10 | ![1.7 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.7.10%2Fmaven-metadata.xml) | - | - | - |
| 1.6.4 | ![1.6 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.6.4%2Fmaven-metadata.xml) | - | - | - |
| 1.5.2 | ![1.5 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.5.2%2Fmaven-metadata.xml) | - | - | - |
| 1.4.7 | ![1.4 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.4.7%2Fmaven-metadata.xml) | - | - | - |
| 1.2.5 | ![1.2 forge version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-1.7.10%2Fmaven-metadata.xml) | - | - | - |
| b1.7.3 | - | - | ![b1.7.3 babric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-b1.7.3%2Fmaven-metadata.xml) | - |
| BTA | - | - | ![BTA babric version badge](https://img.shields.io/maven-metadata/v?color=forestgreen&label=release&metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Ftom5454%2Fmaven%2Fmain%2Fcom%2Ftom5454%2Fcpm%2FCustomPlayerModels-BTA%2Fmaven-metadata.xml) | - |


<a name="gradleproperties"/>

#### gradle.properties
```ini
# CPM versions
cpm_api_version=<api version>
cpm_mc_version=<minecraft version>
cpm_runtime_version=<runtime version>
```


<a name="dependencies-using-fg2"/>

#### Зависимости при использовании FG2
```gradle
dependencies {
  compile "com.tom5454.cpm:CustomPlayerModels-API:${project.cpm_api_version}"
  deobfProvided "com.tom5454.cpm:CustomPlayerModels-${project.cpm_mc_version}:${project.cpm_runtime_version}"
}
```


<a name="dependencies-using-fg3"/>

#### Зависимости при использовании FG3+

```gradle
dependencies {
  /* minecraft dependency is here */

  compileOnly "com.tom5454.cpm:CustomPlayerModels-API:${project.cpm_api_version}"
  runtimeOnly fg.deobf("com.tom5454.cpm:CustomPlayerModels-${project.cpm_mc_version}:${project.cpm_runtime_version}")
}
```


<a name="dependencies-using-neogradle"/>

#### Зависимости при использовании NeoGradle

```gradle
dependencies {
  /* minecraft dependency is here */

  compileOnly "com.tom5454.cpm:CustomPlayerModels-API:${project.cpm_api_version}"
  runtimeOnly "com.tom5454.cpm:CustomPlayerModels-${project.cpm_mc_version}:${project.cpm_runtime_version}"
}
```


<a name="dependencies-using-fabric"/>

#### Зависимости при использовании Fabric

```gradle
dependencies {
  /* minecraft dependency is here */
  
  compileOnly "com.tom5454.cpm:CustomPlayerModels-API:${project.cpm_api_version}"
  modRuntimeOnly "com.tom5454.cpm:CustomPlayerModels-Fabric-${project.cpm_mc_version}:${project.cpm_runtime_version}"
}
```


<a name="dependencies-using-voldeloom"/>

#### Зависимости при использовании Voldeloom

```gradle
dependencies {
  /* minecraft dependency is here */
  
  compileOnly "com.tom5454.cpm:CustomPlayerModels-API:${project.cpm_api_version}"
  //1.4.7, 1.5.2
  coremodImplementation ("com.tom5454.cpm:CustomPlayerModels-${project.cpm_mc_version}:${project.cpm_runtime_version}") {
    copyToFolder("coremods")
  }
  //1.6.4
  modRuntimeOnly "com.tom5454.cpm:CustomPlayerModels-${project.cpm_mc_version}:${project.cpm_runtime_version}"
}
```

Для 1.2.5:  

```gradle
volde {
	runs {
		client {
			programArg "Dev"
			vmArg "-Dcpmcore.deobf=true"
			vmArg "-Dcpmcore.env.client=true"
			vmArg "-javaagent:\"" + file("CustomPlayerModels-${project.cpm_runtime_version}.jar").absolutePath + "\""
		}
	}
}

dependencies {
  /* minecraft dependency is here */
  
  compileOnly "com.tom5454.cpm:CustomPlayerModels-API:${project.cpm_api_version}"
}
```

Поместите текущую версию мода с Modrinth в корневую папку проекта, иначе Java-агент не загрузится.


<a name="create-your-plugin"/>

## Создание плагина

Создайте класс, реализующий `ICPMPlugin`.

```java
public class CPMCompat implements ICPMPlugin {
	public void initClient(IClientAPI api) {
		//Init client
	}
	
	public void initCommon(ICommonAPI api) {
		//Init common
	}
	
	public String getOwnerModId() {
		return "example_mod";
	}
}
```


<a name="forge-125"/>

### Forge 1.2.5
Загрузчик плагинов пока не реализован.


<a name="forge-and-neo"/>

### Forge и NeoForge (0.6.26+)
Добавьте аннотацию `@CPMPlugin` к классу плагина.  
Это устраняет необходимость отправлять IMC-сообщение и позволяет создавать плагины для нескольких загрузчиков и версий.  


<a name="forge-112-and-lower"/>

### Forge 1.12 и ниже
Отправьте IMC-сообщение с полным именем класса плагина.  
`FMLInterModComms.sendMessage("customplayermodels", "api", "com.example.mod.CPMCompat");`


<a name="forge-116-and-up"/>

### Forge 1.16 и выше
Отправьте IMC-сообщение. 
 
```java
public MyMod() {
	...
	FMLJavaModLoadingContext.get().getModEventBus().addListener(this::enqueueIMC);
	...
}
	
private void enqueueIMC(final InterModEnqueueEvent event)  {
	InterModComms.sendTo("cpm", "api", () -> (Supplier<?>) () -> new CPMCompat());
	...
}
```


<a name="fabric"/>

### Fabric
Зарегистрируйте класс плагина как точку входа в fabric.mod.json следующим образом:

```json
"entrypoints": {
    "cpmapi": [ "com.example.mod.CPMCompat" ]
}
```


<a name="bukkit-spigot-paper"/>

### Bukkit, Spigot, Paper (0.4.1+)
Зарегистрируйте плагин через менеджер служб; метод `initCommon` плагина будет вызван с экземпляром `ICommonAPI`.

```java
RegisteredServiceProvider<CPMPluginRegistry> rsp = getServer().getServicesManager().getRegistration(CPMPluginRegistry.class);
if (rsp != null)
	rsp.getProvider().register(new CPMCompat());
else
	log.info("Customizable Player Models plugin not installed, compat disabled");
```


<a name="client-api"/>

## Клиентский API


<a name="voice-animation"/>

### Голосовая анимация
Зарегистрируйте поставщик уровня громкости голоса.  
`IClientAPI:registerVoice(Player.class, player -> voiceLevel);`  
[Player.class](#client-playerclass)  

Зарегистрируйте поставщик уровня громкости голоса. (Вариант с UUID) (0.6.0+)  
`IClientAPI:registerVoice(playerUUID -> voiceLevel);`  

Зарегистрируйте поставщик состояния отключения микрофона. (0.6.0+)  
`IClientAPI:registerVoiceMute(Player.class, player -> voiceMuted);`  
[Player.class](#client-playerclass)  

Зарегистрируйте поставщик состояния отключения микрофона. (Вариант с UUID) (0.6.0+)  
`IClientAPI:registerVoiceMute(playerUUID -> voiceMuted);`  


<a name="rendering-api"/>

### API отрисовки
Создайте средство отрисовки игрока для отображения моделей CPM на любой человекоподобной сущности.  
`PlayerRenderer<Model, ResourceLocation, RenderType, MultiBufferSource, GameProfile> renderer = IClientAPI.createPlayerRenderer(Model.class, ResourceLocation.class, RenderType.class, MultiBufferSource.class, GameProfile.class)`  
Для 1.12 и ниже используйте:  
`RetroPlayerRenderer<Model, GameProfile> renderer = IClientAPI.createPlayerRenderer(Model.class, GameProfile.class);`  
[Model.class](#client-modelclass)  
[ResourceLocation.class](#client-resourcelocationclass)  
[RenderType.class](#client-rendertypeclass)  
[MultiBufferSource.class](#client-multibuffersourceclass)  
[GameProfile.class](#client-gameprofileclass)  


<a name="rendering-an-entity-with-cpm-model"/>

#### Отрисовка сущности с моделью CPM
1. Перед отрисовкой задайте GameProfile или LocalModel в средстве отрисовки.  
`setGameProfile(gameProfile)`: отрисовка модели игрока  
`setLocalModel(localModel)`: отрисовка локальной модели, [загрузка локальной модели](#loading-a-local-model)  
2. Задайте базовую модель; она должна быть моделью Humanoid или Biped: `setRenderModel(model)`
3. Задайте фабрику RenderType по умолчанию для 1.16+: например, для полупрозрачной сущности: `setRenderType(RenderType::entityTranslucent)`.
4. Задайте позу модели и примените анимации с помощью `getAnimationState()`, `setActivePose(pose)`, `setActiveGesture(gesture)`.
5. Вызовите `preRender(buffers, mode)` (или `preRender(mode)` для 1.12-)
6. Отрисуйте модель обычным способом. CPM уже внедрил своё средство отрисовки в модель. (Используйте `getDefaultRenderType()`, чтобы получить RenderType модели (1.16+)).
    1. Для отрисовки дополнительных частей (элитр, плаща, брони) вызовите: `prepareSubModel(model, type, texture)` (или `prepareSubModel(model, type)` для 1.12-)  
    2. При необходимости в 1.16+ измените RenderType части по умолчанию: например, `setRenderType(RenderType::armorCutoutNoCull)`
    3. Отрисуйте часть (используйте `getRenderTypeForSubModel(subModel)`, чтобы получить RenderType модели (1.16+)).
7. Вызовите `postRender()` для завершения отрисовки.  

Пример (1.18 Forge):

```java
import java.io.IOException;
import java.io.InputStream;

import net.minecraft.client.Minecraft;
import net.minecraft.client.model.Model;
import net.minecraft.client.model.PlayerModel;
import net.minecraft.client.model.geom.ModelLayers;
import net.minecraft.client.renderer.MultiBufferSource;
import net.minecraft.client.renderer.RenderType;
import net.minecraft.client.renderer.entity.EntityRendererProvider.Context;
import net.minecraft.client.renderer.entity.LivingEntityRenderer;
import net.minecraft.resources.ResourceLocation;

import com.mojang.authlib.GameProfile;
import com.mojang.blaze3d.vertex.PoseStack;

import com.tom.cpm.api.IClientAPI;
import com.tom.cpm.api.IClientAPI.PlayerRenderer;
import com.tom.cpm.shared.animation.AnimationEngine.AnimationMode;

public class ExampleRenderer extends LivingEntityRenderer<ExampleEntity, PlayerModel<ExampleEntity>> {
	private static PlayerRenderer<Model, ResourceLocation, RenderType, MultiBufferSource, GameProfile> renderer;

	public static void init(IClientAPI api) {
		renderer = api.createPlayerRenderer(Model.class, ResourceLocation.class, RenderType.class, MultiBufferSource.class, GameProfile.class);
		
		// TODO: replace with resource reload listeners to support resourcepacks.
		try (InputStream is = Minecraft.getInstance().getResourceManager().open(new ResourceLocation("example_mod", "models/example_entity_model.cpmmodel"))){
			renderer.setLocalModel(api.loadModel("example_entity_model", is));
		} catch (IOException e) {
			e.printStackTrace();
		}
	}

	public ExampleRenderer(Context pContext, float pShadowRadius) {
		super(pContext, new PlayerModel<>(pContext.bakeLayer(ModelLayers.PLAYER), false), pShadowRadius);

	}

	@Override
	public void render(ExampleEntity pEntity, float pEntityYaw, float pPartialTicks, PoseStack pMatrixStack,
			MultiBufferSource pBuffer, int pPackedLight) {
		renderer.setRenderModel(model);
		renderer.setRenderType(RenderType::entityTranslucent);
		//Pose model using renderer.getAnimationState(), setActivePose(name) or setActiveGesture(name)
		renderer.preRender(pBuffer, AnimationMode.PLAYER);
		if(renderer.getDefaultTexture() != null) {
			super.render(pEntity, pEntityYaw, pPartialTicks, pMatrixStack, pBuffer, pPackedLight);
		} else {
			renderNameTag(pEntity, pEntity.getDisplayName(), pMatrixStack, pBuffer, pPackedLight);
		}
		renderer.postRender();
	}

	@Override
	public ResourceLocation getTextureLocation(ExampleEntity pEntity) {
		return renderer.getDefaultTexture();
	}
}
```

Пока модель загружается в фоне, `renderer.getDefaultTexture()` возвращает null!


<a name="loading-a-local-model"/>

#### Загрузка локальной модели
Загрузите модель из файла `.cpmmodel`.  
`IClientAPI.loadModel(name, inputstream)`  
Используйте загруженную модель для [отрисовки сущности](#rendering-an-entity-with-cpm-model)


<a name="register-editor-generator"/>

### Регистрация генератора редактора
Зарегистрируйте генератор модели для редактора. Генераторы находятся в `Edit/Tools`.  
`IClientAPI.registerEditorGenerator("button.example_mod.example_generator", "tooltip.example_mod.example_generator", ExampleGenerator::apply);`  

```java
public class ExampleGenerator {
	public static void apply(EditorGui gui) {
		//TODO: apply the generator
		// Use gui.getEditor() to access the editor
		// Use Editor.action and ActionBuilder to make undoable changes.
		// Note: parts of the editor may change.
	}
}
```

Локализация:  
Добавьте `button.example_mod.example_generator`, `tooltip.example_mod.example_generator` в языковой файл. Используйте символы `\` для переноса строк в подсказке.


<a name="play-animation"/>

### Воспроизведение анимации (0.6.0+)
Воспроизведите заданную командную анимацию для игрока (на стороне клиента).  

Name: имя анимации  
`IClientAPI.playAnimation(name);` или  
Value: 0: сброс позы/жеста, 1: воспроизведение позы/жеста; для слоёв со значением: 0-255, для переключателя: 0-1 или -1 для смены состояния
`IClientAPI.playAnimation(name, value);`  
Возвращает: true, если анимация найдена и запущена  


<a name="detect-animation"/>

### Проверка анимации (0.6.14+)
Проверьте, воспроизводится ли анимация у игрока  
`int value = IClientAPI.getAnimationPlaying(name);`  
Возвращает: значение анимации (слой со значением: 0-255, остальные анимации: 0-1), -1, если анимация не существует  

<a name="get-animation-max-value"/>

### Получение максимального значения анимации (0.6.20+)
Получите максимальное значение заданной анимации (со значением или переключаемой)  
`int value = IClientAPI.getAnimationMaxValue(name);`  
Возвращает: максимальное значение для слоёв (заданное в анимации значение 0-255; для переключателя: всегда 1; -1, если анимация не существует или не является слоем)  

<a name="client-networking"/>

### Сетевое взаимодействие клиента (0.6.1+)
Зарегистрируйте NBT-сообщение для отправки на сервер или рассылки другим клиентам.  
`MessageSender sender = IClientAPI.registerPluginMessage(Player.class, message_id, (player, message) -> {/*Handle message*/}, broadcastToTracking);`  
[Player.class](#client-playerclass)  
или вариант с UUID:  
`MessageSender sender = IClientAPI.registerPluginMessage(message_id, (player_uuid, message) -> {/*Handle message*/}, broadcastToTracking);`  
Используйте `MessageSender` для отправки сообщений.  
`boolean success = sender.sendMessage(message_tag);`  
Используйте независимую от платформы реализацию NBT из пакета `com.tom.cpl.nbt.*`.  
broadcastToTracking: false: отправить сообщение на сервер / true: разослать сообщение ближайшим игрокам (через сервер).  
Для сетевого взаимодействия на сервере требуется CPM 0.6.1+.  
При использовании broadcastToTracking или сообщений состояния ваш мод/плагин не требуется на сервере для пересылки пакетов; регистрировать ничего не нужно. Для получения сообщений без рассылки используйте ICommonAPI.registerPluginMessage  


<a name="state-messages"/>

#### Сообщения состояния
Последнее сообщение состояния хранится на сервере и отправляется каждому клиенту, входящему в область отслеживания (дальность прорисовки).  
`MessageSender sender = IClientAPI.registerPluginStateMessage(Player.class, message_id, (player, message) -> {/*Handle message*/});`  
[Player.class](#client-playerclass)  
или вариант с UUID:  
`MessageSender sender = IClientAPI.registerPluginMessage(message_id, (player_uuid, message) -> {/*Handle message*/});`  


<a name="tick-listener"/>

#### Обработчик игровых тиков
Можно зарегистрировать `TickEventHandler` для получения событий игровых тиков, чтобы не использовать API конкретного загрузчика.  
Вызывается после обработки тика CPM на клиенте.  
Полезно для модов интеграции, воспроизводящих пользовательские анимации (например, OSC).  
`IClientApi.registerClientGameTick((paused) -> {...});`  
Обработчик вызывается даже при приостановленной игре; это состояние передаётся в параметре.


<a name="class-map"/>

### Соответствие классов
Классы зависят от версии Minecraft и загрузчика модов.  

<a name="client-playerclass"/>

#### Клиентский Player.class
Minecraft Forge 1.12 и ниже: `EntityPlayer.class`  
Minecraft Forge 1.16 и Fabric: `PlayerEntity.class`  
Minecraft Forge 1.17 и выше: `Player.class` из `net.minecraft.*`  


<a name="client-modelclass"/>

#### Клиентский Model.class
Minecraft Forge 1.16+ и Fabric: `Model.class` из `net.minecraft.client.*`  
Minecraft Forge 1.12 и ниже: `ModelBase.class`  


<a name="client-resourcelocationclass"/>

#### Клиентский ResourceLocation.class
Minecraft Forge: `ResourceLocation.class`  
Fabric: `Identifier.class`  


<a name="client-rendertypeclass"/>

#### Клиентский RenderType.class
Minecraft Forge: `RenderType.class`  
Fabric: `RenderLayer.class`  


<a name="client-multibuffersourceclass"/>

#### Клиентский MultiBufferSource.class
Minecraft Forge 1.16: `IRenderTypeBuffer.class`  
Minecraft Forge (1.17+): `MultiBufferSource.class`  
Fabric: `VertexConsumerProvider.class`  


<a name="client-gameprofileclass"/>

#### Клиентский GameProfile.class
GameProfile из AuthLib: `com.mojang.authlib.GameProfile`  


<a name="common-api"/>

## Общий API


<a name="set-model"/>

### Установка модели (0.4.1+)
Задайте модель игрока  
`ICommonAPI.setPlayerModel(Player.class, playerObj, base64Model, forced, persistent);`  
или  
`ICommonAPI.setPlayerModel(Player.class, playerObj, modelFile, forced);`  
Создайте ModelFile с помощью `ModelFile.load(file);` или `ModelFile.load(inputstream);`  
или  
`ICommonAPI.resetPlayerModel(Player.class, playerObj);`  
сбросьте модель, заданную сервером  
[Player.class](#common-playerclass)  


<a name="jump"/>

### Прыжок (0.4.1+)
Воспроизведите анимацию прыжка для игрока.  
`ICommonAPI.playerJumped(Player.class, playerObj);`  
[Player.class](#common-playerclass)


<a name="play-animation"/>

### Воспроизведение анимации (0.6.0+)
Воспроизведите заданную командную анимацию для игрока (на стороне сервера).  

Name: имя анимации  
`ICommonAPI.playAnimation(Player.class, playerObj, name);` или  
`ICommonAPI.playAnimation(Player.class, playerObj, name, value);`  
Value: 0: сброс позы/жеста, 1: воспроизведение позы/жеста; для слоёв со значением: 0-255, для переключателя: 0-1 или -1 для смены состояния  
[Player.class](#common-playerclass)


<a name="server-networking"/>

### Сетевое взаимодействие сервера (0.6.1+)
Зарегистрируйте NBT-сообщение для получения сообщений без рассылки и отправки сообщений клиентам.  
`MessageSender<Player> sender = ICommonAPI.registerPluginMessage(Player.class, message_id, (player, message) -> {/*Handle message*/});`  
[Player.class](#client-playerclass)  
Используйте `MessageSender` для отправки сообщений.  
`boolean success = sender.sendMessageTo(player, message_tag);`  
или разошлите ближайшим игрокам:  
`sender.sendMessageToTracking(player, message_tag, sendToSelf);`  
Используйте независимую от платформы реализацию NBT из пакета `com.tom.cpl.nbt.*`.  
sendToSelf: отправить сообщение игроку, указанному в аргументе 1


<a name="detect-animation"/>

### Проверка анимации (0.6.9+)
Проверьте, воспроизводится ли анимация у игрока  
`int value = ICommonAPI.getAnimationPlaying(Player.class, playerObj, name);`  
Возвращает: значение анимации (слой со значением: 0-255, остальные анимации: 0-1), -1, если анимация не существует  
[Player.class](#common-playerclass)  


<a name="class-map"/>

### Соответствие классов
Классы зависят от версии Minecraft и загрузчика модов.  

<a name="common-playerclass"/>

#### Общий Player.class
Minecraft Forge 1.12 и ниже: `EntityPlayer.class`  
Minecraft Forge 1.16 и Fabric: `PlayerEntity.class`  
Minecraft Forge 1.17 и выше: `Player.class` из `net.minecraft.*`  
Bukkit: `Player.class` из `org.bukkit.entity`.
