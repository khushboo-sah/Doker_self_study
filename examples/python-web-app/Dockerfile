FROM ubuntu

WORKDIR /app

# Copy project files
COPY requirements.txt /app/
COPY devops /app/

# Install system dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-venv python3-pip && \
    python3 -m venv /app/venv && \
    /app/venv/bin/pip install --no-cache-dir -r /app/requirements.txt

# Activate virtual environment
ENV PATH="/app/venv/bin:$PATH"

# Set the entry point
ENTRYPOINT ["python3"]
CMD ["/app/manage.py", "runserver", "0.0.0.0:8000"]






