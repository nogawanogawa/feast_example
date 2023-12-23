FROM  gcr.io/google.com/cloudsdktool/google-cloud-cli:latest
#feast use pyarraw, but it is not support python > 3.11.x

WORKDIR /usr/src/app

RUN apt update
RUN apt install -y cmake python3.9
ENV POETRY_HOME="/opt/poetry"
ENV PATH="$POETRY_HOME/bin::$PATH"
RUN ln -s /usr/bin/python3.9 /usr/bin/python

COPY poetry.lock pyproject.toml ./
RUN curl -sSL https://install.python-poetry.org | python3 - --version 1.4.1 && \
    poetry config virtualenvs.create false && \
    poetry install
