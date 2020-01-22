.PHONY: build

build:
	env CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o greeter-srv ./main.go

docker-build: build
	docker build -t greeter .

docker-push: 
	docker tag greeter:latest moorepatrick/k8s-micro-example:0.1.2
	docker tag greeter:latest moorepatrick/k8s-micro-example:latest
	docker push moorepatrick/k8s-micro-example:0.1.2
	docker push moorepatrick/k8s-micro-example:latest
