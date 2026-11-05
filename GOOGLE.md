# Ligar o app a uma planilha do Google

Com isso você salva as alterações na planilha do Google Drive (só quando tocar em **Salvar na planilha**) e atualiza o app a partir dela em outro aparelho. Funciona apenas na versão publicada no GitHub Pages. Os nomes dos menus do Google podem variar um pouco.

## 1. Configuração única no Google Cloud (uns 10 minutos)
1. Acesse https://console.cloud.google.com e crie um projeto (ex.: "Controle de Estoque").
2. Em APIs e serviços > Biblioteca, procure **Google Sheets API** e ative.
3. Em Tela de consentimento OAuth (Google Auth Platform), preencha nome do app e seu e-mail e escolha público **Externo**.
   - **Importante:** em Público-alvo > **Usuários de teste**, adicione o e-mail de **cada conta Google que vai usar o app** (PC e celular). Sem isso o Google bloqueia o login com o erro 403 `access_denied`.
4. Em Credenciais > Criar credenciais > **ID do cliente OAuth** > tipo **Aplicativo da Web**.
   - Em **Origens JavaScript autorizadas**, coloque só o endereço, sem barra no final e sem o nome do repositório: `https://SEU-USUARIO.github.io`
5. Copie o **ID do cliente** (termina em `.apps.googleusercontent.com`).

## 2. Preparar a planilha
- Precisa ser uma **planilha nativa do Google**. Se no Drive ela for um .xlsx, abra e use Arquivo > Salvar como Planilhas Google.
- Deve ter a aba **Estoque** (ou ser a primeira aba) com os cabeçalhos: Item, Descrição, Und Medida, Tipo, Setor, Quantidade Mínima, Quantidade em estoque, Cód. no Sistema, Cód. 2, Origem.
- Itens novos: acrescente uma linha no fim, com descrição e quantidade. A coluna Item pode ficar em branco.
- A aba **Histórico de saídas** é criada sozinha no primeiro salvamento.

## 3. No app
1. Abra a aba **Planilha**, cole o ID do cliente e o link da planilha e toque em **Vincular planilha**.
2. Toque em **Atualizar da planilha** e entre com a sua conta. Se aparecer "app não verificado", escolha Avançado > continuar (é o seu próprio app).
3. Use normalmente. A aba Planilha mostra quantas saídas estão pendentes.
4. Toque em **Salvar na planilha** quando quiser enviar. O app lê as quantidades atuais da planilha, subtrai só as saídas ainda não enviadas, acrescenta o histórico e atualiza os dados locais. Assim, saídas feitas em dois aparelhos não se sobrescrevem.

## Observações
- O Google pede login a cada sessão (o acesso dura cerca de 1 hora).
- Se o navegador bloquear a janela de login, permita pop-ups para o site.
- Se você renomear ou apagar um item na planilha que tem saída pendente, o salvamento é cancelado sem alterar nada e o app avisa qual item não achou.
- Mexa nas quantidades direto na planilha só depois de salvar ou atualizar, para evitar conflito.

## Histórico de saídas
- **Salvar na planilha** acrescenta as saídas na aba **Histórico de saídas**, com número da saída contínuo entre os aparelhos.
- **Atualizar da planilha** traz esse histórico de volta, então o PC e o celular mostram o mesmo histórico no app. Saídas ainda não salvas aparecem como **Não salva**.
- Não apague nem reordene colunas dessa aba, e evite editar linhas à mão: o app lê data, hora, item, descrição e quantidade para reconhecer cada saída.

## Se der erro no login
- **Erro 403 access_denied / "não concluiu o processo de verificação":** a conta usada não está na lista de usuários de teste. Adicione o e-mail (passo 3).
- **Funciona no PC mas não no celular:** confira qual e-mail aparece na tela de bloqueio. O celular pode ter escolhido outra conta Google. Use "Usar outra conta" e confira também se o ID do cliente colado no celular é o mesmo do PC.
- **Janela não abre:** permita pop-ups para o site. No iPhone, use pelo Safari em vez do app instalado.
