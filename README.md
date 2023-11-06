# jenkins-docker-agent-dotnet-core

cd dotnet3
docker build -t custom-jenkins-agent-dotnet3 . 
docker tag custom-jenkins-agent-dotnet5 prashanthbabu07/dotnet-core:3.1.412
docker push prashanthbabu07/dotnet-core:3.1.412

cd dotnet5
docker build -t custom-jenkins-agent-dotnet5 . 
docker tag custom-jenkins-agent-dotnet5 prashanthbabu07/dotnet-core:5.0.408
docker push prashanthbabu07/dotnet-core:5.0.408


cd dotnet7
docker build -t custom-jenkins-agent-dotnet7 . 
docker tag custom-jenkins-agent-dotnet5 prashanthbabu07/dotnet-core:7.0.113
docker push prashanthbabu07/dotnet-core:7.0.113