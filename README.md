# Beginner examples

This repository contains few examples for docker and k8s. I use these for intruducing basic docker/k8s principles at customer workshops.

## List of examples and what they show

### 01simpleapp

A simple app in node.js that will accept http requests and return the hostname that it is running on.
First build the container image

```bash
sudo docker build -t simpleapp .
```

Now you can run it with:

```bash
sudo docker run --name simpleapp-container -p 8080:8080 -d simpleapp
```

You can now use your browser on the same host to go to http://127.0.0.1:8080 or use the CLI and ```curl localhost:8080```
Eitherway you will see the app will return something like ```You've hit 632dd7362aaf```. This does not return you local hostname but the container name. This proves that the app is running inside the container completly isolate from everything else.