FROM  python:3.10.10-bullseye
#feast use pyarraw, but it is not support python > 3.11.x

WORKDIR /usr/src/app

RUN apt update
RUN apt install -y cmake
ENV POETRY_HOME="/opt/poetry"
ENV PATH="$POETRY_HOME/bin::$PATH"

COPY poetry.lock pyproject.toml ./
RUN curl -sSL https://install.python-poetry.org | python3 -
RUN poetry config virtualenvs.create false
RUN poetry install
