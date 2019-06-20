Este diretório possui os arquivos Dockerfile usados para gerar as imagens de container customizadas para o CodeBuild.

em cada diretório faça:

`docker build -t <accountID>.dkr.ecr.<region>.amazonaws.com/<nome_da_imagem> .`

`docker push <accountID>.dkr.ecr.<region>.amazonaws.com/<nome_da_imagem>:latest`
