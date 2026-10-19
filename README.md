# BIBLIOLAB 2.0

Sistema escolar de biblioteca e laboratório de informática, com frontend responsivo e backend real em Node.js/Express + SQLite.

## Recursos
- Login obrigatório e sessão via cookie HttpOnly.
- Senhas com hash bcrypt.
- Banco SQLite organizado por usuários, perfis, escolaridades, categorias, livros, empréstimos, reservas e logs.
- Controle de acesso por perfil (administrador, professor e aluno).
- Catálogo com busca, filtros e painel de detalhes.
- Empréstimos e devoluções.
- Reservas do laboratório.
- Perfil com foto por URL, dados pessoais e troca de senha.
- Dashboard renovado.
- Tema claro/escuro.
- Área de acessibilidade.
- Logs administrativos.
- Helmet, rate limit e validações básicas.

## Requisitos
Node.js 18+ (recomendado Node 20 LTS ou superior).

## Instalação
```bash
npm install
npm start
```

Abra: http://localhost:3000

## Acesso inicial
- E-mail: admin@escola.local
- Senha: admin123

Para produção, altere a senha inicial e defina `ADMIN_PASSWORD` antes da primeira execução. O banco é criado automaticamente em `data/bibliolab.db`.

## Observação sobre livros
A versão 2.0 deixa o acervo preparado para receber dados da Google Books API. O banco é a fonte principal da aplicação, evitando depender de uma consulta externa a cada abertura da biblioteca. Um próximo passo pode adicionar um importador administrativo da API.
