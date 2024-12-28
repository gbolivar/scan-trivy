# Scanner Trivy

This project is based on doing in a standard way using docker to use the trivy image vulnerability scanner, which allows checking Docker images and some aspects for images for kubernetes.

# Table contents
1. [Project Information](#information)
2. [Requirement](#requirements)
3. [Commands](#commands)
4. [Autor](#team)
5. [Contact](#contact)
6. [Documentation](#doc)

## Project Information
- **Trivy**: It is based on trivy.

## Requirement
- **Docker**: It is required to have docker installed.
- **Docker Compose**: It is required to have docker compose installed.

# Commands

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
## Autor
Create for [Gregorio José Bolívar Bolívar](https://x.com/gbolivarb)

[![Twitter](https://img.shields.io/twitter/follow/gbolivarb?style=social)](https://x.com/gbolivarb)
[![Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&labelColor=0077B5)](https://www.linkedin.com/in/gregorio-bolivar/)
[![GitHub](https://img.shields.io/github/followers/gbolivar?style=social)](https://github.com/gbolivar)

### Contact
<p>
  Anything you need let me know so I can help you. 💬.
</p>
<p>
    <a href="https://x.com/gbolivarb" target="_blank">
        <img src="https://abs.twimg.com/responsive-web/client-web/icon-ios.77d25eba.png" 
    height="30">
    </a> &nbsp;&nbsp;
    <a href="https://github.com/gbolivar" target="_blank">
        <img src="https://cdn.iconscout.com/icon/free/png-256/github-153-675523.png" 
    height="30">
    </a> &nbsp;&nbsp;
    <a href="https://www.linkedin.com/in/gregorio-bolivar/" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/768px-LinkedIn_logo_initials.png" 
    height="30">
    </a>  &nbsp;&nbsp;
    <a href="https://ironsofts.com" target="_blank">
        <img src="https://ironsofts.com/assets/images/app/logo.png" 
    height="30">
    </a>
</p>

## Documentation
- [Trivy doc - Severity Selection](https://trivy.dev/latest/docs/scanner/vulnerability/#severity-selection)
- [Trivy doc - Getting Started](https://trivy.dev/latest/getting-started/)


## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html)




