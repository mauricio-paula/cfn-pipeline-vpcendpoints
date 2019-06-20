Este diretório possui os arquivos Dockerfile usados para gerar as imagens de container customizadas para o CodeBuild.

em cada diretório faça:

`docker build -t <accountID>.dkr.ecr.<region>.amazonaws.com/<nome_da_imagem> .`

`docker push <accountID>.dkr.ecr.<region>.amazonaws.com/<nome_da_imagem>:latest`


# Configuração da Policy no ECR
Para que o CodeBuild tenha permissão de fazer o pull das imagens é necessário cria uma policy em cada repositório do ECR, conforme abaixo:

`
{
  "Version": "2008-10-17",
  "Statement": [
    {
      "Sid": "AllowCodeBuild",
      "Effect": "Allow",
      "Principal": {
        "Service": "codebuild.amazonaws.com"
      },
      "Action": [
        "ecr:BatchGetImage",
        "ecr:DescribeImages",
        "ecr:DescribeRepositories",
        "ecr:GetDownloadUrlForLayer",
        "ecr:GetLifecyclePolicy",
        "ecr:GetLifecyclePolicyPreview",
        "ecr:GetRepositoryPolicy"
      ]
    }
  ]
}
`
