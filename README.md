# 📻 CloudRadio — Biblioteca Musical e Rádio Virtual

**CloudRadio** é um projeto de aplicativo web para organizar, catalogar e reproduzir músicas hospedadas em diferentes serviços de nuvem. Seu objetivo é evoluir para uma **rádio online pública 24 horas por dia, 7 dias por semana**, acessível por link e independente do computador do administrador.

O projeto dá atenção especial a composições criadas com inteligência artificial, como as exportadas do **Happy Shrimp**, mas também prevê músicas e áudios de outras origens, respeitando as permissões de uso e distribuição.

> **Estado do projeto:** em desenvolvimento. A interface HTML e funcionalidades de catalogação foram implementadas em versões experimentais. A autenticação OAuth, o upload e a sincronização no Google Drive ainda exigem configuração e testes. **A transmissão pública contínua 24/7 ainda não está implementada.**

## 🎯 Objetivos

- Construir um acervo musical organizado por categorias e fontes.
- Preservar links de origem e metadados de cada composição.
- Usar o **Google Drive** como destino inicial dos uploads de MP3.
- Manter **GitHub, 4shared, Happy Shrimp e URLs externas** como fontes catalogáveis.
- Oferecer pré-escuta para arquivos efetivamente acessíveis ao navegador.
- Evoluir para playlists, programação automática e uma rádio pública 24/7 **sem AzuraCast**.

## ✨ Funcionalidades e andamento

| Recurso | Estado |
| --- | --- |
| Interface web em HTML, CSS e JavaScript | Protótipo disponível |
| Cadastro de músicas por título, categoria e URL | Protótipo disponível |
| Registro de links do Happy Shrimp e outras fontes | Protótipo disponível |
| Catálogo local no navegador | Protótipo disponível |
| Exportação do catálogo em JSON | Disponível nas versões experimentais |
| Player para URLs diretas de áudio compatíveis | Disponível para testes |
| Autenticação com Google (OAuth 2.0) | Implementação inicial; requer configuração e validação |
| Upload de MP3 para pasta no Google Drive | Implementação inicial; requer validação |
| Catálogo JSON sincronizado com Google Drive | Implementação inicial; requer validação |
| Reprodução automática de páginas compartilhadas de terceiros | Não garantida; depende da plataforma e da URL de áudio |
| Rádio pública sincronizada, 24/7 | Planejada |

## 🏗️ Arquitetura proposta

```text
Google Drive (MP3 e catálogo principal)
Happy Shrimp / 4shared / GitHub / URLs externas
                   │
                   ▼
          Catálogo CloudRadio
  (título, categoria, origem, ID, URL)
                   │
           ┌───────┴────────┐
           ▼                ▼
    Painel de gestão    Player web
                            │
                            ▼
                 Público / ouvintes

Futuro: programador de rádio e distribuição
        contínua de áudio em infraestrutura
        própria ou serviços compatíveis.
```

**Importante:** o GitHub Pages hospeda a interface, **não executa uma transmissão 24/7 no servidor**. E guardar MP3s no Google Drive não garante URLs públicas adequadas para muitos ouvintes. A transmissão contínua precisará de infraestrutura específica para programação e distribuição do áudio.

## 📁 Estrutura prevista no Google Drive

```text
Meu Drive/
└── CloudRadio/
    ├── Musicas/
    │   ├── composicao-01.mp3
    │   └── composicao-02.mp3
    └── catalogo.json
```

Essa é a estrutura de destino proposta para uploads realizados pelo aplicativo após a autorização do usuário. **O envio pelo navegador não acontece automaticamente apenas por selecionar um arquivo:** a conexão OAuth e o upload precisam estar operacionais.

## 🚀 Como publicar a interface no GitHub Pages

1. Crie um repositório chamado `CloudRadio`.
2. Envie o arquivo HTML da versão que deseja testar.
3. Salve uma cópia como `index.html` na raiz do repositório.
4. Abra **Settings → Pages**.
5. Em **Build and deployment**, escolha **Deploy from a branch**, a branch `main` e a pasta `/ (root)`.
6. Acesse `https://SEU-USUARIO.github.io/CloudRadio/` (substitua pelo seu nome de usuário).

> A publicação permite testar o HTML via HTTPS. Ela não configura automaticamente o Google Drive nem transforma a interface em uma estação de rádio 24/7.

## 🔐 Google Drive e autenticação

A integração planejada utiliza **Google OAuth 2.0** e a **Google Drive API**, com permissões limitadas aos arquivos criados ou selecionados pelo aplicativo sempre que possível (`drive.file`).

Para configurar:

1. Crie ou selecione um projeto no [Google Cloud Console](https://console.cloud.google.com/).
2. Ative a **Google Drive API**.
3. Configure a tela de consentimento OAuth.
4. Crie um **OAuth Client ID** do tipo *Aplicativo Web*.
5. Cadastre a origem HTTPS exata do seu GitHub Pages nas origens JavaScript autorizadas.
6. Insira o **Client ID** na configuração do CloudRadio e autorize o acesso.
7. Teste com um MP3 pequeno e confira o arquivo e o catálogo no Drive.

**Segurança:** não publique senhas, tokens de acesso, *client secrets* ou credenciais privadas no GitHub. O Client ID usado por um aplicativo web não é uma senha, mas tokens de acesso devem ser tratados como dados sensíveis.

## 🎵 Como cadastrar músicas

### MP3 no Google Drive

Após configurar a autenticação, o fluxo pretendido é: selecionar o MP3 → definir categoria → opcionalmente registrar o link original do Happy Shrimp → enviar para a pasta `CloudRadio/Musicas` → atualizar `catalogo.json`.

### Arquivos de outras nuvens

Cadastre o **título**, a **origem**, o **link da página** e, se disponível, a **URL direta de áudio**. Links de compartilhamento de páginas do Happy Shrimp ou 4shared **não são necessariamente arquivos MP3 reproduzíveis**. O catálogo pode preservar a referência mesmo quando não for possível tocar o áudio diretamente.

## 📻 Visão da rádio pública 24/7

A evolução planejada prevê:

- Playlist automática e programação musical por categoria.
- Reprodução sincronizada para ouvintes que acessam o mesmo endereço.
- Serviço de programação executado na nuvem, independente do computador local.
- Distribuição estável de áudio, com monitoramento de disponibilidade das fontes.
- Painel de administração separado da página pública para ouvintes.

Uma playlist que começa a tocar ao abrir a página **não equivale** a uma transmissão pública sincronizada 24/7; esta última exige serviços adicionais.

## 🗺️ Próximas etapas

1. Validar a abertura e inicialização do HTML publicado no GitHub Pages.
2. Configurar OAuth e realizar o primeiro upload real no Google Drive.
3. Verificar criação da pasta `CloudRadio/Musicas` e persistência de `catalogo.json`.
4. Implementar importação de backup, mesclagem segura de registros e identificação de duplicatas.
5. Testar reconhecimento de URLs e reprodução de arquivos realmente acessíveis.
6. Definir infraestrutura de distribuição para a rádio pública 24/7 sem AzuraCast.

## ⚖️ Direitos de uso

Antes de transmitir músicas publicamente, confirme as licenças aplicáveis, os termos das plataformas de geração e armazenamento e eventuais obrigações de direitos autorais e execução pública.

---

**CloudRadio** — Um acervo musical conectado à nuvem, com o objetivo de se tornar uma rádio virtual pública e independente.
