# **Desafio - Desenvolvedor(a) Fullstack Pleno**
Bem-vindo(a)! Este desafio foi criado para avaliar suas habilidades técnicas como desenvolvedor(a) Fullstack Pleno. Queremos ver como você aplica boas práticas, organiza seu código e resolve problemas reais com criatividade e eficiência.

---

## **Instruções**
- Faça um fork deste repositório.
- Utilize as tecnologias informadas na proposta do desafio (ou os diferenciais mencionados).
- Crie um passo a passo detalhado no README explicando como rodar sua aplicação.
- Após concluir, submeta um pull request e informe seu e-mail de contato no comentário do PR. Aguarde nossa avaliação!

---

## **Proposta do Desafio**

Desenvolva um **Sistema de Atendimento e Gerenciamento de Chamados** com autenticação, controle de permissões, e funcionalidades voltadas para um administrador e usuários comuns.

---

### **Requisitos do Sistema**
#### **Back-end**
Desenvolver uma **API RESTful** utilizando **Node.js** e **TypeScript** que atenda aos seguintes requisitos:

1. **Autenticação**
   - Todas as rotas devem ser protegidas com **JWT**, exceto `/register` e `/login`.
   - Suporte a dois tipos de usuário:
     - **Administrador**: pode gerenciar todos os chamados (criar, visualizar, editar, responder e excluir).
     - **Usuário comum**: pode gerenciar apenas seus próprios chamados (criar, visualizar, editar e excluir).

2. **Rotas:**
   - **Usuários:**
     - `/register` - [POST] - Cadastro de usuários. Apenas um administrador pode criar outros administradores.
     - `/login` - [POST] - Autenticação de usuários, retornando um token JWT.

   - **Chamados:**
     - `/tickets` - [POST] - Criação de chamados com título, descrição, prioridade e status inicial (ex.: "aberto").
     - `/tickets` - [GET] - Listar chamados:
       - Usuário comum: vê apenas seus próprios chamados.
       - Administrador: vê todos os chamados registrados.
     - `/tickets/{id}` - [GET] - Visualizar detalhes de um chamado, incluindo histórico de atualizações.
     - `/tickets/{id}` - [PUT] - Editar detalhes de um chamado:
       - Usuário comum: apenas seus próprios chamados.
       - Administrador: qualquer chamado.
     - `/tickets/{id}/status` - [PATCH] - Atualizar o status de um chamado (ex.: "em andamento", "concluído").
     - `/tickets/{id}` - [DELETE] - Excluir chamados (somente administradores).

3. **Funcionalidades adicionais no backend:**
   - Histórico de atualizações nos chamados (quem editou e o que foi alterado).
   - Integração para envio de **notificações por email** (confirmação de conta e atualizações nos chamados). Utilize **Mailtrap** para simulações.
   - Simulação de **notificação por WhatsApp**:
     - Registrar notificações em um arquivo `whatsapp.log` no formato:
       ```json
       {
         "phone": "5521999999999",
         "message": "Seu ticket foi atualizado! Acesse agora mesmo <url>"
       }
       ```

---

### **Front-end**
Desenvolver uma aplicação web em **React.js** com **TypeScript** para interagir com a API criada, implementando as seguintes histórias de usuário:

#### **Histórias de Usuário**
1. Eu, como **usuário comum**, desejo:
   - Me cadastrar no sistema.
   - Realizar login e acessar meu painel de chamados.
   - Registrar um chamado com título, descrição, prioridade e status inicial.
   - Visualizar uma lista dos meus chamados com opções de filtro e ordenação.
   - Editar meus chamados, atualizando título, descrição ou prioridade.
   - Atualizar o status de meus chamados.
   - Excluir um chamado.
   - Receber notificações visíveis sobre atualizações em meus chamados.

2. Eu, como **administrador**, desejo:
   - Visualizar uma lista de todos os chamados.
   - Filtrar chamados por status, prioridade ou data.
   - Editar detalhes de qualquer chamado.
   - Adicionar respostas aos chamados, visíveis no histórico do chamado.
   - Atualizar o status de qualquer chamado.
   - Excluir chamados do sistema.

#### **Requisitos Técnicos**
1. **Tecnologias e Ferramentas**
   - **React.js** com **TypeScript**.
   - Gerenciamento de estado com **Context API** ou **Redux**.
   - Estilização com **CSS Modules**, **Styled Components**, ou **Tailwind CSS**.
   - **Axios** ou **Fetch API** para chamadas à API.

2. **Interface**
   - **Responsiva** (mobile-first design).
   - Exibição clara do status dos chamados com distinção visual (ex.: cores diferentes para "aberto", "em andamento", "concluído").
   - Feedback visual ao salvar, editar ou excluir chamados.

3. **Roteamento e Proteção**
   - Utilizar **React Router** para navegação.
   - Proteger rotas para garantir acesso apenas a usuários autenticados e permissões de administrador.

4. **Estrutura Modular**
   - Componentes reutilizáveis, como:
     - **Botões**, com estilos configuráveis (primário, secundário).
     - **Inputs**, com validação dinâmica.
     - **Cards**, para exibir detalhes dos chamados.
     - **Modais**, para confirmações de ações.

---

### **Diferenciais**
- **Notificações em Tempo Real:** 
  - Implementar **WebSockets** para atualizações instantâneas dos chamados.
- **Testes Automatizados:** 
  - Escrever testes unitários para o backend.
- **Deploy Completo:**
  - Backend em **Railway**, **AWS**, ou similar.
  - Frontend em **Vercel** ou equivalente.

---

### **Critérios de Avaliação**
1. **Organização do Código:**
   - Arquitetura clara, com separação de responsabilidades.
   - Modularização e reutilização de componentes.
2. **Qualidade Técnica:**
   - Uso de boas práticas e clareza no código.
3. **Funcionalidade:**
   - Implementação dos requisitos obrigatórios e diferenciais.
4. **Documentação:**
   - README explicativo com:
     - Passo a passo para rodar o projeto.
     - Decisões técnicas e justificativas.
     - Melhorias futuras sugeridas.

---

### **Entrega**
- Crie um repositório público no GitHub e compartilhe o link no pull request.
- Inclua um README detalhado com:
  - Instruções de instalação e execução.
  - Explicação sobre decisões técnicas.
  - Melhorias que poderiam ser implementadas.

📅 **Prazo de Entrega:** 10 dias úteis.  
🎯 **Boa sorte! Estamos ansiosos para avaliar sua solução!**
