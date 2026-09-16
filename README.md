# Apollo BI — Databricks

Pipeline de BI do projeto Apollo (2º ano), rodando no Databricks, responsável
por calcular as métricas do sistema a partir dos dados operacionais do Neon
e alimentar os dashboards por filial.

## Como rodar

1. Configurar o secret scope `apollo` no Databricks (usuário e senha do Neon)
2. Rodar `apollo_connection_neon_core` primeiro

### Configuração do Git para cada desenvolvedor - Passo a passo

A conexão do Databricks com este repositório é presa à conta individual de
cada pessoa, não ao workspace como um todo. Isso significa que **cada
desenvolvedor precisa configurar o próprio token do GitHub no seu usuário do
Databricks** antes de conseguir commitar ou dar push — não é possível
compartilhar um token entre o grupo.

1. **Confirme que você tem acesso de escrita** ao repositório
   `ApolloOficial/Apollo-Databricks-BI` como membro da organização no GitHub.

2. **Gere um token fine-grained no GitHub:**
   - GitHub → seu avatar → **Settings → Developer settings → Personal access
     tokens → Fine-grained tokens → Generate new token**
   - Dê um nome ao token (ex.: `databricks-apollo-bi-<seu-nome>`)
   - Defina uma validade (recomendado: 60–90 dias)
   - Em **Resource owner**, selecione `ApolloOficial`
   - Em **Repository access**, escolha **"Only select repositories"** e
     selecione `Apollo-Databricks-BI`
   - Em **Permissions → Repository permissions**, clique em
     **"+ Add permissions"**, escolha **Contents** e defina como
     **"Read and write"**
   - Clique em **"Generate token and request access"** e copie o token
     gerado (só aparece uma vez)
   - Dependendo da configuração da organização, pode ser necessário um
     admin aprovar o acesso do token antes dele funcionar

3. **Conecte o token no Databricks:**
   - No Databricks, clique no seu usuário (canto superior direito) →
     **Settings**
   - Procure a seção **Linked accounts** (ou "Git integration")
   - Em **Git provider**, selecione **GitHub**
   - Preencha seu usuário do GitHub e cole o token gerado no passo anterior
   - Salve

4. **Acesse a Git folder compartilhada:**
   - No Workspace, vá até `Shared/Apollo/Apollo-Databricks-BI`
   - Se ela ainda não aparecer pra você, confirme que tem acesso a essa
     pasta, ou peça pra alguém com permissão de admin liberar

5. **Teste fazendo uma alteração pequena** (como editar um comentário) e
   confira se o botão de commit/push aparece e funciona com o seu próprio
   login.
