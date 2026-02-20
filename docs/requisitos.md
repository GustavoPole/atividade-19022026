# Documento de Requisitos

Projeto: Sistema de Gerenciamento de Cursos Online  
Versão: 1.0  
Data: 19/02/2026  

---

## 1. Requisitos Funcionais (RF)

### RF01 - Cadastro de Usuário
O sistema deve permitir o cadastro de novos usuários (alunos e administradores).

**Critérios de Aceitação:**
- O usuário deve informar nome, email e senha.
- O sistema não deve permitir email duplicado.
- Após cadastro válido, o usuário deve ser armazenado no banco de dados.

---

### RF02 - Login de Usuário
O sistema deve permitir que usuários cadastrados realizem login.

**Critérios de Aceitação:**
- O sistema deve validar email e senha.
- Em caso de erro, deve exibir mensagem apropriada.
- Em caso de sucesso, deve redirecionar para a área do usuário.

---

### RF03 - Cadastro de Curso
O administrador deve poder cadastrar novos cursos na plataforma.

**Critérios de Aceitação:**
- O curso deve possuir título, descrição e carga horária.
- Apenas usuários com perfil administrador podem acessar essa funcionalidade.
- O curso deve ser salvo no banco de dados.

---

### RF04 - Matrícula em Curso
O aluno deve poder se matricular em um curso disponível.

**Critérios de Aceitação:**
- O aluno deve estar autenticado.
- O sistema deve registrar a matrícula no banco de dados.
- O aluno não pode se matricular duas vezes no mesmo curso.

---

## 2. Requisitos Não Funcionais (RNF)

### RNF01 - Segurança
O sistema deve armazenar senhas de forma criptografada.

**Critérios de Verificação:**
- As senhas devem estar armazenadas utilizando hash (ex: bcrypt).
- Não deve ser possível visualizar a senha original no banco.

---

### RNF02 - Desempenho
O sistema deve responder às requisições em até 2 segundos.

**Critérios de Verificação:**
- Testes de desempenho devem comprovar tempo médio de resposta ≤ 2 segundos para até 100 usuários simultâneos.

---

## 3. Regras de Negócio (RN)

### RN01 - Controle de Perfil
Somente usuários com perfil "Administrador" podem cadastrar ou editar cursos.

**Critério de Verificação:**
- Testes devem impedir acesso à funcionalidade para usuários comuns.

---

### RN02 - Cancelamento de Matrícula
O aluno pode cancelar matrícula somente até 7 dias após a inscrição.

**Critério de Verificação:**
- O sistema deve validar a data da matrícula.
- Após 7 dias, o cancelamento não deve ser permitido.
