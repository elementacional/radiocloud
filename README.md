# CloudRadio 2.3

## Dois aplicativos independentes

- `/index.html`: **Web Player**, interface pública responsiva. Não exige login Google e não gerencia os arquivos.
- `/admin/index.html`: **Admin**, gerencia OAuth, pastas, upload, artistas, álbuns, catálogo e múltiplas contas Drive. É o painel 2.2 com identificação 2.3 e exportação de catálogo público.
- `/catalogo-publico.json`: catálogo público de faixas com URLs HTTPS diretamente reproduzíveis. Começa vazio de propósito: os MP3 privados do Drive **não são URLs públicas**.

## Publicação no GitHub Pages

Copie **o conteúdo inteiro** desta pasta para a raiz do repositório `radiocloud`. Acesse:

- `https://elementacional.github.io/radiocloud/` para o player público.
- `https://elementacional.github.io/radiocloud/admin/` para administrar.

No Google Cloud, a origem JavaScript OAuth continua `https://elementacional.github.io`. Use o mesmo Client ID Web válido da versão anterior. Nunca coloque um Client Secret no GitHub.

## Como alimentar o player público

No Admin, use **Exportar catálogo público (JSON)**. Isso inclui somente músicas cadastradas com URL direta HTTPS de áudio e sem identificador de arquivo privado Drive. Substitua `catalogo-publico.json` na raiz do GitHub pelo JSON exportado.

**Atenção:** exportar não transforma MP3 privados do Drive em públicos. Para disponibilizar essas músicas, será preciso hospedar cópias autorizadas em serviço de mídia que permita distribuição HTTPS pública. O painel Admin e o player Web são separados intencionalmente. O player é sob demanda; não transmite uma estação sincronizada 24/7.

## Interface

Filtros por gênero, artista, álbum, busca, reprodução automática, modo aleatório, repetição, controles ⏮ ▶/⏸ ⏭, temporizador acima dos controles, desktop e celular, suporte Media Session quando disponível. Reprodução em segundo plano no celular depende do navegador e do sistema.
