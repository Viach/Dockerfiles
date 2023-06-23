#README


docker build --file jupyterlab/Dockerfile --tag jupyter-lab .

docker volume create data

docker container run -it --detach --volume data --hostname localhost --publish 8888:8888 --name jupyter-lab jupyter-lab 
