Hello from nginx!👋
========================

The "Hello from nginx!👋" application is just a starter to show a minimalist nginx app.

Requirements
------------

* [Docker Desktop][1]
* [Kubernetes][2]

Installation
------------

Clone this repository:

```console
https://github.com/abdounikarim/poc-nginx
```

Go on the project root folder:

```console
cd poc-nginx
```

Usage
-----

Start the Docker container:

```console
docker compose up -d
```

Then, open your browser and go to [http://localhost](http://localhost).
_If you want to use another port, you can change it in the `[compose.yaml](./compose.yaml)` file._

Deploy with Kubernetes locally
-----

Here, i'm using the Kubernetes context of Docker Desktop.
Make sure you have Kubernetes enabled in Docker Desktop and you have selected docker-desktop in Kubernetes context.
Deploy the application:

```console
kubectl apply -f nginx.yaml
```

Then, open your browser and go to [http://localhost:30100/](http://localhost:30100/).
_If you want to use another port, you can change the **NodePort** key with the value you want in the `[nginx.yaml](./nginx.yaml)` file._

⚠️ **Be careful, you can't use the port you want, you need to use one between 30000 and 32767 like described [here](https://kubernetes.io/docs/reference/networking/ports-and-protocols/) for NodePort.** ⚠️

Destroy the application:

```console
kubectl delete -f nginx.yaml
```

[1]: https://www.docker.com/products/docker-desktop/
[2]: https://kubernetes.io/releases/download/
