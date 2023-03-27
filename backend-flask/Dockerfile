FROM python:3.10-slim-buster

# Inside Container
WORKDIR /backend-flask

# Outside Container ==> Inside Container (libraries)
COPY requirements.txt requirements.txt

# Install the python libraries used for the app and update them
RUN pip3 install -r requirements.txt
RUN apt update && apt install -y curl

# Outside Container ==> Inside Container
COPY . .

# Enviroment Variables 
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
