# CloudRadio 2.5

## Instalação
- **Faça backup** da versão 2.4 e do catálogo público atual.
- Substitua `index.html` e `admin/index.html` pelos novos arquivos.
- Mantenha `audio/` e seus MP3 existentes. Não sobrescreva nem apague os MP3!
- O `catalogo-publico.json` deste pacote preserva Earthbound e Em Chamas, mas caso seu catálogo publicado tenha mais músicas, NÃO o substitua: use o existente e importe pelo editor do Admin.
- No Admin, seção 7, carregue o catálogo publicado e inclua MP3 que você pretende enviar a `audio/`. Ajuste título, gênero, artista e álbum e exporte o JSON.
- Envie os MP3 públicos ao GitHub, na pasta `audio/`, e atualize o JSON na raiz.

O Admin NÃO faz upload direto ao GitHub: evita armazenar tokens de escrita em HTML público. OAuth Google Drive permanece inalterado. As origens privadas continuam privadas.

## Melhorias
- Editor de catálogo público com carregamento, metadados editáveis e exportação de JSON.
- Player com capas de álbum opcionais por URL HTTPS.
- Recuperação de emergência dos MP3 na pasta pública `audio/` caso o catálogo esteja vazio (somente repositório elementacional/radiocloud). Para metadados corretos, mantenha o JSON atualizado.
- Reprodução sequencial e responsividade preservadas.

A 2.5 não é um serviço de streaming 24/7. Para escala será necessária uma solução dedicada de distribuição de áudio.
