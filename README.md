# Sistema de Matrículas Escola Técnica São Lucas

## 1. Descrição Geral
O **Sistema de Matrículas** é um software para gerenciar as atividades acadêmicas de uma escola técnica localizada em Porto Alegre, RS, Brasil. O sistema deve permitir o cadastro e a consulta de informações sobre alunos, disciplinas, turmas e matrículas, além de gerenciar o uso de salas de aula. Ele precisa autenticar usuários com e-mail e senha, garantir que as matrículas respeitem restrições de horário e capacidade, e ter uma interface visualmente consistente com as cores da instituição.

## 2. Contexto
- **Instituição**: Escola São Lucas, com um único campus em Porto Alegre.
- **Curso**: Curso Técnico em Informática.
- **Infraestrutura**: A escola possui 3 salas de aula, cada uma comportando até 20 alunos.
- **Período Acadêmico**: Um semestre por ano (ex.: 2025).
- **Particularidades**:
  - A escola tem cerca de 50 alunos e oferece 5 disciplinas por semestre.
  - Cada aluno pode cursar até 2 disciplinas por semestre.
  - As aulas ocorrem no turno da noite, das 19:00 às 21:00, em dias específicos (Segunda, Terça ou Quarta).
  - Cada disciplina tem uma carga horária de 40 horas por semestre.
  - Alunos e administradores recebem e-mails institucionais no formato nome@saolucas.com.
  - O sistema deve ser acessado por computadores no campus e dispositivos móveis.

## 3. Requisitos Funcionais
- **RF01**: Cadastrar alunos, incluindo nome, CPF, e-mail institucional e senha.
- **RF02**: Autenticar usuários usando e-mail institucional e senha, com registro de cada login (data e hora).
- **RF03**: Cadastrar disciplinas, com um código único e nome.
- **RF04**: Cadastrar turmas, especificando a disciplina, o horário (dia e hora) e a sala onde as aulas ocorrerão.
- **RF05**: Permitir que um aluno se matricule em uma turma, garantindo que:
  - A sala da turma não exceda a capacidade de 20 alunos.
  - O aluno não esteja matriculado em outra turma no mesmo horário.
  - O aluno não exceda o limite de 2 disciplinas por semestre.
- **RF06**: Consultar as turmas em que um aluno está matriculado, mostrando informações sobre as disciplinas e horários.
- **RF07**: Permitir que um administrador (com perfil específico) gerencie cadastros de alunos, disciplinas, turmas e salas.
- **RF08**: Permitir que alunos consultem suas matrículas, mas sem editá-las.

## 4. Requisitos Não Funcionais
- **RNF01**: Desenvolver o sistema em PHP 8.x, com banco de dados MySQL.
- **RNF02**: Criar uma interface responsiva, usando as cores azul-marinho (#003087) para o fundo.
- **RNF03**: Validar:
  - CPF com 11 dígitos, único no sistema.
  - E-mail institucional único, no formato nome@saolucas.com.
  - Senha com no mínimo 6 caracteres, armazenada com criptografia.
- **RNF04**: Proteger contra ataques de SQL Injection usando consultas preparadas.
- **RNF05**: Garantir que consultas simples no sistema respondam em menos de 2 segundos.
- **RNF06**: Registrar logs de autenticação (e-mail, data e hora) para auditoria.

## 5. Premissas
- A escola tem cerca de 50 alunos, 5 disciplinas e 10 turmas por semestre.
- As salas são usadas apenas no turno da noite, em blocos de 2 horas.
- O sistema não gerencia notas, frequência ou pagamentos, apenas cadastros e matrículas.
- Não há integração com sistemas externos.

## 6. Restrições
- A interface deve ser compatível com navegadores Chrome e Firefox.

## 7. Detalhes Adicionais
- **Identidade Visual**: A interface deve usar azul-marinho (#003087) como cor principal.
- **Horários**: Aulas ocorrem apenas às 19:00-21:00, em Segunda, Terça ou Quarta.
- **Segurança**: As senhas devem ser armazenadas de forma segura, e cada login deve ser registrado.
