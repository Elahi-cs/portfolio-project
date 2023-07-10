FROM buildpack-deps:bookworm

# ensure local python is preferred over distribution python
ENV PATH /usr/local/bin:$PATH

# http://bugs.python.org/issue19846
# > At the moment, setting "LANG=C" on a Linux system *fundamentally breaks Python 3*, and that's not OK.
ENV LANG C.UTF-8

WORKDIR /code

COPY requirements.txt /code/
RUN pip3 install -r requirements.txt 
# && pip install gunicorn

COPY . /code/

CMD ["python3", "manage.py", "runserver"]
#CMD ["gunicorn", "-b", "0.0.0.0:8000", "--workers=5", "personal.wsgi"]
