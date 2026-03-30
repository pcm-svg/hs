💧 HydroSystem — Formulário de Abertura de Chamado Técnico
Formulário web para abertura de chamados de assistência técnica, hospedado via GitHub Pages.  
Integração direta com a API do Monday.com — os chamados são criados automaticamente como subitens no board de atendimento.
---
🚀 Acesso
O formulário está disponível em:
```
https://pcm-svg.github.io/hs/
```
---
✅ Funcionalidades
Busca e seleção de condomínio/cliente com autocomplete (busca no board do Monday)
Seleção de tipo de equipamento por chips interativos (múltipla escolha)
Registro de solicitante, contato, endereço e CNPJ (com máscara automática)
Descrição detalhada do problema
Anexo de arquivos (fotos, PDFs, documentos — até 10 arquivos)
Criação automática do subitem no Monday.com com todos os dados preenchidos
Adição de update/comentário no subitem com o resumo do chamado
Upload dos arquivos diretamente para o item no Monday
Feedback visual em tempo real (toasts, spinner, validação inline)
---
🛠️ Tecnologias utilizadas
Tecnologia	Uso
HTML / CSS / JavaScript puro	Interface do formulário (sem dependências externas)
GitHub Pages	Hospedagem estática gratuita
Monday.com API v2 (GraphQL)	Criação de subitens, updates e upload de arquivos
Google Fonts (DM Sans + DM Serif Display)	Tipografia
---
⚙️ Configuração da API Monday.com
O formulário possui um painel de configuração recolhível no topo da página com dois campos:
Campo	Descrição
API Token	Token de acesso pessoal do Monday (`Perfil → Developers → My Access Tokens`)
Board ID	ID do board de Assistência Técnica (padrão: `18404669586`)
> ⚠️ As configurações ficam salvas apenas na sessão do navegador.  
> Para uso fixo, edite o `index.html` e defina as constantes `API_TOKEN` e `BOARD_ID` diretamente no script.
---
📋 Campos do formulário
Bloco 01 — Identificação
Condomínio / Cliente (busca com autocomplete no Monday) `*`
Nome do Solicitante `*`
Contato (telefone) `*`
Endereço
CNPJ (com máscara automática)
Bloco 02 — Equipamento
Tipo de equipamento (chips de seleção múltipla) `*`
Sistema de Recalque, Pressurização SHP, Pressurização Direta, Pressurização Cobertura, Pressurização de Obra, ETE, Grupo Gerador, Elevatória Drenagem, Elevatória Pluvial, Sistema VCN, Outro
Bloco 03 — Descrição do Problema `*`
Bloco 04 — Fotos e Documentos (opcional)
Imagens (JPG, PNG), PDF, Word — até 10 arquivos
`*` Campo obrigatório
---
🔄 Fluxo de envio
```
Cliente preenche o formulário
        ↓
Busca o item pai (condomínio) no board do Monday
Se não existir → cria automaticamente
        ↓
Cria subitem: "Chamado — [Condomínio] — [Data]"
        ↓
Adiciona update com resumo completo do chamado
        ↓
Faz upload dos arquivos anexados para o subitem
        ↓
Exibe confirmação com ID do subitem criado
```
---
📁 Estrutura do repositório
```
/
├── index.html     # Formulário completo (HTML + CSS + JS em arquivo único)
└── README.md      # Este arquivo
```
---
🔒 Segurança
O token da API é inserido pelo operador a cada sessão — não está fixo no código
Este repositório é público: nunca commite tokens ou chaves de API
Para ambientes de produção, considere um proxy/backend para ocultar o token
---
👤 Autor
Marcelo Guimarães  
Engenheiro de Produção · Suporte Operacional e Gestão de Processos  
Portfolio
