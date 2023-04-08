# Ambiente sandbox de kubernetes

Instalar o kind -> [documentation](https://kind.sigs.k8s.io/docs/user/quick-start/#installation)

Criar o nosso cluster com o kind 

`kind create cluster --config=kind/kind.yaml --name=fullcycle`

Montar imagem docker da aplicação go de exemplo:

`docker build -t davidcardoso01/goserver . -f Dockerfile`

Enviar imagem docker para o registry do dockerhub:

`docker push davidcardoso01/goserver`

Configurar o kubectl para usar o cluster novo:

`kubectl config use-context kind-fullcycle`

Aplicar todos os arquivos yaml da pasta k8s:

`kubectl apply -f k8s/<<FILE>>`