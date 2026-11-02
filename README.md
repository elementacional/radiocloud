# CloudRadio 2.6 — Player Web + Admin

## Publicação

Publique `index.html`, `catalogo-publico.json` e a pasta `admin/` no GitHub Pages, usando a branch `main` e `/ (root)`.
**Não substitua nem apague a pasta `audio/` existente.** O ZIP contém apenas um arquivo de orientação na pasta `audio/`, não os MP3.

- Player público: https://elementacional.github.io/radiocloud/
- Administração: https://elementacional.github.io/radiocloud/admin/

## Novidades do Player 2.6
- Controles compactos, volume ajustável e atalhos: espaço (play/pause), setas esquerda/direita (retroceder/avançar 10 s) fora dos formulários.
- Mensagens ao perder/restabelecer conexão.
- Tenta usar uma cópia **somente do catálogo público** no armazenamento local se a leitura remota falhar. Não guarda tokens OAuth.
- Se não houver catálogo, tenta descobrir MP3 da pasta pública `audio/` através da API pública do GitHub, sujeito a limites de requisição.
- A interface preserva filtros por gênero, artista e álbum, reprodução automática e aleatória e layout móvel.

## Admin e arquivos privados

O Admin conserva a integração OAuth já existente. Os arquivos privados do Google Drive **não se tornam públicos automaticamente**. Para transmitir esses áudios sem duplicar arquivos será necessário um backend com autenticação Google segura, controle de acesso e proxy de streaming com suporte a requisições Range. O GitHub Pages, sozinho, não implementa esse backend.

## Testes sugeridos
1. Abra o player e confirme Earthbound e Em Chamas.
2. Teste próximo automático, repetição, alternar gêneros e volume.
3. Teste no celular com a tela vertical e horizontal.
4. Confira o Admin e OAuth antes de novos uploads.

Use apenas conteúdos para os quais você tenha direito de distribuição pública.
