# 📚 BiblioLab

Sistema digital para organização e gerenciamento de bibliotecas e laboratórios escolares.

O BiblioLab foi desenvolvido com o objetivo de modernizar a organização de acervos escolares, facilitando o acesso aos livros, o controle de usuários, reservas, empréstimos e utilização de salas e laboratórios.

---

## 🎯 Objetivo

O projeto busca substituir processos manuais e sistemas antigos por uma plataforma mais organizada, acessível e fácil de utilizar.

Entre os principais objetivos estão:

- Organizar o acervo escolar digitalmente;
- Facilitar a localização de livros;
- Permitir reservas de livros e espaços;
- Organizar usuários e permissões;
- Melhorar o gerenciamento de salas e laboratórios;
- Facilitar o acesso às informações do acervo;
- Oferecer recursos de acessibilidade;
- Disponibilizar uma interface moderna e responsiva.

---

# 🚀 BiblioLab 3.1

A versão 3.1 representa uma etapa de preparação do projeto para publicação na internet, principalmente através do **GitHub Pages**.

Também foram realizadas melhorias importantes no sistema visual, principalmente no modo escuro e na organização dos arquivos.

## ✨ Principais alterações

### 🌙 Novo sistema de modo escuro

O modo escuro foi revisado para funcionar de maneira mais consistente em todo o sistema.

Agora ele:

- Detecta o tema utilizado pelo sistema operacional;
- Permite alternar manualmente entre claro e escuro;
- Salva a preferência do usuário;
- Mantém a preferência ao recarregar a página;
- Altera fundos, textos, bordas e campos de formulário;
- Melhora a visualização de cards e componentes;
- Evita que a página apareça rapidamente no modo claro antes de aplicar o modo escuro.

A preferência é armazenada localmente no navegador.

---

### 🌓 Modo claro

O modo claro continua sendo o padrão quando nenhuma preferência foi definida.

Ele utiliza uma interface clara, com:

- fundos claros;
- textos escuros;
- maior contraste;
- cards destacados;
- elementos organizados visualmente.

---

### 📱 Interface responsiva

A estrutura continua preparada para diferentes tamanhos de tela.

O sistema pode ser utilizado em:

- Computadores;
- Notebooks;
- Tablets;
- Smartphones.

---

# 🌐 Preparação para GitHub Pages

A versão 3.1 foi organizada para facilitar a publicação como um site estático.

Os caminhos dos arquivos utilizam referências relativas, permitindo que o sistema funcione dentro de um repositório do GitHub.

Exemplo:

```text
https://usuario.github.io/BiblioLab/
```

A estrutura principal é:

```text
BiblioLab/
├── index.html
├── css/
│   └── styles.css
├── js/
│   ├── app.js
│   └── tailwind.config.js
├── database/
│   └── bibliolab.sql
├── api/
├── .github/
│   └── workflows/
│       └── pages.yml
├── .nojekyll
├── .gitignore
└── README.md
```

---

## ⚙️ Deploy automático

O projeto possui um workflow do GitHub Actions localizado em:

```text
.github/workflows/pages.yml
```

Esse arquivo permite que o GitHub publique automaticamente o projeto no GitHub Pages após alterações na branch principal.

### Para publicar:

1. Criar um repositório no GitHub;
2. Enviar os arquivos do BiblioLab;
3. Utilizar a branch `main`;
4. Acessar:

```text
Settings → Pages
```

5. Selecionar **GitHub Actions** como método de publicação;
6. Fazer o primeiro `push`.

Após o processo, o GitHub fornecerá o endereço público do site.

---

# 🗄️ Banco de dados

O projeto possui uma estrutura de banco de dados relacional em:

```text
database/bibliolab.sql
```

O banco foi organizado para separar diferentes tipos de informação.

Entre as estruturas previstas estão:

- Usuários;
- Funções e permissões;
- Categorias de livros;
- Níveis de escolaridade;
- Livros;
- Relação entre livros e níveis escolares;
- Salas e laboratórios;
- Horários;
- Empréstimos;
- Reservas;
- Configurações de acessibilidade;
- Registros de auditoria.

### ⚠️ Importante

O GitHub Pages **não executa bancos MySQL ou PostgreSQL**.

O arquivo SQL faz parte do projeto como estrutura do banco de dados, mas um sistema real precisará de um servidor/backend para executar as operações.

---

# 🔌 API

O BiblioLab possui uma camada preparada para trabalhar com uma API.

A estrutura permite futuramente conectar o sistema a um backend responsável por:

- Usuários;
- Login;
- Livros;
- Reservas;
- Empréstimos;
- Salas;
- Laboratórios;
- Permissões;
- Dados do sistema.

Atualmente, a aplicação possui mecanismos de fallback para permitir a demonstração do frontend sem depender obrigatoriamente de um servidor.

---

# 🔐 Segurança

A versão atual foi estruturada pensando na futura implementação de um backend seguro.

Em uma versão de produção:

- Senhas deverão ser armazenadas utilizando hash seguro;
- Credenciais do banco não devem ficar no frontend;
- Tokens privados não devem ser publicados no GitHub;
- Operações administrativas deverão ser realizadas pelo backend;
- A API deverá utilizar HTTPS;
- O sistema deverá validar permissões no servidor.

### ⚠️ Nunca coloque no GitHub:

```text
.env
senhas
tokens privados
chaves de API privadas
credenciais do banco
```

---

# ♿ Acessibilidade

O BiblioLab possui uma área dedicada à acessibilidade.

Entre os recursos estão:

- Controle de contraste;
- Preferências visuais;
- Modo claro/escuro;
- Redução de animações;
- Estrutura preparada para navegação mais acessível;
- Elementos semânticos;
- Atalhos e navegação mais organizada.

O projeto também considera a preferência:

```text
prefers-reduced-motion
```

para reduzir animações quando essa opção estiver habilitada no sistema do usuário.

---

# 📖 Acervo

O sistema possui uma área específica para gerenciamento e visualização do acervo.

É possível trabalhar com informações como:

- Título;
- Autor;
- ISBN;
- Categoria;
- Escolaridade;
- Disponibilidade;
- Descrição;
- Quantidade de páginas;
- Ano aplicável;
- Capa do livro.

O projeto também possui integração preparada para consulta de informações de livros através de API externa.

---

# 👤 Usuários

O BiblioLab possui estrutura para diferentes tipos de usuários e permissões.

A arquitetura prevê funções como:

- Administrador;
- Funcionários;
- Professores;
- Alunos.

Cada função poderá possuir permissões diferentes quando o backend for implementado.

---

# 📅 Reservas

O sistema foi projetado para permitir o gerenciamento de:

- Reservas de livros;
- Empréstimos;
- Salas;
- Laboratórios;
- Horários de utilização.

Essa estrutura é especialmente importante para escolas que possuem vários turnos e precisam controlar a utilização dos recursos disponíveis.

---

# 📊 Dashboard

A página inicial apresenta informações resumidas do sistema.

Entre os indicadores previstos estão:

- Total de livros;
- Livros disponíveis;
- Empréstimos;
- Usuários;
- Reservas;
- Informações do acervo.

O objetivo é permitir que o usuário visualize rapidamente a situação da biblioteca.

---

# 📝 Changelog

## [3.1.0] — Preparação para GitHub Pages

### ✨ Adicionado

- Estrutura compatível com GitHub Pages;
- Workflow de deploy automático;
- `.nojekyll`;
- `.gitignore`;
- Estrutura reservada para API;
- Metadados adicionais da aplicação;
- Detecção automática do tema do sistema;
- Persistência do modo claro/escuro;
- Sistema de tema aplicado antes da renderização;
- Melhor suporte para `prefers-reduced-motion`.

### 🌙 Modo escuro

- Correção de fundos que permaneciam claros;
- Correção de textos com baixo contraste;
- Correção de bordas;
- Correção de campos de formulário;
- Ajuste de cards;
- Ajuste de elementos coloridos;
- Melhor transição entre os temas.

### 🌐 GitHub Pages

- Caminhos absolutos substituídos por caminhos relativos quando necessário;
- Preparação para hospedagem em subdiretório;
- Configuração de GitHub Actions;
- Documentação de publicação.

### 🗄️ Banco de dados

- Mantida a estrutura SQL relacional;
- Separação entre frontend e banco;
- Preparação para futura API/backend.

---

## [3.0.0] — Reestruturação do projeto

### ✨ Adicionado

- Separação do HTML, CSS e JavaScript;
- Estrutura de banco de dados relacional;
- Área de API do acervo;
- Visualização de informações de livros;
- Exportação de dados do acervo;
- Melhor organização do código;
- Melhorias de acessibilidade;
- Suporte aprimorado ao modo claro/escuro;
- Estrutura preparada para backend.

### 🗂️ Estrutura

O projeto passou a utilizar:

```text
index.html
css/
js/
database/
```

Isso facilita a manutenção e permite que cada parte do sistema seja modificada separadamente.

---

## [2.0.0] — Melhorias do sistema

### 🔐 Segurança

- Melhor organização do sistema de login;
- Estrutura para usuários;
- Organização de permissões;
- Preparação para armazenamento estruturado dos dados.

### 📚 Acervo

- Melhor visualização dos livros;
- Busca por título;
- Busca por autor;
- Busca por ISBN;
- Filtros;
- Informações adicionais dos livros;
- Integração com API de livros.

### 👤 Perfil

- Melhorias na área de usuário;
- Alteração de informações pessoais;
- Organização do perfil;
- Preparação para foto de usuário.

### 🎨 Interface

- Melhorias visuais;
- Dashboard reformulado;
- Melhor organização das abas;
- Modo claro/escuro;
- Melhorias de acessibilidade.

---

# 🛠️ Tecnologias

O projeto utiliza principalmente:

- HTML5;
- CSS3;
- JavaScript;
- Tailwind CSS;
- LocalStorage para dados locais de demonstração;
- Google Books API;
- SQL para estrutura do banco;
- GitHub Pages;
- GitHub Actions.

---

# 📌 Estado atual do projeto

| Recurso | Estado |
|---|---|
| Interface | ✅ Implementado |
| Dashboard | ✅ Implementado |
| Acervo | ✅ Implementado |
| Busca de livros | ✅ Implementado |
| API de livros | 🟡 Preparado |
| Modo claro | ✅ Implementado |
| Modo escuro | ✅ Corrigido |
| Acessibilidade | ✅ Implementado |
| Banco SQL | ✅ Estruturado |
| GitHub Pages | ✅ Preparado |
| Deploy automático | ✅ Preparado |
| Backend | 🟡 Futuro |
| Banco online | 🟡 Futuro |
| Login real | 🟡 Futuro |
| Autenticação segura | 🟡 Futuro |
| Reservas persistentes | 🟡 Futuro |

**Legenda:**

- ✅ Implementado
- 🟡 Em desenvolvimento / preparado
- ❌ Não implementado

---

# 🚧 Próximos passos

As próximas versões poderão incluir:

1. Backend próprio;
2. API REST;
3. Banco PostgreSQL ou MySQL online;
4. Login real;
5. Sistema de permissões;
6. Cadastro de usuários;
7. Cadastro e edição de livros;
8. Sistema real de empréstimos;
9. Sistema real de reservas;
10. Gerenciamento de salas e laboratórios;
11. Painel administrativo;
12. Logs e auditoria;
13. Notificações;
14. Recuperação de senha;
15. Maior proteção dos dados.

---

# 📄 Licença

Projeto desenvolvido para fins educacionais e acadêmicos.

O uso, modificação e distribuição do projeto devem respeitar as condições definidas pelos responsáveis pelo desenvolvimento do BiblioLab.
