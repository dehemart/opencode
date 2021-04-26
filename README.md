# Opencode
## Ambiente de desenvolvimento

Prepara um ambiente docker para edição de temas em serviços de hopedagem que utilizem o Opencode para manter os temas.

## Primeiros passos
### Variáveis de ambiente

No arquivo `.env`, adicione o API_KEY, PASSWORD E THEME_ID, fornecido pela empresa que hospeda seu site.

#### Exemplo de preenchimento (desconsiderar dados)
```shell
API_KEY=20a699301d454509691f3ea02c1cba4b
PASSWORD=ea0727075e1639a42fd966a2f6e67abc
THEME_ID=1
```
### Iniciar container

Na pasta raiz do projeto, execute:

```shell
docker-compose up -d
```
Este comando irá executar o Opencode num container Docker e baixará o tema, de acordo com o THEME_ID  
Será criada uma pasta, `theme`, onde serão armazenados os arquivos  a serem editados.   

       
Caso não tenha alterado o `docker-compose.yml`, o Opencode iniciará com os seguintes comandos iniciais:
```shell
opencode configure API_KEY PASSWORD THEME_ID  # Configurado no arquivo .env.exemplo 
opencode download
opencode clean
opencode watch
```
Abaixo listamos os possíveis comando com o Opencode   

### Comandos adicionais
Para acessar o terminal do Opencode:
```shell
docker exec it opencode /bin/sh
```
Para executar um comando, sem acessar o terminal
```shell
docker exec it opencode /bin/sh {{um dos comando da tabela abaixo}}
```

#### Comandos Opencode

| Comando | Descrição |
|---|---|
|opencode clean                                       | Limpa o cache de arquivos estáticos |
|opencode components                                  | Listagem de componentes|
|opencode components install NOME_COMPONENTE          | Instalação de componentes |
|opencode configure API_KEY PASSWORD THEME_ID         | Configura o tema que sera modificado |
|opencode download FILE                               | Baixa o FILE informado ou todos se for omitido |
|opencode help [COMMAND]                              | Ajuda |
|opencode list                                        | Lista todos os temas da loja |
|opencode new API_KEY PASSWORD THEME_NAME THEME_BASE  | Cria um novo tema com o nome informado |
|opencode open                                        | Abre a loja no navegador |
|opencode rm FILE                                     | Remove um arquivo do tema |
|opencode systeminfo                                  | Mostra informações do sistema |
|opencode upload FILE                                 | Sobe o FILE informado ou todos se for omitido |
|opencode watch                                       | Baixa e sobe um arquivo sempre que ele for salvo |
