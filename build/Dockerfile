# Latest base CPU image from Google Cloud's Deep Learning Container Images
FROM gcr.io/deeplearning-platform-release/base-cpu:latest
# Copying requirements.txt to app folder
COPY requirements.txt /app/requirements.txt
# Changing working directory to /app
WORKDIR /app
# Pip installing requirements.txt into the base conda environment
RUN /opt/conda/bin/pip install -r requirements.txt