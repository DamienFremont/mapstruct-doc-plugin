# MapStruct Doc - Maven & Gradle Plugin

[![License](https://img.shields.io/badge/License-Apache%202.0-yellowgreen.svg)](https://github.com/DamienFremont/mapstruct-doc/blob/main/LICENSE)
[![Follow](https://img.shields.io/twitter/follow/Damien_Fremont?style=social&logo=X)](https://twitter.com/intent/follow?screen_name=Damien_Fremont)

:warning: **WORK IN PROGRESS !!!**

Liked some of my work? Buy me a coffee (or more likely a beer)

<a href="https://www.buymeacoffee.com/damienfremont" target="_blank"><img src="https://bmc-cdn.nyc3.digitaloceanspaces.com/BMC-button-images/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>

- [What is MapStruct Doc?](#what-is-mapstruct-doc)
- [Requirements](#requirements)
- [Using MapStruct Doc](#using-mapstruct-doc)
    - [Maven](#maven)
- [Contributors](#contributors)
- [Licensing](#licensing)

---

## What is MapStruct Doc?

MapStruct Doc is a
Java [annotation processor](https://docs.oracle.com/javase/6/docs/technotes/guides/apt/index.html)
for the generation of documentation for mapping interface (CSV, Markdown or
AsciiDoc).

![alt text](documentation/diagrams.jpg)

At compile time MapStruct will generate a file for each interface.

## Requirements

MapStruct Doc requires Java 1.8 or later.

## Using MapStruct Doc

### Maven

For Maven-based projects, add the following to your POM file in order to use
MapStruct Doc:

```xml

<project>
  ...
  <properties>
    <mapstruct-doc.version>1.5.5-SNAPSHOT</mapstruct-doc.version>
  </properties>
  ...
  <build>
    <plugins>
      ...
      <plugin>
        <groupId>com.damienfremont.mapstruct</groupId>
        <artifactId>mapstruct-doc-maven-plugin</artifactId>
        <version>${mapstruct-doc.version}</version>
        <configuration>
          <include>com.damienfremont.mapstruct.CarMapper</include>
        </configuration>
        <executions>
          <execution>
            <goals>
              <goal>generate</goal>
            </goals>
            <phase>install</phase>
          </execution>
        </executions>
      </plugin>
    </plugins>
  </build>
</project>
```

And execute any of the following commands:

```bash
mvn install -DskipTests
```

```bash
mvn com.damienfremont.mapstruct:mapstruct-doc-maven-plugin:1.5.5-SNAPSHOT:generate
```

## Contributors

![GitHub Contributors Image](https://contrib.rocks/image?repo=DamienFremont/mapstruct-doc)

## Licensing

Copyright (c) 2023 Damien FREMONT.

Licensed under the Apache License version 2.0, available
at http://www.apache.org/licenses/LICENSE-2.0