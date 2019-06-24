FROM python:3.7.3
ENV PYTHONUNBUFFERED 1

COPY requirements.txt /code/
WORKDIR /code/
RUN pip install -r requirements.txt

COPY . /code/

RUN ["chmod", "+x", "./docker/app/startup.sh"]
CMD [ "./docker/app/startup.sh" ]