FROM python:3.7-slim

WORKDIR /app
COPY api_yamdb/ .
RUN pip3 install --upgrade pip
RUN pip3 install -r requirements.txt --no-cache-dir

CMD ["gunicorn", "--capture-output", "api_yamdb.wsgi:application", "--bind", "0:8000" ]