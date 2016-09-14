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

Copy to container your local `settings.xml` file, usually containing your 
repositories' credentials, if necessary.

```sh
docker cp ~/.m2/settings.xml [container]:/root/.m2/
```

### 3. Start Bash

```sh
docker exec --interactive --tty [container] /bin/bash
```

### 4. (Optional) Create mvnrepo.tar.gz

```sh
docker exec [container] /root/mvnrepo-create
docker cp [container]:/root/mvnrepo.tar.gz [host-path]
```
