FROM python:3.11-slim

WORKDIR /app

COPY ./frontend/pyproject.toml ./frontend/poetry.lock* /app/

RUN pip install --upgrade pip && \
    pip install poetry && \
    poetry config virtualenvs.create false && \
    poetry install --no-interaction --no-ansi

COPY ./frontend /app

CMD ["streamlit", "run", "app/main.py"]