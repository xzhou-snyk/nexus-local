This repo is for testing private Nexus registry locally.

The official [sonartype/nexus3](https://hub.docker.com/r/sonatype/nexus3/) image doesn't support the M1 chip. Therefore, we use the [klo2k/nexus3](https://hub.docker.com/r/klo2k/nexus3) image.

The official [sonartype/nexus](https://hub.docker.com/r/sonatype/nexus) image somehow works with ARM, but a bit wobbly. Sometimes it gets stuck and we might have to restart the container.

[Documentation](https://docs.snyk.io/integrations/private-registry-integrations/nexus-repo-manager-setup) for running Snyk Nexus broker.

### How to run
```text
docker-compose -f docker-compose-nexusX.yaml up --build
```

Then follow [this tutorial](https://developer.entando.com/v6.1/tutorials/ecr/how-to-create-local-npm-registry.html#create-the-role) to create a local npm registry.

### Add packages
Follow [this guide](https://area51.dev/linux/nexus/repos/npm/) to set up NPM registry mirror.

To publish packages into the local private Nexus registry, I had auth issue with Nexus 2, and to solve it in my local lodash package directory I need to manually create a `.npmrc` file:
```text
registry=http://localhost:8081/nexus/content/repositories/test-npm-repo/
_auth=username:password (base64 encoded)
```
