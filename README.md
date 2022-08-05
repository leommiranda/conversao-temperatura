## Como rodar

```
# clonar o repositório
git clone https://github.com/leommiranda/conversao-temperatura

# ir para a pasta "k8s" deste repositório
cd conversao-temperatura/k8s

# criar cluster com k3d
k3d cluster create mycluster --servers 1 --agents 1 -p "30000:30000@loadbalancer"

# rodar site
kubectl apply -f deployment.yaml

# conferir até estar rodando (dica: usar watch)
kubectl get all

# acessar localhost:30000 pelo browser
```

## Como atualizar a imagem docker

```
# ir para a pasta "src" deste repositório
cd conversao-temperatura/src

# build a imagem docker
docker build . -t leommiranda/conversao-temperatura:v[numero_da_versao]

# fazer login para usar o dockerhub
docker login

# subir a imagem docker para o dockerhub
docker push leommiranda/conversao-temperatura:v[numero_da_versao]

# atualizar número da versão no arquivo k8s/deployment.yaml
```
