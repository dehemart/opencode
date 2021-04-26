# Opencode
## Ambiente de desenvolvimento

Prepara um ambiente docker para edição de temas em serviços de hopedagem que utilizem o opencode para manter os temas.

## Primeiros passos
### Variáveis de ambiente

No arquivo .env, adicione o API_KEY, PASSWORD E THEME_ID referente à loja Tray.

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

Este comando irá executar o opencode num container e baixarṕa o tema, de acordo com o configurado no THEME_ID 

### Comandos adicionais
Para executar algum comando do opencode

```shell
docker exec it ID_DO_CONTAINER /bin/sh
```

#### Comandos opencode
Help: `opencode -h`