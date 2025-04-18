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
https://github.com/ProofOfConceptFactory/poc-nginx
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

Then, open your browser and go to [http://localhost][3].
_If you want to use another port, you can change it in the [compose.yaml][4] file._

Deploy with Kubernetes locally
-----

Here, i'm using the Kubernetes context of Docker Desktop.
Make sure you have Kubernetes enabled in Docker Desktop and you have selected docker-desktop in Kubernetes context.
Deploy the application:

```console
kubectl apply -f nginx.yaml
```

Then, open your browser and go to [http://localhost:30100][5].
_If you want to use another port, you can change the **NodePort** key with the value you want in the [nginx.yaml][6] file._

⚠️ **Be careful, you can't use the port you want, you need to use one between 30000 and 32767 like described [here][7] for NodePort.** ⚠️

Destroy the application:

```console
kubectl delete -f nginx.yaml
```

Helm
-----

Install project with [Helm][8]:

```console
helm install hello-from-nginx helm-nginx
```

_The `hello-from-nginx` name is not important. It's the project name, you can change it to whatever you want._

Upgrade project:

```console
helm upgrade hello-from-nginx helm-nginx
```

Delete project with helm:

```console
helm uninstall hello-from-nginx
```

[1]: https://www.docker.com/products/docker-desktop/
[2]: https://kubernetes.io/releases/download/
[3]: http://localhost
[4]: ./compose.yaml
[5]: http://localhost:30100
[6]: ./nginx.yaml
[7]: https://kubernetes.io/docs/reference/networking/ports-and-protocols
[8]: https://helm.sh/
