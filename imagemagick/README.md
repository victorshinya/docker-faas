# Create an ImageMagick functions using OpenFaaS with Docker and Docker Swam

## How-to

Build ImageMagick function. The `-yaml` flag is used to reference your build on a yml file.

```sh
faas-cli build -yaml image.yml
```

Deploy ImageMagick function into [OpenFaaS UI](http://127.0.0.1:8080).

```sh
faas-cli deploy -yaml image.yml
```

Send the `whale.jpg` image as a parameter to **resizer** function (our ImageMagick function) and execute.

```sh
cat whale.jpg | faas-cli invoke resizer > whale-smaller.jpg
```

Check out `whale-smaller.jpg` image. You can change the resize reference.
