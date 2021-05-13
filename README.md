### Simple Python Flask Program with MongoDB

To show how you can see metrics for DB calls also in Python app, we have created a sample app which also uses a database (MongoDB) so that the example is more realistic

If you already have Mongo daemon running, you can skip the following step to install Mongo

Download MongoDB for:
- Mac from https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/
- Linux from https://docs.mongodb.com/manual/administration/install-on-linux/


### Run instructions for sending data to SigNoz
```
sudo pip3 install -r requirements.txt
```

```
sudo opentelemetry-bootstrap --action=install
```

```
OTEL_RESOURCE_ATTRIBUTES=service.name=pythonApp OTEL_EXPORTER_OTLP_ENDPOINT="http://<IP of SigNoz>:4317" opentelemetry-instrument python3 app.py
```

Our web server is running in the port 5000 by default. Browse `http://localhost:5000` and check the data in SigNoz
