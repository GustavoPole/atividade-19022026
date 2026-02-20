# Documento de Requisitos

Projeto: Sistema de Gerenciamento de Cursos Online  
Versão: 1.0  
Data: 19/02/2026  

---

# 1. Requisitos Funcionais (RF)

---

## RF01 – Cadastro de Usuário

**Descrição:**  
O sistema deve permitir o cadastro de novos usuários com perfil Aluno ou Administrador.

**Entradas:**
- Nome completo
- Email
- Senha
- Tipo de usuário (Aluno ou Administrador)

**Processamento:**
- Validar campos obrigatórios.
- Verificar se o email já está cadastrado.
- Criptografar a senha antes de armazenar.

**Saída:**
- Confirmação de cadastro realizado com sucesso.
- Mensagem de erro caso haja inconsistências.

**Critérios de Aceitação:**
- O sistema não permite cadastro com email já existente.
- A senha deve ser armazenada criptografada.
- Todos os campos obrigatórios devem ser validados.

**Critérios de Verificação/Teste:**
- Teste com email duplicado deve retornar erro.
- Teste com campos vazios deve impedir cadastro.
- Verificação no banco deve confirmar senha criptografada.

---

## RF02 – Autenticação de Usuário (Login)

**Descrição:**  
O sistema deve permitir que usuários cadastrados realizem autenticação utilizando email e senha.

**Entradas:**
- Email
- Senha

**Processamento:**
- Validar credenciais.
- Comparar senha informada com hash armazenado.

**Saída:**
- Redirecionamento para dashboard do usuário.
- Mensagem de erro em caso de credenciais inválidas.

**Critérios de Aceitação:**
- Apenas usuários cadastrados podem acessar o sistema.
- O sistema deve bloquear acesso com senha incorreta.
- Deve ser criada sessão/token após login válido.

**Critérios de Verificação/Teste:**
- Login com dados corretos deve permitir acesso.
- Login com senha incorreta deve retornar erro.
- Usuário inexistente não deve acessar o sistema.

---

## RF03 – Cadastro de Curso

**Descrição:**  
O sistema deve permitir que usuários com perfil Administrador cadastrem novos cursos.

**Entradas:**
- Título do curso
- Descrição
- Carga horária
- Valor (opcional)

**Processamento:**
- Validar permissões do usuário.
- Validar campos obrigatórios.
- Registrar curso no banco de dados.

**Saída:**
- Confirmação de curso cadastrado.
- Mensagem de erro caso usuário não tenha permissão.

**Critérios de Aceitação:**
- Apenas Administradores podem cadastrar cursos.
- O curso deve ser salvo corretamente no banco.
- Campos obrigatórios devem ser validados.

**Critérios de Verificação/Teste:**
- Usuário Aluno não pode acessar funcionalidade.
- Após cadastro, o curso deve aparecer na listagem.
- Cadastro com campo obrigatório vazio deve falhar.

---

## RF04 – Matrícula em Curso

**Descrição:**  
O sistema deve permitir que usuários com perfil Aluno se matriculem em cursos disponíveis.

**Entradas:**
- Identificador do curso
- Usuário autenticado

**Processamento:**
- Verificar se o usuário está logado.
- Verificar se já existe matrícula ativa para o curso.
- Registrar matrícula no banco.

**Saída:**
- Confirmação de matrícula realizada.
- Mensagem de erro em caso de matrícula duplicada.

**Critérios de Aceitação:**
- O aluno deve estar autenticado.
- O aluno não pode se matricular duas vezes no mesmo curso.
- A matrícula deve ser registrada corretamente no banco.

**Critérios de Verificação/Teste:**
- Matrícula duplicada deve ser bloqueada.
- Usuário não autenticado não pode se matricular.
- Registro deve constar corretamente na tabela de matrículas.
