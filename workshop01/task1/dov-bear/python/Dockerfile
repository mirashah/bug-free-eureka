FROM python:3.11.3

# Create directory /app and cd /app
WORKDIR /app

# Inside /app
# Copy source code
COPY main.py .
COPY requirements.txt .
COPY run.sh .
COPY utils.py .
COPY templates templates
COPY public public

# Install dependencies
RUN pip install -r requirements.txt

# How to run
ENV PORT=3000
ENV INSTANCE_NAME=""
ENV INSTANCE_HASH=""

# Expose ports
EXPOSE ${PORT}

# Define healthcheck
HEALTHCHECK --interval=30s --timeout=3s \
  CMD curl -f http://localhost:${PORT}/ || exit 1

# Run the application
ENTRYPOINT ["/app/run.sh"]