#### ELK

* elastic-search default port >>> 9200
* Logstash  default port >>>9600
* KIbana default port >>> 5601


ELK run from docker
-
* Step1: docker pull sebp/elk
* Step2: sudo docker run -p 5601:5601 -p 9200:9200 -p 5044:5044 -it --name elk sebp/elk
* Now,
* goto url localhost:5601
* Localhost:9200

Elasticsearch
*  Real time distributed and analytic engine>>java language>>document based>> instead tables and schemas>> for single page application
* Query/Analyze>>>it let you undarsand billions of log lines easily>> can query both structured and unstructured, geo, metric etc.
* You can aggregate data by days>>>you can track files
* Elastic search is scalable >>> it can be scalable across multiple nodes>>really fast in performance>>>multilingual>>document oriented
Prerequisites:
* Java version must be 7 or more
* Https://www.elastic.co/downloads
* Click on Download to get the zip file
* Unzip the file
* goto bin folder from command line and execute >>>>> bin/elasticsearch >>>>> file will open and goto local host and port is 5601>>>json file will open
* 
For kibana
Goto kibana folder>>bin>>and execute >>>bin/kibana


For Logstash
./bin/logstash -f cars.config 
