![image](https://github.com/user-attachments/assets/c0e74a89-0e8e-4cf4-b1fc-3a574bc6191f)



# Inicializando a Aplicação

A aplicação é composta por dois repositórios: **backend** e **frontend**, cada um com seu próprio `docker-compose` para facilitar a inicialização.

## Clonando os Repositórios

Antes de iniciar a aplicação, clone os repositórios do backend e frontend:

```sh
# Clone o repositório do backend
git clone https://github.com/Denilsoj/safedriver-back.git

# Clone o repositório do frontend
git clone https://github.com/Denilsoj/safedriver-frontend.git
```

## Executando o Backend

1. Navegue até o diretório do backend:
   ```sh
   cd safedriver-back
   ```
2. Crie um arquivo `.env` na raiz do backend e adicione as seguintes variáveis de ambiente:
   ```ini
   POSTGRES_PASSWORD= //senha banco de dados
   POSTGRES_DB=driversafe
   POSTGRES_USER= //usuário banco de dados
   DATABASE_URL="postgresql://user:password@driversafedb:5432/driversafedb?schema=public"
   
   minio_api_endpoint= http://localhost:9000/
   minio_port=9000
   access_key=minioadmin
   secret_key=minioadmin
   bucket_name=images
   minio_host=minio
   ```

3. Execute o seguinte comando para construir e iniciar os containers:
   ```sh
   docker compose up -d --build
   ```
4. A API estará disponível em: [localhost:8080](http://localhost:8080)
  

## Executando o Frontend

1. Navegue até o diretório do frontend:
   ```sh
   cd safedriver-frontend
   ```
2. Execute o seguinte comando para construir e iniciar os containers:
   ```sh
   docker compose up -d --build
   ```
3. O frontend estará disponível em: [localhost:3000](http://localhost:3000)

## Portas Utilizadas

Garanta que as seguintes portas estejam livres:

- **3000**: Frontend
- **8080**: API (Backend)
- **5432**: Banco de dados
- **9000**: MinIO
- **9001**: MinIO (Painel de administração)

## Tecnologias Utilizadas

- **Frontend:**  Next.js, React Query, Zod, TailwindCSS, ShadCN/UI
- **Estilização:** Tailwind + ShadCN/UI
- **Backend:** Fastify , Prisma, PostgreSQL
- **Infraestrutura:**  Docker, Git
- **Armazenamento:** MinIO

