FROM python:3.11.6-slim

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

COPY mock/req.txt /
RUN pip3 install -q pip --upgrade && \
    pip3 install -q -r req.txt && \
    rm req.txt

RUN pip3 freeze
    
WORKDIR /app
COPY mock/api.py /app

EXPOSE 8000

CMD ["uvicorn", "api:app", "--host", "0.0.0.0", "--port", "8000"]