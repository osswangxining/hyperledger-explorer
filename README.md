# hyperledger-explorer-docker-image
This is one docker image of hyperledger explorer.

## Building your image
Go to the directory that has your Dockerfile and run the following command to build the Docker image. The -t flag lets you tag your image so it's easier to find later using the docker images command:
```sh
docker build -t osswangxining/hyperledger-explorer .
```

## Run the image
Running your image with -d runs the container in detached mode, leaving the container running in the background. The -p flag redirects a public port to a private port inside the container. 

Run the image you previously built:
```
docker run -v /Users/xiningwang/blockchain/blockchain-explorer/config.json:/blockchain-explorer/config.json -v /Users/xiningwang/Downloads/fabric-samples-1.1.0/first-network/crypto-config:/first-network/crypto-config -p 8080:8080 -d osswangxining/hyperledger-explorer
```
docker run -v /Users/xiningwang/blockchain/blockchain-explorer/config.json:/blockchain-explorer/config.json -v /Users/xiningwang/Downloads/fabric-samples-1.1.0/first-network/crypto-config:/first-network/crypto-config  -p 8080:8080   -it osswangxining/hyperledger-explorer bash

## Push Docker images to your namespace
Upload (push) the image to your namespace. Replace <my_namespace> with your namespace, and <image_repo> and <tag> with the repository and the tag of the image that you chose when you tagged the image.

```docker
docker push <my_namespace>/<image_repo>:<tag>
```

For example:
```sh
docker push osswangxining/hyperledger-explorer:latest
```