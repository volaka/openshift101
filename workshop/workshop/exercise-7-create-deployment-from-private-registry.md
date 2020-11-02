# Exercise 7: Create Deployment from Private Registry

If you don't have python install locally, don't worry! Because you don't need it. One of the advantages of using Docker containers is that you can build python into your containers, without having python installed on your host.

## Prerequisite

1. Go to [https://www.katacoda.com/courses/docker/playground](https://www.katacoda.com/courses/docker/playground)
2. Sign in with one of the choices.
3. Click to **Start Scenario**

## Create a Dockerfile

Create a `Dockerfile` but running the following command. \(copy-paste the entire code block\)

```bash
mkdir ~/app && cd ~/app
echo 'from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "hello world!"

if __name__ == "__main__":
    app.run(host="0.0.0.0")' > app.py
```

```bash
echo 'FROM python:3-alpine
RUN pip install flask
CMD ["python","app.py"]
COPY app.py /app.py
USER 1001' > Dockerfile
```

## Build the docker image

Pass in `-t` to name your image `python-hello-world`.

```bash
docker image build -t python-hello-world .
```

Verify that your image shows up in your image list via `docker image ls`.

```bash
docker image ls
```

```bash
> REPOSITORY           TAG                 IMAGE ID            CREATED             SIZE
> python-hello-world   latest              f1b2781b3111        26 seconds ago      99.3MB
> python               3.6.1-alpine        c86415c03c37        8 days ago          88.7MB
```

Notice that your base image, python:3.6.1-alpine, is also in your list.

