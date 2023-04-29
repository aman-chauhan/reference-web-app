FROM python:3.11-alpine3.17
RUN apk add protoc && \
    apk add protobuf-dev && \
    pip install protobuf
WORKDIR /protobuf
CMD protoc --proto_path=src/common \
    --proto_path=src/api \
    --python_out=/py_pb_gen \
    src/*/*.proto