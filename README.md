# Scanner Trivy

This project is based on doing in a standard way using docker to use the trivy image vulnerability scanner, which allows checking Docker images and some aspects for images for kubernetes.
## Project Information
- **Trivy**: It is based on trivy.

# Container to run commands

## Clone repository
```shell
git clone git@github.com:gbolivar/scan-trivy.git
```

## Access the project
```shell
cd scan-trivy
```

### Commands executed locally

Once the repository is cloned, the first thing is to generate the docker images:

```shell
docker-compose up -d --build
```
### To run the command in the container:

Scan an image in python with alpine
```shell
docker-compose exec scan-trivy trivy image python:3.4-alpine
```

You can scan the packets of an image:

```shell
docker-compose exec scan-trivy trivy image --pkg-types os ruby:2.4.0
```

Can scan packets for the most critical vulnerabilities with the highest priority:

```shell
docker-compose exec scan-trivy trivy image --severity HIGH python:3.4-alpine
```

Then go into the backend container:

```shell
docker exec -it scan-trivy /bin/bash
```

To exit the container, use the exit command:

```shell
exit
```

Then you may want to delete the entire project container and leave it clean.:

```shell
docker-compose down
```
## Documentation
- [Trivy doc - Severity Selection](https://trivy.dev/latest/docs/scanner/vulnerability/#severity-selection)
- [Trivy doc - Getting Started](https://trivy.dev/latest/getting-started/)


## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html)




