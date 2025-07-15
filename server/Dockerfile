FROM python:3.12-slim

WORKDIR /app

# Copy the requirements file from the server directory
COPY server/requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt psycopg2-binary

# Copy the server application code
COPY server/ .

EXPOSE 8000

ENV PYTHONUNBUFFERED=1

# Run the application without reload for production
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
