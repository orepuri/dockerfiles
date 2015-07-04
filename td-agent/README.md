### Dockerfile for td-agent

#### Build 

```
docker build -t <tag> .
```

#### Run

```
docker run -d -p 24224:24224 -p 8888:8888 -v `pwd`/log:/var/log/td-agent/ <tag>:latest
```
