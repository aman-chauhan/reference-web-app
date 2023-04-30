FROM python:3.11-alpine3.17
RUN apk add protoc && \
    apk add protobuf-dev && \
    pip install protobuf && \
    pip install grpcio && \
    pip install grpcio-tools
WORKDIR /protobuf
CMD protoc  --proto_path=src/common --proto_path=src/api --proto_path=src/grpc \
            --python_out=/py_pb_gen \
            src/*/*.proto \
        && \
    python -m grpc_tools.protoc \
            --proto_path=src/common --proto_path=src/api --proto_path=src/grpc \
            --grpc_python_out=/py_pb_gen \
            src/grpc/*.proto