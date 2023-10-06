FROM python
RUN apt-get update && \
    apt-get install -y locales && \
    sed -i -e 's/# pt_BR.UTF-8 UTF-8/pt_BR.UTF-8 UTF-8/' /etc/locale.gen && \
    locale-gen
ENV LANG pt_BR.UTF-8
ENV LC_ALL pt_BR.UTF-8
RUN apt-get install curl
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -y
RUN pip install --upgrade pip
COPY requirements.txt /root/requirements.txt
RUN pip install -r /root/requirements.txt
