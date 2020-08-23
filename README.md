# radon-dockerfile
radon + mysql = radondb. this is radon node.

## VOLUME

mount volume on /data

## ENV

### BACKEND_NAME_HOST_PORT_USER_PASSWORD_MAXCONNECTIONS

sample:

```
    one backend:

    BACKEND_NAME_HOST_PORT_USER_PASSWORD_MAXCONNECTIONS="name,host,3306,user,password,1000"

    two backend:

    BACKEND_NAME_HOST_PORT_USER_PASSWORD_MAXCONNECTIONS="name,host,3306,user,password,1000:name2,host2,3306,user,password,1000"
```
### BACKEND_REPLICA

sample:

```
    default is 0. 
    if BACKEND_REPLICA is 2, it will add two backend.  first backend name="name-0" host="podname-0.svcname", second backend name="name-1" host="podname-1.svcname", this is used in k8s.
```

## PARAMETERS

change any parameters use the api(https://github.com/radondb/radon/blob/master/docs/api.md#meta)

## build image
```
cd radonbuild
docker build -f radonbuild -t radon:v1.0 .
```
