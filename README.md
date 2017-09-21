# uiamjupyter
Custom C/SciPy Jupyter Docker Image

[![](https://images.microbadger.com/badges/image/kvasnica/uiamjupyter.svg)](https://microbadger.com/images/kvasnica/uiamjupyter "Get your own image badge on microbadger.com")

## Building
```
docker build -t kvasnica/uiamjupyter .
docker push kvasnica/uiamjupyter
```

## Run via Docker
```
docker run -d \
           --restart unless-stopped \
           --name jupyter \
           -u $( id -u $USER ):$( id -g $USER ) \
           -p 127.0.0.1:8888:8888 \
           -v /etc/group:/etc/group:ro \
           -v /etc/passwd:/etc/passwd:ro \
           -v /home/jupyter/notebooks:/home/jovyan \
           kvasnica/uiamjupyter
```

## References and Credits

* [Jupyter C kernel](https://github.com/brendan-rius/jupyter-c-kernel)
* [SciPy Notebook](https://github.com/jupyter/docker-stacks/tree/master/scipy-notebook)
