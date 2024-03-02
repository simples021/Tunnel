<h1 align="center">
  <img src="https://i.ibb.co/7SMc2NX/logo.jpg" alt="DTunnel" style="width: 80px; height: 80px; border-radius: 50%;">
</h1>

<p align="center">
 <img src="https://img.shields.io/static/v1?label=DTunnel&message=Mod&color=E51C44&labelColor=0A1033" alt="DTunnelMod" />
</p>

![cover](https://i.ibb.co/0yPYBjy/preview.png)

## :rocket: Principais funções

- [x] Layout storages
- [x] Edição de textos
- [x] Edição de layouts
- [x] Edição de categorias
- [x] Edição de configurações

## ✨ Foi utilizado

- [x] Node.js (Runtime)
- [x] Fastify (Framework web super rapido)
- [x] Prisma (ORM moderno para bancos de dados)
- [x] Typescript (Traz segurança e clareza ao código, oferecendo tipagem estática e um desenvolvimento mais robusto)
- [x] JSON Web Token (Autenticação)
- [x] BCrypt (Um forte mecanismo de hash para proteger senhas e dados sensíveis)
- [x] Zod (Oferece validação de dados rápida e flexível em TypeScript)
- [x] ETA (Uma alternativa EJS mais rápida, leve e configurável)

## Iniciando o projeto

Primeiro você deve criar seu arquivo de variável ambiente `.env` na pasta do projeto.
Exemplo:

```cl
PORT=                // 80
NODE_ENV=            // "production"
DATABASE_URL=        // "file:./database.db"
ENCRYPT_FILES=       // "7223fd56-e21d-4191-8867-f3c67601122a"
CSRF_SECRET=         //
JWT_SECRET_KEY=      //
JWT_SECRET_REFRESH=  //
```

`CSRF_SECRET`, `JWT_SECRET_KEY`, `JWT_SECRET_REFRESH` são chaves secretas sensíveis, ninguém além de você deve ter acesso a elas, para garantir a segurança do painel recomendo que utilizem este comando para gerar chaves privadas:

```js
node -e "console.log(require('crypto').randomBytes(256).toString('base64'));"
```

### 1. Instale as dependências:

```bash
npm install
```

### 2. Gerar artefactos do prisma

```bash
npx prisma generate
```

### 3. Crie as migrations do banco de dados

```bash
npx prisma migrate deploy
```

### 4. Testando o projeto

```bash
npm run dev
```
## Executando em modo produção
### 1. Instale o pm2
```bash
npm install -g pm2
```

### 2. Execute usando o pm2
```bash
pm2 start --name "DTunnel" npm -- run dev
```
## Execução automática
Após executar a aplicação, a gente pode configurar o mp2 para iniciar essa execução automáticamente.
### 1. Crie o script de inicialização automática:
```bash
pm2 startup
```

### 2. Salve o status atual do mp2
```bash
pm2 save
```
Isso é tudo! Agora, mesmo quando reiniciar o VPS o painel ficará online automáticamente.
<br />
