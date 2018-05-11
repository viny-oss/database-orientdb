# database-orientdb

Theses images are super-lightweight. Based on lightweight operating system : [Alpine](https://alpinelinux.org/) and based on lightweight java virtual machine: [SFJ by IBM](https://www.ibm.com/support/knowledgecenter/en/SSYKE2_8.0.0/com.ibm.java.lnx.80.doc/user/small_jre.html).

Take up to 2 minutes to pull and build the image.

## Build and run

```shell
cd 2.2/
docker build -t viny/orientdb .
docker run -p 2424:2424 -p 2480:2480 viny/orientdb
```

You can check your OrientDB Studio at `http://localhost:2480/studio/index.html`.

## Supported version
- [2.2](https://github.com/orientechnologies/orientdb/tree/2.2.x)

## Dependencies
- [IBMJava 8-sfj-alpine](https://hub.docker.com/_/ibmjava/)
- [Alpine 3.6](https://hub.docker.com/_/alpine/)
