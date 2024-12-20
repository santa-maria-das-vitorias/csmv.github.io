## Definição de entidade

**Quem somos:** A Associação Civil Santa Maria das Vitórias tem por fim promover a evangelização através da divulgação da liturgia romana tradicional, bem como apresentar os valores da cultura católica publicando resenhas, seletas e crônicas que focalizem temas filosóficos, teológicos, históricos e literários. Nossa Associação construiu uma capela em estilo barroco dedicada a Santa Maria das Vitórias onde se celebra como rito exclusivo a missa romana tradicional, também conhecida como missa de São Pio V ou missa tridentina.

Nossa associação pretende construir também um centro de cultura católica anexo à capela, onde se cultive a filosofia tomista bem como outras correntes do pensamento católico contra-revolucionário, conforme o magistério perene da Igreja.

**Finalidades**: A Associação Civil Santa Maria das Vitórias tem por finalidade:
- Celebrar a Santa Missa no rito tridentino, bem como os demais sacramentos católicos.
- Acolher qualquer sacerdote católico que, em caráter perpétuo, terá o direito de celebrar o Santo Sacrifício da Missa e do Ofício Divino na Capela Santa Maria das Vitórias, segundo o rito tridentino.
- Ensinar o Catecismo e a preparar para os sacramentos.
- Promover a assistência social a famílias carentes e outras práticas de caridade.
- Administrar uma escola de ensino fundamental precedida de classes de alfabetização para os filhos dos associados e um Centro de Cultivo do Pensamento Aristotélico-Tomista.
- Promover orações e outras celebrações pela santificação dos bispos e prelados de toda a hierarquia católica e suas respectivas Cúrias para que governem o povo de Deus com prudência e sabedoria, inspirados sempre pela graça do Divino Espírito Santo e guiados pelas mãos do Imaculado Coração de Maria, Mãe de Deus e dos homens.

**Padroeiros:**
- Nossa Senhora das Vitórias
- Beato José de Anchieta

## Definição do projeto
**Ponto de partida:** Recentemente o site da Capela foi atacado por hackers, felizmente não foi perdido nenhum dado devido a um backup no [Wayback Machine](https://web.archive.org/web/20220705213743/http://santamariadasvitorias.org/). Entretanto para evitar futuros incidentes como esse, não basta apenas restaurar o que havia antes, **por isso elaboramos a seguinte proposta:**

## **Proposta de desenvolvimento**
Visando principalmente estabilidade e segurança, propomos uma arquitetura API Gateway com Microserviços que possuirá os seguintes aspectos:
1. Multicamadas (front-end/back-end, API, cache, database)
2. Microserviços independentes
3. Banco de dados segmentado e independente
4. Criptografia de ponta a ponta
5. Backup automático de dados

**API Gateway com Microserviços**:
    - **API Gateway**: Gerencia o tráfego entre os clientes e os microserviços. Implementa autenticação, autorização e monitoramento.
    - **Microserviços Independentes**: Cada serviço é projetado para atender a uma funcionalidade específica (blog, livraria, cursos, site institucional) de forma independente, com APIs exclusivas.
 
**Multicamadas**:
    - **Frontend**: Utiliza tecnologias modernas como Rust/Yew (para desempenho com WebAssembly) e Vue/Nuxt.js (para interatividade e usabilidade).
    - **Backend**: Implementado com WebAssembly e gRPC, garante comunicação rápida e segura entre serviços.
    - **Cache**: Reduz a latência ao armazenar dados frequentemente acessados.
    - **Banco de Dados**: Segmentado e isolado para cada microserviço, utilizando AWS DynamoDB para escalabilidade e confiabilidade.

**Criptografia**
    - Criptografia ponta a ponta, tanto na comunicação quanto no armazenamento.

**Backup Automatizado**:
    - Implementação de backups regulares e integrados com sistemas externos (como AWS ou Google Cloud) para recuperação de dados.

**Componentes do Sistema**:
    - **Site Institucional**: Estático, com tecnologia Next.js para alta performance.
    - **Blog (CMS)**: Endereço independente e criptografado para a gestão de conteúdo.
    - **Plataforma de Cursos (LMS)**: Endereço separado para gerenciamento de alunos, cursos e materiais.
    - **Livraria**: Gestão de acervos físicos e digitais, integrando sistemas de pagamento e distribuição.

Para mais informações, vide [[arquitetura.canvas|Arquitetura]].