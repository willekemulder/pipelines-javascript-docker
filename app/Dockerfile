# Use an official Python runtime as a parent image
FROM python:3.11-slim

# Set the working directory to /app
WORKDIR /app

# # add an URL that PIP automatically searches (e.g., Azure Artifact Store URL)
# ARG INDEX_URL
# ENV PIP_EXTRA_INDEX_URL=$INDEX_URL

# Copy requirements.txt and install Python dependencies
COPY requirements.txt .
RUN pip install -r requirements.txt

# Install system dependencies (e.g., ffmpeg)
RUN apt-get update && apt-get install -y ffmpeg

RUN python -m pip install --upgrade pip
RUN pip install keyring artifacts-keyring
RUN pip install takkie==0.1.377553

# Copy the current directory contents into the container at /app
COPY . /app
