# image to create container from
FROM python:3.10-slim

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1


# Set the working directory in the container
WORKDIR /DRF

COPY DRF/  ./DRF
COPY manage.py .
COPY pyproject.toml .
COPY poetry.lock .

# Install poetry
RUN pip install poetry

# Turn of virtualenvs
RUN poetry config virtualenvs.create false

# Install dependencies
RUN poetry install --no-root

# Copy the rest of the project
COPY . .