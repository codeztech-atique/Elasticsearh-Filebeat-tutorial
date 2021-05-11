Step 1 - Create a folder where your log file will be created.
Step 2 - Open filebeat.yml file and change the Filebeat inputs paths (Define your folder paths) also do enabled: true
Step 3 - If you are running kibana then setup.kibana: host: "localhost:5601" as per the documentation (https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-configuration.html) 


After that -- If your index is not there into Elasticsearch then you need to create it maunally

deb and rpm: filebeat setup --index-management -E output.logstash.enabled=false -E 'output.elasticsearch.hosts=["localhost:9200"]'

mac: ./filebeat setup --index-management -E output.logstash.enabled=false -E 'output.elasticsearch.hosts=["localhost:9200"]'

brew: filebeat setup --index-management -E output.logstash.enabled=false -E 'output.elasticsearch.hosts=["localhost:9200"]'

linux: ./filebeat setup --index-management -E output.logstash.enabled=false -E 'output.elasticsearch.hosts=["localhost:9200"]'

docker: docker run docker.elastic.co/beats/filebeat:7.5.0 setup --index-management -E output.logstash.enabled=false -E 'output.elasticsearch.hosts=["localhost:9200"]'

windows:

Open a PowerShell prompt as an Administrator (right-click the PowerShell icon and select Run As Administrator).

From the PowerShell prompt, change to the directory where you installed Filebeat, and run:

PS > .\filebeat.exe setup --index-management -E output.logstash.enabled=false -E 'output.elasticsearch.hosts=["localhost:9200"]'




Step 4 - Run Elasticsearch
Step 5 - Run Kibana
Step 6 - Inside the log folder create a log file by saying - touch test1.log
Step 7 - Go to Filebeat/bin folder then run 

         ./filebeat -e -c filebeat.yml &   [& that means has to run background]




Note - If you want to load the kibana dashboard ./filebeat setup --dashboards
