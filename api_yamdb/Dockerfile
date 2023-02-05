FROM python:3.7-slim

RUN mkdir /app
WORKDIR /app
COPY api_yamdb/ .
RUN pip install --upgrade pip
RUN pip install -r requirements.txt --no-cache-dir

CMD ["gunicorn", "--capture-output", "api_yamdb.wsgi:application", "--bind", "0:8000" ]