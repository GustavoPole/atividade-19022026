---

# 2. Requisitos Não Funcionais (RNF)

---

## RNF01 – Segurança da Informação

**Descrição:**  
O sistema deve garantir a segurança das informações dos usuários.

**Especificações:**
- As senhas devem ser armazenadas utilizando algoritmo de hash seguro (ex: bcrypt).
- O sistema deve utilizar autenticação baseada em sessão ou token (JWT).
- Dados sensíveis não devem ser expostos em respostas da API.

**Critérios de Verificação:**
- Verificação no banco confirma que senhas não estão em texto puro.
- Testes de autenticação validam geração correta de token/sessão.
- Endpoints protegidos exigem autenticação válida.

---

## RNF02 – Desempenho

**Descrição:**  
O sistema deve apresentar tempo de resposta adequado para múltiplos usuários simultâneos.

**Especificações:**
- O tempo médio de resposta deve ser inferior a 2 segundos.
- O sistema deve suportar ao menos 100 usuários simultâneos sem falhas.

**Critérios de Verificação:**
- Testes de carga demonstram tempo médio ≤ 2 segundos.
- Não devem ocorrer erros 500 sob carga moderada.
- O banco de dados deve responder sem travamentos.
