FROM node:16-alpine AS builder

WORKDIR /client

COPY . .

RUN npm install

RUN npm run build

FROM nginx:alpine

WORKDIR /usr/share/nginx/html

COPY --from=builder /client/build .

CMD ["nginx", "-g", "daemon off;"]

## BUILDING THE IMAGE 
## docker build -t purchify-client .

## RUNNING THE IMAGE 
## docker run -itd -p 80:80 --name purchify-aws-test purchify-aws-test

## TAGGING THE IMAGE 
## docker tag purchify-aws-test dallenpyrah/purchify-aws-test

## PUSHING THE IMAGE 
## docker push dallenpyrah/purchify-aws-test

## CONNECTING TO AWS EC2 INSTANCE 
## Open Ubuntu 18.04 LTS and run the following commands:
## chmod 400 purchify-login.pem
## ssh -i "purchify-login.pem" ec2-user@ec2-54-212-196-76.us-west-2.compute.amazonaws.com

## CONNECTING TO DOCKER HUB
## docker login --username=<username> --password=<password>

## PULLING IMAGE TO AWS EC2 INSTANCE
## docker pull dallenpyrah/purchify-aws-test:latest
## RUNNING THE IMAGE ON AWS EC2 INSTANCE
## docker run -d -p 80:80 --name purchify-aws-test dallenpyrah/purchify-aws-test
