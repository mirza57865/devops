<project xmlns="http://maven.apache.org/POM/4.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.google.gerrit</groupId>
  <artifactId>project-download-commands</artifactId>
  <packaging>jar</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>project-download-commands</name>
  <properties>
    <Gerrit-ApiType>plugin</Gerrit-ApiType>
    <Gerrit-ApiVersion>2.9-SNAPSHOT</Gerrit-ApiVersion>
  </properties>
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-jar-plugin</artifactId>
        <version>2.4</version>
        <configuration>
          <archive>
            <manifestEntries>
              <Gerrit-PluginName>project-download-commands</Gerrit-PluginName>
              <Gerrit-Module>com.googlesource.gerrit.plugins.download.command.project.Module</Gerrit-Module>
              <Implementation-Vendor>Gerrit Code Review</Implementation-Vendor>
              <Implementation-URL>http://code.google.com/p/gerrit/</Implementation-URL>
              <Implementation-Title>${Gerrit-ApiType} ${project.artifactId}</Implementation-Title>
              <Implementation-Version>${project.version}</Implementation-Version>
              <Gerrit-ApiType>${Gerrit-ApiType}</Gerrit-ApiType>
              <Gerrit-ApiVersion>${Gerrit-ApiVersion}</Gerrit-ApiVersion>
            </manifestEntries>
          </archive>
        </configuration>
      </plugin>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>2.3.2</version>
        <configuration>
          <source>1.7</source>
          <target>1.7</target>
          <encoding>UTF-8</encoding>
        </configuration>
      </plugin>
    </plugins>
  </build>
  <dependencies>
    <dependency>
      <groupId>com.google.gerrit</groupId>
      <artifactId>gerrit-${Gerrit-ApiType}-api</artifactId>
      <version>${Gerrit-ApiVersion}</version>
      <scope>provided</scope>
    </dependency>
  </dependencies>
  <repositories>
    <repository>
      <id>gerrit-api-repository</id>
      <url>https://gerrit-api.storage.googleapis.com/snapshot/</url>
    </repository>
  </repositories>
</project>
