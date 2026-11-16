
Core Box - Grupo 01
Repositório utilizado para organizar os artefatos, evidências, relatórios e entregáveis produzidos pelo Grupo 01 durante o desafio Core Box.

O trabalho foi desenvolvido ao longo de três dias, passando pela modelagem de ameaças, implementação da esteira DevSecOps e realização de testes de segurança no BoxGPT e no fluxo de autenticação SSO/JWT.

Visão geral do desafio
Dia	Tema	Objetivo
Dia 01	Threat Modeling	Identificar ativos, fluxos, fronteiras de confiança e ameaças
Dia 02	DevSecOps	Implementar a esteira de segurança, executar testes e registrar correções
Dia 03	BoxGPT e SSO/JWT	Validar controles de autorização, autenticação, sessão e proteção de dados
Dia 01 - Threat Modeling
No primeiro dia, o grupo realizou a modelagem de ameaças do Core Box, identificando os principais ativos, componentes, fluxos de dados e fronteiras de confiança da solução.

Principais atividades
Construção e análise do DFD;
Identificação dos ativos críticos;
Aplicação da metodologia STRIDE;
Levantamento de ameaças e riscos;
Análise de UX Security;
Definição inicial de controles e recomendações;
Organização do backlog de segurança.
Principais riscos avaliados
BOLA/IDOR;
Enumeração de usuários e CPF;
Exposição de dados pessoais e financeiros;
Falhas de autorização;
Recuperação de conta insegura;
Exposição de informações em logs e respostas.
📁 Documentação: dia01/

Dia 02 - DevSecOps
No segundo dia, o grupo implementou e executou a esteira DevSecOps do Core Box, integrando verificações de segurança ao ciclo de desenvolvimento.

A esteira foi estruturada com 8 etapas, incluindo análise de código, verificação de segredos, testes automatizados, análise de dependências, container scanning, DAST e deploy.

Ferramentas e verificações
Gitleaks: identificação de segredos;
Semgrep: análise estática de segurança;
Trivy FS: análise de dependências e arquivos;
Trivy Image: análise da imagem do container;
Pytest: execução dos testes e abuse cases;
OWASP ZAP: análise dinâmica da aplicação;
Docker: construção e verificação da imagem;
GitHub Actions: automação da esteira.
Correções realizadas
TM-03: correção da falha BOLA relacionada à conta de origem no Pix;
TM-23: redução da enumeração de usuários por mensagens e códigos de resposta;
Inclusão da etapa de deploy;
Registro dos riscos residuais e das exceções identificadas.
A execução final contemplou as 8 etapas previstas.

📁 Documentação: dia02/

Dia 03 - BoxGPT e SSO/JWT
No terceiro dia, o grupo aprofundou os testes de segurança no BoxGPT e no fluxo de autenticação SSO/JWT.

As atividades avaliaram a autorização das ferramentas utilizadas pelo agente, o isolamento entre usuários, a proteção do histórico de conversas e a validação dos tokens JWT.

Testes realizados no BoxGPT
Consulta de dados de terceiros;
Autorização da ferramenta consultar_cliente;
BOLA/IDOR no histórico de conversas;
Segregação de contexto entre usuários;
Exposição do modo debug e telemetria;
Tratamento de dados pessoais e financeiros.
Testes realizados em SSO/JWT
Inspeção de tokens JWT;
Token com algoritmo none;
Token com privilégios administrativos;
Token expirado;
Validação de issuer e audience;
Verificação de nonce e PKCE;
Teste do endpoint /sso/callback;
Análise da criação de sessão e emissão de cookie.
Principais achados
Consulta indevida de informações de terceiros;
BOLA/IDOR no histórico de conversas;
Possível mistura de contexto entre usuários;
Exposição de informações internas pelo modo debug;
Callback criando sessão após o envio de token inválido;
Ausência de validação adequada de issuer e audience;
Ausência de nonce e PKCE;
Excesso de dados sensíveis dentro do JWT;
Tempo de expiração elevado para o token.
Entregáveis
Relatório consolidado do Dia 03;
Arquivo achados-dia03.csv;
Evidências dos testes do BoxGPT;
Evidências dos testes de SSO/JWT;
Prints, resultados e registros técnicos.
📁 Documentação: dia03/

Principais resultados
Ao longo dos três dias, o grupo conseguiu:

Modelar as principais ameaças do Core Box;
Relacionar ameaças aos componentes e fluxos da aplicação;
Implementar uma esteira DevSecOps com 8 etapas;
Executar scanners e testes de segurança;
Corrigir falhas relacionadas a BOLA e enumeração;
Identificar riscos no BoxGPT e nas APIs associadas;
Avaliar tokens e o fluxo de autenticação SSO/JWT;
Registrar os achados, evidências e recomendações;
Organizar os artefatos para garantir rastreabilidade.
Estrutura do repositório
core-box-grupo/
├── .github/
│   └── workflows/
├── core-box/
├── dia01/
│   ├── documentação
│   ├── DFD
│   └── Threat Modeling
├── dia02/
│   ├── relatório
│   ├── esteira DevSecOps
│   └── evidências
├── dia03/
│   ├── README.md
│   ├── RELATORIO-DIA03-BOXGPT-CONSOLIDADO.pdf
│   ├── achados-dia03.csv
│   └── evidencias/
└── README.md
