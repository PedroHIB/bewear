# Nome do Projeto

Breve descrição do projeto — o que ele faz e seu propósito principal.

---

## 🏆 Badges

![Build](https://img.shields.io/github/actions/workflow/status/seu-usuario/seu-repo/ci.yml?label=build&logo=github)
![License](https://img.shields.io/github/license/seu-usuario/seu-repo?color=blue)
![Node](https://img.shields.io/badge/node-%3E%3D18-green?logo=node.js)
![Deploy](https://img.shields.io/github/deployments/seu-usuario/seu-repo/Production?label=vercel&logo=vercel)

---

## 🚀 Tecnologias Utilizadas

- **[Next.js](https://nextjs.org/)** — Framework React com renderização híbrida (SSR/SSG) e otimizações de performance.
- **[TailwindCSS](https://tailwindcss.com/)** — Framework CSS utilitário para estilização rápida e responsiva.
- **[Better Auth](https://www.better-auth.com/)** — Biblioteca de autenticação e autorização agnóstica ao framework, voltada para TypeScript.
- **[shadcn/ui](https://ui.shadcn.com/)** — Sistema de componentes acessíveis e personalizáveis baseado em Tailwind CSS/Radix.
- **[Neon](https://neon.com/)** — Banco de dados serverless compatível com PostgreSQL, com escalabilidade automática.

---

## 📦 Instalação

### Requisitos

- Node.js >= 18
- TypeScript >= 5
- Conta ativa no Neon

```bash
git clone https://github.com/seu-usuario/seu-repo.git
cd seu-repo
npm install
```

⚙️ **Configuração**

1. Renomeie o arquivo `.env.example` para `.env` e adicione as variáveis de ambiente:

```env
DATABASE_URL="postgresql://neondb_owner:npg_GTroFEBNnM61@ep-autumn-pine-acobzgtm-pooler.sa-east-1.aws.neon.tech/neondb?sslmode=require&channel_binding=require"
BETTER_AUTH_SECRET=Mn4TqRhbc6YMqaXZcNyQrpV8B1v1TsmS
```

2. Configure o Better Auth no seu projeto:

```ts
import { betterAuth } from "better-auth";
import { Pool } from "pg";
import { organization, twoFactor } from "better-auth/plugins";

export const auth = betterAuth({
  database: new Pool({ connectionString: process.env.DATABASE_URL }),
  emailAndPassword: { enabled: true },
  plugins: [organization(), twoFactor()],
});
```

🗄️ **Banco de Dados (Drizzle + Neon)**  
Após alterar o schema do banco de dados, execute:

```bash
npx drizzle-kit studio
```

Para visualizar e gerenciar seu banco via interface:

```bash
npx drizzle-kit studio
```

## 💻 Uso

### Better Auth

- Suporte para autenticação por email/senha, provedores OAuth e plugins como 2FA e magic link.
- Integração simples com frameworks como React, Next.js, Svelte, entre outros.

### shadcn/ui

- Componentes acessíveis e altamente personalizáveis.
- Ideal para criar seu próprio design system.

### Neon

- Banco de dados PostgreSQL serverless.
- Recursos avançados como branching e time-travel para ambientes de desenvolvimento.

---

## 📸 Capturas de Tela

> Adicione aqui prints da aplicação mostrando a interface e exemplos de uso.

---

## 🌐 Deploy

O projeto está disponível em:  
**[Link do Deploy](#)**

Deploy automático via Vercel a cada push na branch `main`.

---

## 📍 Roadmap

- [ ] Criar interface de login com shadcn/ui
- [ ] Adicionar passkey no Better Auth
- [ ] Configurar branching no Neon para ambientes separados

---

## 🤝 Contribuição

Sinta-se à vontade para contribuir!

Este projeto foi criado por [Felipe Rocha](https://github.com/fullstackclubeducacao).
Desenvolvido por [Pedro Barros](https://github.com/PedroHIB).

Para contribuir, faça um fork, crie uma branch e envie um pull request.

---
