---
name: "Prática 06"
about: "Template para criar a issue da pratica06"
title: "[Prática 06] – Navegação entre Páginas com React Router"
labels: ["pratica06"]
assignees: ''
---

## 📌 Contexto
Nas práticas anteriores, você criou as páginas da aplicação **Aluno Online** como componentes React. Entretanto, a aplicação ainda não possui navegação real entre suas páginas.

Atualmente, para visualizar uma página diferente é preciso alterar manualmente o `App.jsx`, o que é inviável em uma aplicação real.

A equipe decidiu implementar um sistema de rotas para que o usuário possa navegar entre as páginas sem recarregar a aplicação.

## ❓ Problema Norteador
Como estruturar a navegação para que o usuário sinta que está em um aplicativo fluido, mantendo partes da interface fixas (como o Menu) enquanto apenas o conteúdo central é substituído com base na URL?

## 🎯 Objetivo
Nesta prática, você irá:
- Definir rotas para cada página da aplicação;
- Implementar o padrão **Layout & Outlet** para reaproveitamento de interface;
- Diferenciar links tradicionais (`<a>`) de navegação SPA (`NavLink`);
- Garantir que a navegação ocorra sem recarregamento de página.

## 📝 Instruções da Atividade
**1️⃣ Preparação do ambiente**
1. Abra o **Visual Studio Code** na pasta do seu repositório.
2. Abra um terminal e certifique-se de que está na branch `develop`.
```bash
git checkout develop
```
3. Crie e alterne para a branch desta prática.
```bash
git checkout -b feature/pratica06
```

**2️⃣ Implementação do código**
1. No terminal, instale o React Router;
2. Configure o ponto de entrada da aplicação (`main.jsx`) para suportar navegação via histórico do navegador;
3. Crie o componente `Layout` (em `src/layouts/`) que deve envolver as páginas filhas. Utilize o componente `<Outlet />` para indicar exatamente onde o conteúdo dinâmico deve ser injetado.
4. Configure o `App.jsx` para gerenciar a árvore de rotas:
- A rota `/` deve carregar o `Layout`.
- As demais rotas (`/faltas`, `/notas`, `/boletos`, etc.) devem ser **filhas** da rota principal.
5. Refatore o componente `Menu` utilizando o componente `<NavLink>` para criar links de acesso às páginas;
6. Implemente um feedback visual (estilo CSS) que mostre ao aluno em qual página ele está no momento, usando os recursos nativos do `NavLink`.

**3️⃣ Execução e teste**
1. Inicie o servidor de desenvolvimento (caso não esteja rodando):
```bash
docker compose exec app npm run dev
```
2. Acesse no navegador: `http://localhost:5173`.
3. Teste a navegação e verifique:
- Se ao clicar nos itens do menu a página muda sem recarregar;
- Se a URL no navegador é atualizada corretamente;
- Se o item de menu da página atual aparece destacado visualmente;
- Se os botões de voltar/avançar do navegador funcionam;
- Se não há erros no console do navegador.

**4️⃣ Checklist antes de enviar**
- [ ] Branch criada a partir da `develop`
- [ ] `react-router` instalado
- [ ] `BrowserRouter` configurado no `main.jsx`
- [ ] Componente `Layout` criado com `<Outlet />`
- [ ] Rotas configuradas corretamente no `App.jsx`
- [ ] Menu lateral usando `<NavLink>` com estilo ativo
- [ ] Projeto executa sem erros

## 📤 Entrega da Prática
1. Abra outro terminal do VSCode (isso garante que você esteja na pasta raiz).
2. Adicione os arquivos ao controle de versão e grave suas alterações. Substitua `#ID` pelo número da Issue (ex.: 11).
```bash
git add .
git commit -m "feat: conclui pratica06. Fecha #ID"
```
3. Envie suas alterações para o GitHub.
```bash
git push origin feature/pratica06
```
4. No GitHub, clique no botão **Compare & pull request**.
5. **Importante**: Certifique-se de que o **base repository** é o seu repositório e a **base branch** é a `develop`.
6. Na descrição, escreva: `Nesta prática, implementei a navegação entre páginas com React Router. Fecha #ID`. Substitua `#ID` pelo número da Issue.
7. Clique em **Create pull request** e envie o link do PR na plataforma de ensino.

⚠️ **Erros comuns**
- Envolver o `<BrowserRouter>` no lugar errado (dentro do `App` em vez de no `main.jsx`);
- Esquecer o `<Outlet />` no componente `Layout`, fazendo as páginas não renderizarem;
- Usar `<a href="...">` no menu em vez de `<NavLink to="...">`;
- Definir a rota do `Dashboard` como `/dashboard` em vez de `/`, deixando a raiz vazia;
- Criar a branch de trabalho a partir de uma branch diferente da indicada;
- Enviar o PR para a branch errada.