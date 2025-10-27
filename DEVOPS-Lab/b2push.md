Python (app.py)
Dockerfile
Dockerfile

# Use an official Python runtime as a parent image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app
# Copy the local directory contents into the container at /app
COPY . .

# Install any needed packages specified in requirements.txt
# (Uncomment the line below if you have a requirements.txt)
# RUN pip install --no-cache-dir -r requirements.txt

# Run app.py when the container launches
CMD ["python", "./app.py"]
Terminal Commands
Bash

# Build the image
docker build -t my-python-image .

# Run the image
docker run my-python-image
2. Java (sample.java)
Dockerfile
Dockerfile

# Use an official OpenJDK runtime
FROM openjdk:21-jdk

# Set the working directory
WORKDIR /app

# Copy the Java source file
COPY sample.java .

# Compile the Java file
RUN javac sample.java

# Set the default command to run the compiled class
CMD ["java", "sample"]
Terminal Commands
Bash

# Build the image
docker build -t my-java-image .

# Run the image
docker run my-java-image
3. HTML (index.html)
Dockerfile
Dockerfile

# Use an official Nginx image to serve static content
FROM nginx:alpine

# Copy your static files (HTML, CSS, JS) to the default Nginx web root
COPY . /usr/share/nginx/html
Terminal Commands
Bash

# Build the image
docker build -t my-html-image .

# Run the image, mapping your port 8080 to the container's port 80
docker run -d -p 8080:80 my-html-image
(Now open http://localhost:8080 in your browser)
