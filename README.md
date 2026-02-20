# 🎓 FRONT: Construção de Frontend
Repositório destinado às aulas teóricas e às atividades práticas da disciplina.

## 🛠️ Ambiente de Desenvolvimento
Para acompanhar a disciplina, você precisará das seguintes ferramentas:
| Ferramenta | O que é? | Recomendação |
| :--- | :--- | :--- |
| Editor de código | Ambiente onde você escreverá seu código. | [Visual Studio Code](https://code.visualstudio.com/) | 
| Plataforma de Containerização | Responsável por executar aplicações em containers. | [Docker Desktop](https://www.docker.com/) |
| Versionador | Controla e registra o histórico de alterações do código. | [Git](https://git-scm.com/) |

## 📂 Estrutura de Pastas
Este repositório está organizado da seguinte forma:
- **aulas/**: Contém os códigos utilizados nas aulas teóricas.
- **praticas/aluno-online-vanilla/**: Contém o projeto de um portal utilizando HTML5, CSS3 e JavaScript puro.
- **praticas/aluno-online-react/**: Contém o projeto de um portal utilizando React.js + Vite.

## 🐳 Como Rodar o Projeto
Siga os passos:
1. Acesse a pasta do projeto:
```bash
cd pasta-do-projeto
```
2. Suba o container e instale as dependências:
```bash
docker compose up -d
docker compose exec app npm install
```
3. Inicie o servidor de desenvolvimento:
```bash
docker compose exec app npm run dev
```
4. Acesse no navegador: `http://localhost:5173`

## 🚀 Fluxo de Trabalho Acadêmico
Todas as atividades seguem o fluxo de trabalho baseado em [GitFlow](https://www.atlassian.com/br/git/tutorials/comparing-workflows/gitflow-workflow).

### 1. Configuração Inicial (realizar apenas uma vez)
Execute estes passos para preparar seu ambiente:
1. **Fork**: Clique no botão `Fork`, no topo da página, para criar uma cópia deste repositório na sua conta GitHub.
2. **Clone**: Faça o clone o *seu fork* para a sua máquina local:
```bash
git clone https://github.com/SEU_USUARIO/front-SEMESTRE.git
```
3. **Identificação**: Certifique-se que seu **nome** e **email** estejam configurados no Git:
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
``` 

### 2. Entrega de Atividades (repetir para cada prática)
Para cada nova atividade, siga o fluxo abaixo:
1. **Crie uma Issue**: Acesse a aba `Issues` no GitHub e clique no botão `New issue` para criar a prática usando o template correspondente.
2. **Crie uma branch**: Acesse a branch de referência da prática e crie uma nova branch.
3. **Desenvolva e teste**: Implemente os arquivos na pasta do projeto e realize os testes.
4. **Envie para o GitHub**: Salve suas alterações e envie para o *seu fork*
5. **Solicite a revisão**: Acesse o *seu fork* no GitHub e crie um `pull request` direcionando para a branch `develop` do repositório do professor. 

### 3. Feedback e Avaliação
Os Pull Requests podem receber os seguintes status:
- `aceito`: Indica que a atividade foi validada com sucesso.
- `revisao`: Indica que a atividade está sendo revisada pelo professor.
- `ajustes`: Indica que há modificações necessárias (ver comentários no PR).
