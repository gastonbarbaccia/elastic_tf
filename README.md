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
