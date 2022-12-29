This repo is for testing private Nexus registry locally.

The official [sonartype/nexus3](https://hub.docker.com/r/sonatype/nexus3/) image doesn't support the M1 chip. Therefore, we use the [klo2k/nexus3](https://hub.docker.com/r/klo2k/nexus3) image.

[Documentation](https://docs.snyk.io/integrations/private-registry-integrations/nexus-repo-manager-setup) for running Snyk Nexus broker.

### How to run
```text
docker-compose -f docker-compose.local.yaml up --build
```

Then follow [this tutorial](https://developer.entando.com/v6.1/tutorials/ecr/how-to-create-local-npm-registry.html#create-the-role) to create a local npm registry.
