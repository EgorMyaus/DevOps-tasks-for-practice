FROM python:3.9-slim

WORKDIR /app

# Pre-install dependencies first to leverage Docker layer caching
COPY requirements.txt .

RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# Copy the rest of the code
COPY . .

# Set port (just a hint, not mandatory for functionality)
EXPOSE 5000

# Run app using uvicorn
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "5000"]
