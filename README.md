# url-shortener 

A simple example of a url shortener.  

Example, given a url ( EG https://www.google.com/?t=3922&usa=1&private=false )

Create a short url https://[domain]/r/[shortcode]  ( EG http://localhost:8181/r/3928 )


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
^^ Then test with http://localhost:8181/ 

#### Viewing logs on Docker

Use the container id and stream the logs
```
$ docker ps
CONTAINER ID   IMAGE                             COMMAND                  CREATED         STATUS         PORTS                                       NAMES
dc81eaa56ef0   url-shortener_urlshortner-app     "python server.py"       7 minutes ago   Up 7 minutes   

$ docker logs -f dc81eaa56ef0 

```


After executing, you will have 2 running cointainers on your Docker host: `urlshortner-app` and `urlshortner-mysql`. For accessing the web application, open your browser and go to http://localhost:8181

To destroy the containers, execute:

```
docker-compose down --rmi all
```
