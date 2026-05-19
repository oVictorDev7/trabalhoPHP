============================================
  TaskFlow — Gerenciador de Tarefas Colaborativo
  Trabalho PHP — Disciplina de Desenvolvimento de Sistemas
  Professor: João Paulo Nunes da Silva
============================================

INTEGRANTES DO GRUPO:
  Enzo F F Chemin          - RGM: 33402621
  Felipe Paulista Silveira - RGM: 43389988
  Leonardo Valente Montes  - RGM: 42979846
  Hygor Daniel Fieszt      - RGM: 41984561
  Victor Gonçalves         - RGM: 38094649

REQUISITOS:
  - PHP 8.1 ou superior
  - MySQL 5.7+ ou MariaDB 10+
  - Servidor web (Apache via XAMPP/WAMP)
  - Extensões PHP: pdo, pdo_mysql, session (padrão no XAMPP)

COMO RODAR LOCALMENTE (XAMPP):
  1. Coloque a pasta "gerenciador_tarefas" dentro de htdocs/
  2. Abra o phpMyAdmin: http://localhost/phpmyadmin
  3. Crie o banco executando o arquivo banco.sql:
       - Clique em "Novo" e crie o banco "taskflow"  (ou use a aba SQL e cole o conteúdo do banco.sql)
  4. Abra dal/Conn.php e confirme as credenciais:
       $host     = "localhost"
       $dbname   = "taskflow"
       $user     = "root"
       $password = ""       ← senha padrão do XAMPP é vazia
  5. Acesse: http://localhost/gerenciador_tarefas/index.php

ESTRUTURA DO PROJETO:
  index.php          → Ponto de entrada e roteador principal
  banco.sql          → Script de criação do banco de dados
  Autoload.php       → Autoloader de classes (PSR-4)
  assets/
    style.css        → Estilos do sistema
  model/
    Usuario.php      → Modelo de Usuário (POO)
    Tarefa.php       → Modelo de Tarefa  (POO)
  dal/
    Conn.php         → Conexão PDO com MySQL (Singleton)
    UsuarioDao.php   → Acesso a dados de usuários via PDO
    TarefaDao.php    → Acesso a dados de tarefas via PDO
  util/
    Functions.php    → Funções utilitárias (sanitização, CSRF, etc.)
  view/
    login.php        → Tela de login
    cadastro.php     → Tela de cadastro
    home.php         → Dashboard com estatísticas
    listar.php       → Listagem de tarefas com filtros GET
    form_tarefa.php  → Criar / Editar tarefa
    detalhe.php      → Detalhe, comentários e histórico
    404.php          → Página não encontrada

FUNCIONALIDADES IMPLEMENTADAS:
  [x] Cadastro de usuários com senha criptografada
  [x] Login / Logout com sessão PHP
  [x] Cookie "lembrar de mim" (30 dias)
  [x] Proteção CSRF em todos os formulários
  [x] Criar tarefa com título, descrição, prazo e responsável
  [x] Listar tarefas com filtros por responsável, status e data (GET)
  [x] Atualizar status (somente criador ou responsável)
  [x] Comentários em tarefas
  [x] Histórico de alterações registrado no banco
  [x] Layout responsivo com CSS próprio
  [x] HTML semântico
  [x] Banco de dados MySQL com PDO
  [x] Sem bibliotecas externas
