FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt .

RUN pip3 install -r requirements.txt --no-cache-dir

COPY . .

CMD sh -c "python manage.py migrate && \
           python manage.py collectstatic --no-input && \
           gunicorn api_yamdb.wsgi:application --bind 0:8000"

