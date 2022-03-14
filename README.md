# ontodia-docker
Dockerization of ontodia diagram library


## fuseki jena

### creating volume storage 
docker run --name fuseki-data -v /fuseki busybox

### lunching fuseki container
docker run  -d -p 3030:3030 --name fuseki -e TDB=2 -e FUSEKI_DATASET_1=ontology --volumes-from fuseki-data -e ADMIN_PASSWORD=pw123 stain/jena-fuseki



