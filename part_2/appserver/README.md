
cd ./appserver
docker image build -t registration .
cd ./database
docker image build -t registrationdb .

docker container run -d -p 3306:3306 --name registrationdb --network FirstNetwork registrationdb
docker container run -d -p 8080:8080 -p 8000:8000 --name registration --network FirstNetwork registration



Webserver container for the User Signup demo application.

This container is a Tomcat 7 servlet engine with remote debugging enabled.
