FROM python:3.11-slim

WORKDIR /db/app

COPY /app/requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY /app ./

ENV ALEMBIC_CONFIG=/db/app/alembic.ini

EXPOSE 8001
CMD ["sh", "-c", "alembic -c $ALEMBIC_CONFIG upgrade head && python /db/app/main.py"]