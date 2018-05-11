# Viny OrientDB docker file

Theses images are super-lightweight. Based on lightweight operating system : [Alpine](https://alpinelinux.org/) and based on lightweight java virtual machine: [SFJ by IBM](https://www.ibm.com/support/knowledgecenter/en/SSYKE2_8.0.0/com.ibm.java.lnx.80.doc/user/small_jre.html).

Take up to 2 minutes to pull, build and run the image.

## How to use

### Build and run

```shell
cd 2.2/
docker build -t viny/orientdb .
docker run -p 2424:2424 -p 2480:2480 -e ORIENTDB_ROOT_PASSWORD=rootpwd viny/orientdb
```

### OrientDB Studio

The Studio plugin is automaticaly installed on this image.

You can check your [OrientDB Studio](https://orientdb.com/docs/last/Studio-Home-page.html) at `http://localhost:2480/studio/index.html`.

### Persistent volume

You can add persistents volumes to easily upgrade your image.

```shell
docker run -d --name orientdb -p 2424:2424 -p 2480:2480 \
    -v <config_path>:/orientdb/config \
    -v <databases_path>:/orientdb/databases \
    -v <backup_path>:/orientdb/backup \
    -e ORIENTDB_ROOT_PASSWORD=rootpwd \
    viny/orientdb
```

## Supported version
- [2.2](https://github.com/orientechnologies/orientdb/tree/2.2.x), 162MB

## More informations

### Docker Dependencies
- [IBMJava 8-sfj-alpine](https://hub.docker.com/_/ibmjava/)
- [Alpine 3.6](https://hub.docker.com/_/alpine/)

### Licences

This docker image is directly inspired of the official docker image, check it out [here](https://github.com/orientechnologies/orientdb-docker), you can find additional informations in their repository.

- [OrientDB](https://orientdb.com), [licence file](https://github.com/orientechnologies/orientdb/blob/develop/license.txt).
- [IBMJAVA](https://github.com/ibmruntimes/ci.docker), [licence file](https://github.com/ibmruntimes/ci.docker/blob/master/LICENSE).

Dockerfiles and associated scripts found in this project are licensed under the [MIT licence](https://github.com/viny-oss/orientdb-docker/blob/master/LICENSE).
