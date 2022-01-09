### What is this?

The goal of this is to have an image that can run as a jenkins worker where
- jenkins is running in kubernetes
- kubernetes is k3s on raspberry pi 4
- architecture is arm64
- it can run node, npm and yarn

### build:

```
#once
buildx create --name mybuilder --use
docker buildx build --platform linux/arm64 . -t agentbellnorm/jnlp-node-arm64 --push
```

### How to use
See this article for details on how to set up the image as the default `jnlp` container:
https://bryanbende.com/development/2021/07/02/k3s-raspberry-pi-jenkins-registry-p1

### Why
I never succeeded to use separate containers for build steps, one recommendation was to run steps in the jnlp container.