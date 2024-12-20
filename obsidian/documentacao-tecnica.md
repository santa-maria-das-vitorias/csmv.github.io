# Documentação Técnica
## Introdução
### Objetivos do Sistema
O sistema visa oferecer uma solução robusta, escalável e segura para gerenciar os serviços da Associação Civil Santa Maria das Vitórias. Isso inclui o site institucional, blog, plataforma de cursos e livraria, alinhando-se aos objetivos da Associação de promover a evangelização e a cultura católica.

### Benefícios da Arquitetura Proposta
- **Estabilidade:** Minimiza falhas ao segmentar funcionalidades em microserviços independentes.
- **Segurança:** Criptografia ponta a ponta e monitoramento ativo garantem proteção contra ataques.
- **Escalabilidade:** Componentes modulares permitem crescimento sem reestruturar todo o sistema.
- **Backup Automatizado:** Reduz risco de perda de dados com backups regulares e integrados.
- **Alta Performance:** Uso de tecnologias modernas para front-end e back-end proporciona carregamento rápido e comunicação eficiente.

## Descrição da Arquitetura
### Visão Geral do API Gateway e Microserviços
- **API Gateway:** Atua como um ponto único de entrada, gerenciando autenticação, autorização, balanceamento de carga e roteamento de requisições para os microserviços.
- **Microserviços Independentes:** Cada microserviço atende a uma funcionalidade específica (blog, livraria, cursos, site institucional e seus respectivos "admins") e opera de forma autônoma, facilitando a manutenção e a escalabilidade.

### Justificativa para a Escolha das Tecnologias
- **Frontend:** Uso de Rust/Yew e Vue/Nuxt.js para garantir interatividade e alto desempenho com suporte a WebAssembly.
- **Backend:** Implementação com WebAssembly e gRPC para comunicação rápida e segura entre microserviços.
- **Cache:** Integração com sistemas como Redis para reduzir latência.
- **Banco de Dados:** Segmentado e isolado por microserviço, utilizando AWS DynamoDB por sua escalabilidade e confiabilidade.
- **Criptografia:** Aplicada em toda a comunicação e armazenamento para garantir a privacidade dos dados.

## Detalhamento por Serviço
### Especificação Funcional e Técnica de Cada Microserviço
1. **Site Institucional:**
    - **Funcionalidade:** Apresentar informações sobre a Associação e sua missão e ser o "root" que liga os microserviços.
2. **Blog (CMS):**
    - **Funcionalidade:** Gerenciar resenhas, seletas e crônicas.
3. **Plataforma de Cursos (LMS):**
    - **Funcionalidade:** Gerenciar alunos, cursos e materiais didáticos.
4. **Livraria:**
    - **Funcionalidade:** Gerenciar acervos físicos e digitais, incluindo vendas e distribuição.

### Fluxos de Dados e Interações entre os Serviços
- Comunicação entre os microserviços via gRPC.
- Banco de dados segmentado para evitar dependências cruzadas.
- Cache compartilhado para dados frequentemente acessados.

## Segurança
### Políticas de Autenticação e Autorização
- **Autenticação:** OAuth 2.0 para acesso aos serviços e TFA para acesso a Admins.
- **Autorização:** Controles baseados em papéis (RBAC) para limitar acessos.

## Backup e Recuperação
### Frequência e Estratégia de Backups
- Backups semanais automáticos para bancos de dados e armazenamento de arquivos.
- Integração com sistemas de nuvem como AWS S3 e Google Cloud Storage.