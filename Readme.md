# Vote App
example microservice vote app 

![img](/ex-vote.svg)

## Prerequisites
- [Python v.3.x](https://www.python.org/) has installed
- Redis running default port : 6379
  
  command to install using docker
  ```bash
  docker run -it --rm --name redis -p 6379:6379 redis:alpine
  ```

## Initial Project

- Init files
  - app.py
  - static
  - template
- Install Python Package
  - Flask

  ```bash
  pip install Flask
  ```
  - Redis
  ```bash
  pip install redis
  ```
  - gunicorn ; not support on windows os
  ```bash
  pip install gunicorn
  ```

  - Coverage Unittest
  ```bash
  pip install coverage
  ```

## Run Project in Local development

  ```bash
  python app.py
  ```

Run with gunicorn server (don't support Windows)

```bash
gunicorn app:app -b 0.0.0.0:80 --log-file - --access-logfile - --workers 4 --keep-alive 0
```

## Unittest

python unittest
```bash
python -m unittest discover
```

Run with coverage discover
```bash
coverage run -m unittest discover
```

Print Report Coverage
```
coverage report
```

Export HTML Report
```bash
coverage html
```


## Configurations

|Env Variables|Default|Example|
|---|---|---|
|REDIS_CONNECTION|redis|127.0.0.1|
|OPTION_A|cat|teamA|
|OPTION_B|dog|teamB|




## Docker

Build Image

```
docker build -t vote:0.0.1 .
```
Run Container Image

```
docker run -it --rm --name vote -p 80:80 -e REDIS_CONNECTION=192.168.1.102 vote:0.0.1
```