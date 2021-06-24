# our base image
FROM python:3.6-slim

RUN pip install --upgrade pip

RUN pip3 install gunicorn

# Copy python files
ADD ./aksharamukha-back/ /usr/backend/
ADD ./aksharamukha-python-package/aksharamukha /usr/backend/aksharamukha/

# install requirements
WORKDIR /usr/backend/
RUN pip3 install -r requirements.txt
RUN pip3 install aksharamukha

# tell the port number the container should expose
EXPOSE 8085

# run the application
WORKDIR /usr/backend/
CMD ["gunicorn", "--bind", "0.0.0.0:8085", "main:app"]

