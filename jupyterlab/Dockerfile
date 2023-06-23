#
ARG PYTHON_VERSION=3.11
ARG BASE_IMAGE=python
FROM $BASE_IMAGE:$PYTHON_VERSION

RUN apt update -y && apt upgrade -y  && apt install unzip nano git htop wget apt-utils -y

RUN pip install --upgrade pip && \
    pip install --upgrade \
      jupyterlab pandas fastapi numpy scikit-learn pandas-profiling seaborn sklearn folium 
      
### RUN jupyter notebook --generate-config && echo "c.NotebookApp.quit_button = False" >> /root/.jupyter/jupyter_notebook_config.py

RUN mkdir data

WORKDIR /data

CMD ["jupyter", "lab", "--allow-root", "--notebook-dir=/data/", "--ip=0.0.0.0", "--port=8888"]