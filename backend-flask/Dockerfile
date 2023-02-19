FROM python:3.10-slim-buster

# Inside Container
# Make a new folder inside container
WORKDIR /backend-flask

# Outside Container -> Insider Container
# this contains the libraries want to install to run the app
COPY requirements.txt requirements.txt

# Inside Container
# install the python libraries used for the app
RUN pip3 install -r requirements.txt

#Outside Container -> Inside Container
# . means everything in the current directory
# first . means /backend-flask (outside container)
# second . means /backend-flask (inside container)
COPY . .

# set environment variables
# inside container and will remain set when the container is running
ENV FLASK_ENV=development

#
EXPOSE ${PORT}

# command used to run flask
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]