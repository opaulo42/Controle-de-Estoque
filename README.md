# Controle de Estoque

App de saída de material: marca a saída, dá baixa nas quantidades, guarda o histórico (com o código do sistema) e exporta a planilha atualizada. Funciona sem internet, no PC e no celular.

**Este repositório não contém nenhum material.** O app vem vazio; os itens são importados por você, no seu aparelho, e ficam salvos só nele.

## Publicar no GitHub Pages
1. Crie um repositório e envie todos os arquivos desta pasta (Add file > Upload files).
2. Em Settings > Pages, escolha Deploy from a branch, branch `main`, pasta `/ (root)`, e salve.
3. Aguarde um ou dois minutos e abra o endereço `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

## Instalar como app
- Android (Chrome): menu ⋮ > Instalar app (ou Adicionar à tela inicial).
- iPhone (Safari): Compartilhar > Adicionar à Tela de Início.
- PC (Chrome ou Edge): ícone de instalar na barra de endereço.

Depois de instalado, abra o app uma vez com internet; a partir daí ele funciona offline.

## Primeiro uso
Na aba **Planilha**, toque em **Importar planilha (.xlsx)** e escolha a sua planilha de estoque (ou baixe o **modelo vazio** para preencher). Cabeçalhos esperados: Item, Descrição, Und Medida, Tipo, Setor, Quantidade Mínima, Quantidade em estoque, Cód. no Sistema, Cód. 2, Origem.

## Ligar ao Google Planilhas (opcional)
Veja o passo a passo em `GOOGLE.md`.

## Cuidados
- Não envie planilhas nem backups para o repositório (o `.gitignore` já bloqueia `.xlsx`, `.csv` e backups `.json`).
- Os dados ficam no navegador de cada aparelho. PC e celular não se sincronizam: use **Baixar planilha** ou **Backup** e importe/restaure no outro.
- No iPhone, o app instalado na tela inicial guarda os dados separados do Safari. Importe a planilha depois de instalar.
- Limpar os dados do navegador apaga o histórico. Baixe a planilha atualizada com frequência.
- Atualizações: ao publicar uma versão nova, o app instalado a carrega na segunda abertura.
