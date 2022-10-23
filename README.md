# url-shortener 

A simple example of a url shortener.  

Example, given a url https://www.google.com/?t=3922&usa=1&private=false 

Create a short url https://[domain]/r/[shortcode]


## View all short codes 
<img src="https://i.imgur.com/nnp6yJT.png" width="1024"/>



## Add new short code 
<img src="https://i.imgur.com/gVAzyol.png" width="1024"/>

## Test a short code 
```
http://[domain]/r/[code]
```
Example: 
```
localhost:8181/r/3928
```




#### Running on Docker

```
docker-compose up -d

```


#### Viewing logs on Docker

```
$ docker ps
CONTAINER ID   IMAGE                             COMMAND                  CREATED         STATUS         PORTS                                       NAMES
dc81eaa56ef0   url-shortener_urlshortner-app     "python server.py"       7 minutes ago   Up 7 minutes   0.0.0.0:8181->8181/tcp, :::8181->8181/tcp   urlshortner-app
a692a2501621   url-shortener_urlshortner-mysql   "docker-entrypoint.s…"   7 minutes ago   Up 7 minutes   3306/tcp                                    urlshortner-mysql
$ docker logs -f dc81eaa56ef0 

```


After executing, you will have 2 running cointainers on your Docker host: `urlshortner-app` and `urlshortner-mysql`. For accessing the web application, open your browser and go to http://your-docker-host-ip-address:8181

To destroy the containers, execute:

```
docker-compose down --rmi all
```
