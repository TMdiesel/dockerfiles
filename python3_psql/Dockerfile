
FROM python:3.8
USER root

RUN apt-get update
RUN apt-get -y install locales && \
    localedef -f UTF-8 -i ja_JP ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8
ENV TZ JST-9
ENV TERM xterm

RUN apt-get install -y \
    vim \
    less \
    sudo \
    wget \
    tmux 
RUN pip install --upgrade pip
RUN pip install --upgrade setuptools

RUN set -x \
    && pip install jupyter \
    poetry \
    ipython \
    jupyterlab \
    numpy \
    pandas \
    matplotlib \
    scikit-learn \
    seaborn \
    psycopg2

RUN set -x \
  && poetry config --list \
  && poetry config virtualenvs.in-project true

RUN set -x \
  && : "install node.js" \
  && curl --silent --location https://deb.nodesource.com/setup_14.x | bash - \
  && apt-get install --yes nodejs \
  && apt-get install --yes build-essential

WORKDIR /python_postgres

CMD ["/bin/bash"]
