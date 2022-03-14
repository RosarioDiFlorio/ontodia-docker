# ontodia-docker
Dockerization of ontodia diagram library


## Step 1 - run fuseki jena triplestore

### creating volume storage 
docker run --name fuseki-data -v /fuseki busybox

### lunching fuseki container
docker run  -d -p 3030:3030 --name fuseki -e TDB=2 -e FUSEKI_DATASET_1=ontology --volumes-from fuseki-data -e ADMIN_PASSWORD=pw123 stain/jena-fuseki

## Step 2 - upload ttl file in the ontology repository
go to localhost:3030 

add data and select the ontology you want to upload.

## Step 3 - launch docker compose
docker-compose up --build
