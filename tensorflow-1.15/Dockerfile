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

# ユーザーを作成
ARG USER=docker
ARG UID=1000
RUN useradd -m -u ${UID} ${USER}
#RUN gpasswd -a ${USER} sudo
RUN echo "${USER}:${USER}" | chpasswd

#RUN rm -f ~/.cache/matplotlib/fontList.json
ADD --chown=docker:docker jupyter_notebook_config.py /home/${USER}/.jupyter/
#chownで USERを参照してくれない
#ADD --chown=${USER}:${USER} jupyter_notebook_config.py /home/${USER}/.jupyter/

# 作成したユーザーに切り替える
USER ${UID}

CMD ["jupyter", "notebook"]

