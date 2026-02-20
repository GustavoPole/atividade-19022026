---

# 3. Regras de Negócio (RN)

---

## RN01 – Controle de Permissões por Perfil

**Descrição:**  
Somente usuários com perfil "Administrador" podem cadastrar, editar ou excluir cursos.

**Regra:**
- Usuários do tipo "Aluno" possuem apenas permissão de visualização e matrícula.

**Critérios de Verificação:**
- Teste de acesso com usuário Aluno deve retornar erro 403 (Acesso Negado).
- Teste com Administrador deve permitir acesso completo às funcionalidades de gestão de cursos.

---

## RN02 – Restrição de Matrícula Duplicada

**Descrição:**  
Um aluno não pode possuir mais de uma matrícula ativa no mesmo curso.

**Regra:**
- O sistema deve verificar previamente a existência de matrícula antes de registrar uma nova.

**Critérios de Verificação:**
- Tentativa de matrícula duplicada deve retornar mensagem de erro.
- O banco de dados deve possuir restrição lógica ou constraint que impeça duplicidade.
