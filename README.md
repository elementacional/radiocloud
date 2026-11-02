# CloudRadio 2.7 — Admin e Player Web

Atualização incremental sobre a versão 2.6.

- Raiz `index.html`: player público, com ícone de volume ao lado do tempo total. Clique para abrir barra vertical com gradiente azul–vermelho.
- `admin/index.html`: painel administrativo com seção 5A de mapeamento em árvore das pastas e MP3 acessíveis na conta Google ativa. Exporta mapa somente de metadados como JSON.
- `catalogo-publico.json`: cópia de referência; preserve o arquivo já publicado se houver outras músicas.
- Pasta `audio/`: **não incluída neste pacote**; mantenha os MP3 do repositório existente.

O mapeamento não disponibiliza MP3 privados ao Player Web. Para ouvir publicamente sem OAuth, continua necessário áudio servido por URL pública ou backend seguro. O escopo `drive.file` limita o acesso às pastas/arquivos autorizados. Mapeie uma conta de cada vez; o token fica só em memória.

Instalação: substitua apenas `index.html` e `admin/index.html` no repositório, preserve a pasta `audio/` e o catálogo público atual. Teste a autenticação e os controles depois do deploy.
