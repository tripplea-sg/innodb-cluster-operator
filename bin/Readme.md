# How to Install from Binary
If pulling image from docker hub is not an option, then perform the following steps:
1. Download triplea-operator.tar.gz and Dockerfile
2. Extract triplea-operator.tar.gz
```
tar -zxvf triplea-operator.tar.gz
```
3. Build image:
```
docker build -m 2g -c 4 -t triplea-operator:1.0 .
```
