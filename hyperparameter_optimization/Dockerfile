FROM tensorflow/tensorflow:latest

RUN pip install --upgrade pip

RUN pip --no-cache-dir install \
        keras \
        pandas \
        talib-binary

ENV PYTHONUNBUFFERED=TRUE
ENV PYTHONDONTWRITEBYTECODE=TRUE
ENV PATH="/opt/ml/code:${PATH}"

RUN mkdir -p /opt/ml/input/data
RUN mkdir -p /opt/ml/input/config
RUN mkdir -p /opt/ml/code
RUN mkdir -p /opt/ml/failure
RUN mkdir -p /opt/ml/model
RUN mkdir -p /opt/ml/output

COPY model /opt/ml/code
RUN chmod -R 777 /opt/ml/code
WORKDIR /opt/ml/code