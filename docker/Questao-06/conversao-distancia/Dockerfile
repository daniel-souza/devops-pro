FROM python:3.7-alpine
WORKDIR /app
COPY . .
RUN pip3 install -r requirements.txt
RUN export FLASK_APP=app.py
EXPOSE 5000
# CMD [ "python3", "app.py", "run", "-h", "0.0.0.0" ]
CMD [ "flask", "run", "--host=0.0.0.0"]