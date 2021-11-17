# Docker

```
docker --version
```


## Running

When we encounter command
```
aws COMMAND
```
Use this instead.
```
docker run --rm -it amazon/aws-cli:latest COMMAND
```

-rm : clean up container after exit
-it open a pseudo-TTY with stdin (to provide input to subsequent prompts). Omit if running scripts.
latest: version, could substitute with version in x.x.x


## Update

```
docker pull amazon/aws-cli:latest
```


## mount credentials

mount host %userprofile%\.aws in docker /root/.aws
```
docker run --rm -it -v %userprofile%\.aws:/root/.aws amazon/aws-cli command
```

## environment variable

```
docker run --rm -it -v %userprofile%\.aws:/root/.aws -e ENVVAR_NAME amazon/aws-cli s3 ls
```


## shorten command
```
doskey aws-learning=docker run --rm -it -v %userprofile%\.aws:/root/.aws amazon/aws-cli $*
aws-learning COMMAND
```

