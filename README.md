# elastic-env
Scripts for setting up Elastic Stack environments for experimentation purposes

# Starting Elastic core services
For convenience, the following starts ElasticSearch and Kibana (6.4.0) in Docker containers:

`docker-compose up`

The ElasticSearch API will be exposed at: [http://localhost:9200](http://localhost:9200)

The Kibana API will be exposed at [http://localhost:5601](http://localhost:5601)

# Adding PacketBeat

Assuming you're running on a Mac _and_ would like to capture traffic on your host machine, do not run PacketBeat in a Docker container.  Docker for Mac does not support host networking, which would be required for the container to capture the Mac's traffic.

Instead, download PacketBeat 6.4.0 for Mac separately and run with the supplied configuration file:

`sudo ./packetbeat -c <path-to-packetbeat.yml>`

PacketBeat will generate Kibana dashboards where the captured network traffic will be visible.