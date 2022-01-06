# Vote App
example microservice vote app 

![img](/ex-vote.svg)

## Initial Project

- Install Python
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
