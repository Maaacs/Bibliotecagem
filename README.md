# Guia de Implantação da Aplicação Livros

Este guia explica como subir os containers para a aplicação Livros, que inclui serviços para o backend, frontend, um banco de dados MySQL e phpMyAdmin para gerenciamento do banco de dados.

## Pré-Requisitos

Antes de iniciar, certifique-se de que você tem o Docker e o Docker Compose instalados em seu sistema. Se não tiver, você pode baixá-los e instalá-los a partir dos seguintes links:

- Docker: https://docs.docker.com/get-docker/
- Docker Compose: https://docs.docker.com/compose/install/

## Estrutura do Projeto

Assegure-se de que a estrutura de diretórios do seu projeto esteja conforme esperado. Os diretórios relevantes são:

- `webacademy-livros-backend/`: Contém os arquivos do backend, incluindo o Dockerfile.
- `webacademy-livros-frontend/`: Contém os arquivos do frontend, incluindo o Dockerfile.
- Arquivos de configuração Docker Compose e `.env` na raiz do projeto.

## Configuração de Ambiente

Antes de iniciar os serviços, verifique se os arquivos `.env` estão configurados corretamente para o seu ambiente. Há três arquivos `.env` importantes:

- `.env` na raiz para configurações do banco de dados e phpMyAdmin.
- `webacademy-livros-backend/.env` para configurações específicas do backend.
- `webacademy-livros-frontend/.env` para configurações específicas do frontend.

## Como Subir os Containers

Para subir os containers, execute os seguintes passos:

1. Abra um terminal e navegue até o diretório raiz do projeto.
2. Execute o seguinte comando para construir e iniciar os containers:

    ```bash
    docker-compose up --build
    ```

   Este comando irá construir as imagens necessárias e iniciar os containers. Importante aguardar alguns minutos para que todos os containers estejam funcionando. Quando os containers estiverem prontos deverá ver no terminal a seguinte mensagem:
   ```[INFO] 2024-04-07 02:38:45 GMT-04: SERVIDOR RODANDO VIOLENTAMENTE NA PORTA 4444.```



3. Para verificar se os containers estão rodando, você pode usar:

    ```bash
    docker ps
    ```

4. Para acessar a aplicação, navegue para `http://localhost:8000` no seu navegador para o frontend e `http://localhost:8080` para o phpMyAdmin.

## Logs

Os principais logs coletados durante a execução e uso da aplicação estão no diretório `webacademy-livros-backend/log`

## Parando os Containers

Para parar e remover os containers, redes e volumes associados, você pode usar o seguinte comando:

```bash
docker-compose down
