FROM nvcr.io/nvidia/l4t-tensorflow:r32.4.4-tf1.15-py3

RUN apt-get update
RUN apt-get install -y fonts-ipaexfont
RUN apt-get install -y libffi-dev
RUN apt-get install -y python-pip
RUN apt-get install -y python3-pip
RUN pip3 install -U pip
RUN pip3 install notebook
RUN pip3 install matplotlib
RUN pip3 install pandas
RUN pip3 install scipy
RUN pip3 install opencv-contrib-python

RUN mkdir /tf
RUN chmod 777 /tf

ADD jupyter_notebook_config.py /root/.jupyter/

CMD ["jupyter", "notebook", "--allow-root"]

