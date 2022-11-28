FROM python:3

RUN apt-get update -qy
RUN apt-get install -y gettext-base

COPY app /app

RUN useradd -m -d /backend backend

RUN mv app/ /backend/

RUN chown -R backend /backend/

RUN su - backend

RUN pip3 install flask

COPY student.txt.template /backend/app/

WORKDIR /backend/app/

ENV FLASK_APP=web
ENV FLASK_RUN_PORT=5000
ENV FLASK_RUN_HOST=0.0.0.0
ENV STUDENT_NAME="Andrew"
ENV STUDENT_ID="A01265976"

ENTRYPOINT [ "/bin/bash", "-c" ]

CMD ["envsubst < student.txt.template > student.txt; python3 -m flask run"]
