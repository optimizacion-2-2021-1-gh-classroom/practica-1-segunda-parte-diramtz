#dummy line
FROM ubuntu:bionic

ENV JUPYTERLAB_VERSION 3.0.0
ENV LANG C.UTF-8
ENV LC_ALL C.UTF-8
ENV DEB_PACKAGES="sudo nano less git python3-dev python3-pip python3-setuptools nodejs"
#Kale 
#ENV PIP_PACKAGES_KALE="kubeflow-kale==0.6.1"

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive && echo "America/Mexico_City" > /etc/timezone && apt-get install -y tzdata

RUN apt-get update && apt-get install -y $DEB_PACKAGES && pip3 install --upgrade pip

RUN groupadd miuser
RUN useradd miuser -g miuser -m -s /bin/bash
RUN echo 'miuser ALL=(ALL:ALL) NOPASSWD:ALL' | (EDITOR='tee -a' visudo)
RUN echo 'miuser:qwerty' | chpasswd
RUN pip3 install jupyter jupyterlab==$JUPYTERLAB_VERSION --upgrade

#Kale
#RUN pip install $PIP_PACKAGES_KALE --upgrade
#RUN jupyter labextension install kubeflow-kale-labextension

COPY requirements.txt .
RUN pip3 install --requirement requirements.txt
COPY . .
COPY reporte_equipo_2_parte_2_practica_1.ipynb .

USER miuser
RUN jupyter notebook --generate-config && sed -i "s/#c.NotebookApp.password = .*/c.NotebookApp.password = u'sha1:115e429a919f:21911277af52f3e7a8b59380804140d9ef3e2380'/" /home/miuser/.jupyter/jupyter_notebook_config.py
ENTRYPOINT ["/usr/local/bin/jupyter", "lab", "--port=8888", "--no-browser", "--ip=0.0.0.0", "--allow-root"]
