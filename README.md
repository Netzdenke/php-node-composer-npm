# php-node-composer-npm

## Build Command
```
cd php7.4
docker build -t netzdenke/php-node-composer-npm .
docker tag XXXXXXXXXXX netzdenke/php-node-composer-npm:php7.4
docker push netzdenke/php-node-composer-npm
```

## Run Commands
```
docker run -v ${PWD}:/application --workdir="/application" -it netzdenke/php-node-composer-npm:php7.4 bash
```