# elastic_tf

sudo nano /etc/kibana/kibana.yml

server.host: "0.0.0.0"

sudo systemctl daemon-reload
sudo systemctl restart kibana
sudo systemctl status kibana


sudo /usr/share/elasticsearch/bin/elasticsearch-create-enrollment-token --scope kibana

sudo /usr/share/kibana/bin/kibana-verification-code

sudo /usr/share/elasticsearch/bin/elasticsearch-reset-password -u elastic -i

sudo /usr/share/kibana/bin/kibana-encryption-keys generate

lo que devuelva copiarlo en sudo nano /etc/kibana/kibana.yml


########################################

Generar SSL

sudo mkdir -p /etc/kibana/certs
cd /etc/kibana/certs

# Generar clave privada
sudo openssl genrsa -out kibana.key 2048

# Generar certificado autofirmado
sudo openssl req -new -x509 -key kibana.key -out kibana.crt -days 365



# Asignar permisos

sudo mv /home/ubuntu/kibana.key /etc/kibana/certs/
sudo mv /home/ubuntu/kibana.crt /etc/kibana/certs/

sudo chown kibana:kibana /etc/kibana/certs/kibana.key /etc/kibana/certs/kibana.crt
sudo chmod 600 /etc/kibana/certs/kibana.key
sudo chmod 644 /etc/kibana/certs/kibana.crt
