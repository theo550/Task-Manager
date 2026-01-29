FROM python:3.12

WORKDIR /app
COPY . /app/

RUN pip install -r requirements.txt

RUN useradd -m appuser
USER appuser

EXPOSE 8000
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
HEALTHCHECK --timeout=5s --retries=3 \
    CMD curl --fail http://localhost:8000|| exit 1
