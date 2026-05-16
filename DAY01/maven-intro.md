# Linux, Git & GitHub, Shell Scripting, Maven Build Tool

# Maven Build Tool

## Why do we need Maven?

Maven is used to automate the **build process** in Java projects.

### Build

A **build** is the process of creating deployable packages such as:

* JAR
* WAR
* EAR

Maven helps developers:

* Compile code
* Download dependencies
* Run tests
* Package applications
* Deploy applications

---

# Flow Explanation

## Developer → GitHub → Maven → Tomcat

```text
Developer
    ↓
Writes Java Code
    ↓
Pushes code to GitHub
    ↓
Maven downloads dependencies and builds project
    ↓
Maven creates JAR/WAR/EAR package
    ↓
Deploy package into Tomcat Server
    ↓
Application runs on server
```

---

# What is Maven?

* Maven is a popular **build automation** and **project management** tool mainly used for Java projects.
* Developed by the Apache Software Foundation.
* Maven is open source.
* Maven is platform independent.
* Maven is not executable software (`.exe`).
* It is distributed as `.zip` or `.tar.gz`.

## Download Maven

[Apache Maven Download Page](https://maven.apache.org/download.cgi?utm_source=chatgpt.com)

---

# Build Tools

## Java

* Ant
* Maven
* Gradle

## Python

* PyBuilder

## .NET

* MS Build
* NAnt

## Ruby

* Rake

## Go

* Go Build Tool

---

# What are JAR, WAR, and EAR?

## 1. Standalone Applications [JAR]

### JAR = Java Archive

Contains:

* Java code
* `.class` files

Used for:

* Standalone Java applications

---

## 2. Web Applications [WAR]

### WAR = Web Archive

Contains:

* Java code
* HTML
* CSS3
* JavaScript
* Images

WAR contains:

```text
JAR + HTML/CSS3/JS/Images
```

Used for:

* Web applications

---

## 3. Enterprise Applications [EAR]

### EAR = Enterprise Archive

Contains:

* Java code
* Web content
* Standalone modules
* Web modules

EAR contains:

```text
JAR + WAR + HTML/CSS3/JS/Images + Modules
```

Used for:

* Enterprise-level applications

---

# Maven Directory Structure

```text
bin   ---> Contains binary files (mvn, etc.)

boot  ---> Contains jar files used at runtime

conf  ---> Configuration files (settings.xml)

lib   ---> Contains library files (jars)
```

---

# Default Build Script File Names

| Build Tool | File Name      |
| ---------- | -------------- |
| Maven      | `pom.xml`      |
| Ant        | `build.xml`    |
| Gradle     | `build.gradle` |

> Gradle does not use XML.

---

# Maven Installation

## System Requirements

### Maven 3.9+ requires:

* JDK 8 or above
* Approximately 10 MB disk space
* Any operating system

> Startup scripts are available for both Linux and Windows.

---

# Important Note

All external software is generally stored in:

```bash
/opt
```

---

# Step-by-Step Maven Installation on Linux (EC2)

## Step 0: Launch EC2 Machine

Launch an EC2 instance and connect to it.

---

# Step 1: Switch to Root User

```bash
sudo su -
```

---

# Step 2: Install Java

## Update Packages

```bash
yum update -y
```

## Check Java Compiler

```bash
javac -version
```

## Search Java Packages

```bash
sudo yum search java | grep -i OpenJDK
```

## Check Java Version

```bash
java -version
```

---

## Install Java 21

```bash
sudo yum install java-21-openjdk-devel -y
```

---

# Step 3: Install Maven

## Pre-Requisite

Java (JDK) must be installed before Maven.

## Verify Java

```bash
javac -version
```

---

## 1. Login as Root User and Move to `/opt`

```bash
sudo su -

cd /opt/
```

## Install Required Utilities

```bash
yum install wget unzip tree git -y
```

---

## 2. Download Maven

### Maven 3.9.10

```bash
wget https://dlcdn.apache.org/maven/maven-3/3.9.10/binaries/apache-maven-3.9.10-bin.zip
```

### Maven 3.9.11

```bash
wget https://dlcdn.apache.org/maven/maven-3/3.9.11/binaries/apache-maven-3.9.11-bin.zip
```

### Maven 3.9.12

```bash
wget https://dlcdn.apache.org/maven/maven-3/3.9.12/binaries/apache-maven-3.9.12-bin.zip
```

### Maven 3.9.15

```bash
wget https://dlcdn.apache.org/maven/maven-3/3.9.15/binaries/apache-maven-3.9.15-bin.zip
```

---

## Extract Maven

```bash
unzip apache-maven-3.9.15-bin.zip
```

---

# Step 4: Set Environment Variables

Edit `.bash_profile`

```bash
vi ~/.bash_profile
```

Add the following lines:

```bash
export M2_HOME=/opt/apache-maven-3.9.15
export PATH=$PATH:$M2_HOME/bin
```

---

# Step 5: Reload Profile

```bash
source ~/.bash_profile
```

---

# Step 6: Verify Maven Installation

```bash
mvn -version
```

or

```bash
mvn -v
```

Expected output will display:

* Maven version
* Java version
* Maven home path
* OS details
