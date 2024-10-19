Etapas para o deploy

Buildando a imagem
docker build --platform linux/amd64 -t backend-eventos:1.0 .


Substituir o XX pela versão atual

Enviando para o Docker Hub
docker tag backend-eventostec:XX.0 kipperdev/backend-eventostec:XX.0
docker push kipperdev/backend-eventostec:XX.0
Substituir o XX pela versão atual

Acessa máquina virtual
ssh ec2-user@44.212.51.2

Puxa e executa a imagem do Docker
docker pull kipperdev/backend-eventostec:XX.0
docker run -d -p 80:80 kipperdev/backend-eventostec:XX.0

É importante mapear o Docker para a porta 80 da máquina virtual, pois é a porta que o LB está acessando.