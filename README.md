# docker-phoenix

This repository contains a script for create [phoenix](http://www.phoenixframework.org/) server image.
DockerHub repository is [here](https://hub.docker.com/r/shufo/phoenix/)

You can use these tags as a version of elixir.

- `1.4.2`, `latest`
- `1.4.2-development`
- `1.4.1`
- `1.4.1-development`
- `1.4.0`
- `1.4.0-development`
- `1.4.0-rc.1`
- `1.4.0-rc.1-development`
- `1.4.0-rc.0`
- `1.3.4`
- `1.3.4-development`
- `1.3.3`
- `1.3.2`
- `1.3.1`
- `1.3.0`
- `1.2.6`
- `1.2.5`
- `1.2.3`


## Usage

Run below command in your phoenix project directory.

```
docker run -d -p 4000:4000 -v $(pwd):/app -w /app shufo/phoenix
```

### docker-compose


```
app:
  image: shufo/phoenix:1.4.1-development
  container_name: myproject_app
  hostname: app
  expose:
    - 4000
  ports:
    - "4000:4000"
    - "4001:4001"
  working_dir: /code
  volumes:
    - ".:/code"
  environment:
    - "PORT=4000"
  links:
    - mysql
```
