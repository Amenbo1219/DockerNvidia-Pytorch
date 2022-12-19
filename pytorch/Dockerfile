FROM nvidia/cuda:11.8.0-base-ubuntu22.04

RUN apt-get update && apt-get install -y \
    python3-pip \ 
    sudo \
    wget \
    git \
    vim
RUN apt-get install -y libgl1-mesa-dev
COPY requirements.txt /install/requirements.txt

RUN ln -s /usr/bin/python3.10 /usr/bin/python
RUN pip install --upgrade pip
RUN pip install -r /install/requirements.txt

WORKDIR /work
#CMD ["/bin/bash"]
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--allow-root", "--LabApp.token=''"]