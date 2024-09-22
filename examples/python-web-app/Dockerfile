FROM ubuntu

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

# Install Python, pip, and virtualenv; then use virtualenv for package installation
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv /app/venv && \
    /app/venv/bin/pip install -r requirements.txt

# Ensure the virtual environment is used
ENV PATH="/app/venv/bin:$PATH"

ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
