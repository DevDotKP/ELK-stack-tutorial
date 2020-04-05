# ELK-stack-tutorial
Tutorial of the Elasticsearch, Logstash and Kibana. 


LECTURE 1: 
These tutorial is for windows. Please modify the commands based on the OS.


1. Downloading the stack
	
	Download Elasticsearch, Logstash, Kibana and FileBeat from "https://www.elastic.co/downloads/"

2. Starting elasticsearch

	- Head on over to the location where the Elasticsearch is extracted, go to the bin folder and type in the command "elasticsearch.bat"
	- Go to your browser, hit localhost:9200. Assuming no changes have been made to the elasticsearch config, you'll see something like this
	 
				{
					"name" : "XYZ",
					"cluster_name" : "elasticsearch",
					"cluster_uuid" : "N_hqAchlSMOKmhVl4nf2Gg",
					"version" : {
									"number" : "7.4.0",
									"build_flavor" : "default",
									"build_type" : "zip",
									"build_hash" : "22e1767283e61a198cb4db791ea66e3f11ab9910",
									"build_date" : "2019-09-27T08:36:48.569419Z",
									"build_snapshot" : false,
									"lucene_version" : "8.2.0",
									"minimum_wire_compatibility_version" : "6.8.0",
									"minimum_index_compatibility_version" : "6.0.0-beta1"
								},
					"tagline" : "You Know, for Search"
				}
3. Configuring and starting Kibana
	
	- Navigate to the location where Kibana is installed. Inside that folder, under the sub-folder 'config', you'll be able to see config.yml. Make sure the elasticsearch.url = localhost:9200
	- Type in the command "kibana.bat" after navigating to the bo folder
	- Verify by going to localhost:5601

4. Putting values into Kibana	
	
	- Head to the dev tools, to the right of the screen
	 
	SYNTAX: PUT {index}/_create/{id}
	
	 Give the following command
	 
	 PUT vehicles/_create/3
  
  {
	"Make": "Aston Martin",
	"Model": "DB9",
	"CountryOfOrigin": "GBR",
	"Currency": "GBP",
	"Cost": "120,000"
}
  
  
5. Reading values from Kibana 
	
	SYNTAX: GET {index}/_doc/{id}
	
	Example:
	GET vehicles/_doc/3

6. Check whether a document is present or not
	
	- If it is present, the user will get a 200 OK, otherwise a 404.
		SYNTAX: HEAD {index}/_doc/{id}
		
7. Delete a document
	
	SYNTAX: DELETE {index}/_doc/{id}
	
