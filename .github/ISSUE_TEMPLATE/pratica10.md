---
name: "Prática 10"
about: "Template para criar a issue da pratica10"
title: "[Prática 10] – Autenticação com JWT"
labels: ["pratica10"]
assignees: ''
---

## 📌 Contexto
Em outra prática, implementamos uma autenticação "fake" que apenas mudava um booleano no estado. Agora, vamos elevar o nível: a aplicação **Aluno Online** deve realizar uma autenticação real contra uma API. 

Em sistemas modernos, não enviamos a senha do usuário em todas as requisições. Em vez disso, após o login, recebemos um **Token (JWT - JSON Web Token)**. Esse token é como um "crachá digital" que o Frontend deve guardar e apresentar em cada chamada à API para provar quem o usuário é.

## ❓ Problema Norteador
Como armazenar as credenciais do usuário de forma persistente e segura para que ele não precise fazer login novamente ao atualizar a página, e como garantir que o Token seja enviado automaticamente em todas as requisições protegidas?

## 🎯 Objetivo
Nesta prática, você irá:
- Entender o fluxo de autenticação baseada em **Tokens (JWT)**;
- Implementar a persistência de estado via **LocalStorage** com segurança;
- Configurar cabeçalhos globais para requisições autenticadas;
- Aplicar boas práticas de Segurança (ocultar informações sensíveis e gerenciar sessões expiradas).

## 📝 Instruções da Atividade
**1️⃣ Preparação do ambiente**
1. Abra o **Visual Studio Code** na pasta do seu repositório.
2. Certifique-se de que está na branch `develop`.
```bash
git checkout develop
```
3. Crie e alterne para a branch desta prática.
```bash
git checkout -b feature/pratica10
```

**2️⃣ Implementação do código**
1. Adicione um recurso `/usuarios` no seu `db.json` com e-mail e senha.
2. Implemente no seu `authService.js` uma lógica que busque o usuário por e-mail e valide a senha. Se correto, simule o recebimento de um token (pode ser uma string aleatória em base64).
3. Ao logar com sucesso, salve o objeto do usuário e o token no LocalStorage.
4. O `AuthContext` deve verificar se existe um token no LocalStorage antes de decidir se o usuário está logado ou não.
5. Ao sair da aplicação, limpe a sessão apagando os dados armazenados no LocalStorage.
6. Refatore o `requerimentosService.js` para incluir o header `Authorization: Bearer <SEU_TOKEN_AQUI>` nas requisições listar e cadastrar.
7. Faça o `requerimentosService.js` retornar um erro **401 (Unauthorized)** caso não tenha um token nas requisições. Force o logout do usuário imediatamente.

**3️⃣ Execução e teste**
1. Inicie o servidor de desenvolvimento (caso não esteja rodando):
```bash
docker compose exec app npm run dev
```
2. Acesse no navegador: `http://localhost:5173`.
3. Teste os seguintes cenários:
- O login só é permitido se as credenciais coincidirem com os dados do `db.json`;
- Ao recarregar a página (F5), o usuário logado continua logado (sessão persistente);
- Ao clicar em "Sair", o LocalStorage é limpo completamente;
- Inspecionando a aba **Network** (Rede) do navegador, é possível ver o Token sendo enviado no cabeçalho das requisições de Requerimentos;
- Se o token for removido manualmente do LocalStorage, a aplicação redireciona o usuário para o Login no próximo clique

**4️⃣ Checklist antes de enviar**
- [ ] Branch criada a partir da `develop`;
- [ ] `src/services/authService.js` criado;
- [ ] Projeto executa sem erros.

## 📤 Entrega da Prática
1. Abra outro terminal do VSCode (isso garante que você esteja na pasta raiz).
2. Adicione os arquivos ao controle de versão. Substitua `#ID` pelo número da Issue.
```bash
git add .
git commit -m "feat: conclui pratica10. Fecha #ID"
```
3. Envie suas alterações para o GitHub.
```bash
git push origin feature/pratica10
```
4. No GitHub, clique em **Compare & pull request**.
5. **Importante**: Certifique-se de que o **base repository** é o seu repositório e a **base branch** é a `develop`.
6. Na descrição, escreva: `Nesta prática, implementei a autenticação persistente com JWT simulado. Fecha #ID`. Substitua `#ID` pelo número da Issue.
7. Clique em **Create pull request** e envie o link do PR na plataforma de ensino.

⚠️ **Erros comuns**
- Esquecer de subir o JSON Server no container;
- Esquecer de salvar e apagar dados no LocalStorage;
- Esquecer o header `Authorization: Bearer <SEU_TOKEN_AQUI>` nas requisições;
- Criar a branch de trabalho a partir de uma branch diferente da `develop`;
- Enviar o PR para a branch errada.