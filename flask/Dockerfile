FROM python:3.7
ARG GIT_BRANCH
RUN useradd -ms /bin/bash flask-user 
USER flask-user
WORKDIR /home/flask-user
RUN git clone -b $GIT_BRANCH https://github.com/JHU-EN650-631-01-SP22-G01/server.git server
COPY --chown=flask-user:flask-user .env server
WORKDIR /home/flask-user/server/

ENV PATH="/home/flask-user/.local/bin:${PATH}"
RUN git pull --ff-only\
    && pip install --user --upgrade pip \
    && pip install --user gunicorn \
    && pip install --user -r requirement.txt

CMD ["gunicorn", "-w", "5", "-b", "0.0.0.0:5000", "app:app"]
