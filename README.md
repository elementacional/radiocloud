# CloudRadio 2.4 — Player público e Admin

## Estrutura no GitHub Pages

- `index.html`: página pública /radiocloud/.
- `admin/index.html`: administração /radiocloud/admin/.
- `catalogo-publico.json`: índice usado pelo player (sem credenciais).
- `audio/`: MP3 **públicos** autorizados para distribuição.

## Publicar músicas reais (procedimento inicial)

1. Abra o Admin e conecte a conta Google que contém seus MP3. Confirme que o catálogo foi carregado.
2. Na seção **Publicação do player Web**, selecione uma faixa e clique em **Baixar MP3 selecionado**. O arquivo será baixado como `<id>.mp3`; **não renomeie**.
3. No repositório GitHub, coloque o arquivo na pasta `audio/` (crie-a, caso necessário).
4. No Admin, clique **Exportar índice público**. Substitua `catalogo-publico.json` na raiz do GitHub pelo arquivo baixado.
5. Depois de o GitHub Pages publicar o commit, abra `/radiocloud/` e recarregue com Ctrl+F5.

**Importante:** o índice pode conter faixas para as quais você ainda não enviou o MP3 público. Esses itens aparecerão, mas não tocarão até que o respectivo `audio/<id>.mp3` exista. Use apenas músicas que você tem direito de distribuir. O Drive privado original não é alterado.

O OAuth Client ID Web do Google deve ser inserido no Admin; **nunca** publique um Client Secret ou token. A interface `/admin/` é publicamente acessível como página; OAuth protege acesso às contas, não oculta a página.

**Limitações:** GitHub Pages não é hospedagem dedicada de streaming e tem limites de uso e tamanho; esse método é para acervos pequenos/testes, não rádio em escala ou 24/7. Google Drive privado não é fonte direta do player público. Requer publicação manual dos arquivos e do catálogo. Reprodução no player é sob demanda e depende do navegador aberto.
