FROM python:alpine3.19
RUN apk update && apk add git
WORKDIR /app/giropops-senhas
RUN git clone https://github.com/badtuxx/giropops-senhas.git /app/giropops-senhas
ENV REDIS_HOST=redis-desafio02
EXPOSE 5000
RUN pip install --no-cache-dir -r /app/giropops-senhas/requirements.txt
ENTRYPOINT ["flask"]
CMD ["run","--host=0.0.0.0"]
