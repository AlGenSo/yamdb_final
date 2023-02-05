FROM python:3.7-slim

RUN mkdir /app
WORKDIR /app
COPY api_yamdb/ /app
RUN pip3 install --upgrade pip
RUN pip3 install -r requirements.txt --no-cache-dir

CMD ["gunicorn", "--capture-output", "api_yamdb.wsgi:application", "--bind", "0:8000" ]