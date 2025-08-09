.PHONY: proto

proto:
	protoc \
		-I proto \
		--proto_path=proto \
		--go_out=. \
		--go-grpc_out . \
		--grpc-gateway_out . \
		--grpc-gateway_opt logtostderr=true \
		proto/identity.proto

protoc:
	mkdir -p protogen/golang && \
	cd proto && \
	protoc \
		--go_out=../protogen \
		--go_opt=paths=source_relative \
		--go-grpc_out=../protogen \
		--go-grpc_opt=paths=source_relative \
		--grpc-gateway_out=../protogen \
		--grpc-gateway_opt paths=source_relative \
		--grpc-gateway_opt generate_unbound_methods=true \
		--grpc-gateway_opt logtostderr=true \
		./**/*.proto
