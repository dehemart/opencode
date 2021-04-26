# Opencode
## Ambiente de desenvolvimento

Prepara um ambiente docker para edição de temas em serviços de hopedagem que utilizem o Opencode para manter os temas.

## Primeiros passos
### Variáveis de ambiente

No arquivo `.env`, adicione o API_KEY, PASSWORD E THEME_ID, fornecido pela empresa que hospeda seu site.

#### Exemplo de preenchimento
```shell
# Exemplo de uso (desconsiderar dados)

API_KEY=d614da37e97d9e5b3bc1ce35024a0ce6
PASSWORD=3941f8ccdba855061a8f6a2d9de17cc8
THEME_ID=1308
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
      opencode configure API_KEY PASSWORD THEME_ID  # Configurado no arquivo .env 
      opencode download
      opencode clean
      opencode watch
```
Abaixo listamos os possíveis comando com o Opencode   

### Comandos adicionais
Para executar algum comando:
```shell
docker exec it ID_DO_CONTAINER /bin/sh
```

#### Comandos Opencode

| Comando | Descrição |
|---|---|
|`opencode clean`                                       | Limpa o cache de arquivos estáticos |
|`opencode components`                                  | Listagem (opencode components list) ou instalação de componentes(opencode components install nome) |
|`opencode configure API_KEY PASSWORD THEME_ID`         | Configura o tema que sera modificado |
|`opencode download FILE`                               | Baixa o arquivo informado ou todos se FILE for omitido |
|`opencode help [COMMAND]`                              | Describe available commands or one specific command |
|`opencode list`                                        | Lista todos os temas da loja |
|`opencode new API_KEY PASSWORD THEME_NAME THEME_BASE`  | Cria um novo tema com o nome informado |
|`opencode open`                                        | Abre a loja no navegador |
|`opencode rm FILE`                                     | Remove um arquivo do tema |
|`opencode systeminfo`                                  | Mostra informações do sistema |
|`opencode upload FILE`                                 | Sobe o arquivo informado ou todos se FILE for omitido |
|`opencode watch`                                       | Baixa e sobe um arquivo sempre que ele for salvo |
