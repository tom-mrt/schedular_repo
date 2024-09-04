FROM python:3.11-slim

WORKDIR /app

COPY ./backend/pyproject.toml ./backend/poetry.lock* /app/

RUN pip install --upgrade pip && \
    pip install poetry && \
    poetry config virtualenvs.create false && \
    poetry install --no-interaction --no-ansi

COPY ./backend /app

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]