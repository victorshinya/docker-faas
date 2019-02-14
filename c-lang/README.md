# IBM Cloud Functions Docker

## Pre-requisites

- Download and install [IBM Cloud CLI](https://cloud.ibm.com/docs/cli/reference/ibmcloud/download_cli.html) and create an account.
- Download and install [IBM Cloud Functions CLI](https://cloud.ibm.com/openwhisk/learn/cli).
- Download and install [Docker](https://docker.com) and create an account.

## Important notes

- The executable file must be located in `/action` folder.
- The name of the executable must be `/action/exec`and be any file with executable permissions.
- The `openwhisk/dockerskeleton` base image is useful for actions that run scripts (e.g., bash, perl, python) and compiled binaries or, more generally, any native executable.

## How-to

Check if you are using the latest version of IBM Cloud Functions CLI and update to.

```sh
ibmcloud plugin update cloud-functions
```

1. Log in to your Docker account.

```sh
docker login -u <username> -p <password>
```

2. Build your Docker container.

```sh
docker build -t <your-docker-image> .
```

3. Push to Docker Hub.

```sh
docker push <username>/<your-docker-image>
```

4. Create an Action on IBM Cloud Functions from your Docker image on Docker Hub.

```sh
ibmcloud fn action create <action-name> --docker <username>/<your-docker-image>
```

5. Now you can test your Action running the command-line below.

```sh
ibmcloud fn action invoke --result <action-name>
```

6. If you update the code, you need to deploy the new version on IBM Cloud Functions. Follow the command-line below.

```sh
ibmcloud fn action update <action-name> --docker <username>/<your-docker-image>
```
