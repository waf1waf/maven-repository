# maven-repository

A maven repository is simply a web server with a repository directory.  Inside of that repository directory are all of the maven artifacts.

This project simply uses the official apache httpd server and maps the local public-html directory into the container.

I have chosen `/opt/m2` as the location for my repository.

## Building

```
docker build -t maven-repository .
```

## Running

```
docker run -d -p 80:80 -v /opt/m2:/usr/local/apache2/htdocs --name maven-repository maven-repository
```

or

```
docker-compose up -d
```

## Stopping

```
docker-compose down
```

## Updating the repository

To update the repository, simply copy files into the /opt/m2/repository directory using the file manager of your choice.
