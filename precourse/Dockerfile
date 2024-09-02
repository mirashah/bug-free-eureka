FROM python:3.11.3

# Create directory /app and cd /app
WORKDIR /app

# Inside /app
# Copy source code
COPY app.py .
COPY requirements.txt .
COPY templates templates

# Install dependencies
RUN pip install -r requirements.txt

# How to run
ENV FLASK_DEBUG=1

# Expose ports
EXPOSE 5000

# Run the application
# ENTRYPOINT python app.py
CMD ["flask", "run", "--host=0.0.0.0"]