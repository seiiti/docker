maven
=====

Base image for Java build environment.

- Debian 8.5
- Oracle JDK 8
- Git
- Subversion
- Maven

## Download

```sh
docker pull seiiti/maven
```

## Run

### 1. Start container

Start container named `[container]` from image `seiiti/maven`:

```sh
docker run --detach --name=[container] seiiti/maven
```

### 2. (Optional) Copy Maven's settings.xml

Copy `settings.xml` file from host, usually containing your repositories'
credentials, if necessary.

```sh
docker cp ~/.m2/settings.xml /root/.m2/
```

### 3. Start Bash

```sh
docker exec --interactive --tty [container] /bin/bash
```
