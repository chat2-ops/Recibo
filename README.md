# VendaFácil

Aplicativo web simples para controlar estoque de celulares e acessórios, vendas parceladas e recibos. O resumo mostra custo, preço de venda e lucro bruto médios por unidade, além dos totais do estoque. Ao cadastrar novamente um produto com o mesmo nome e categoria, ele pode somar a reposição ao estoque existente e recalcular o custo médio; também permite unir cadastros duplicados. Contratos sem parcelas pagas podem ser excluídos com confirmação, repondo o item ao estoque quando possível.

## Publicar no GitHub Pages

1. Crie um repositório no GitHub.
2. Extraia este pacote no seu computador.
3. Envie todos os arquivos (`index.html`, `sw.js`, `manifest.webmanifest`, `icon-192.png`, `icon-512.png` e `README.md`) para a pasta principal do repositório.
4. Nas configurações do repositório, abra **Pages** e escolha publicar a partir da branch principal (`main`) e da pasta raiz (`/ (root)`).
5. Salve e aguarde o GitHub mostrar o endereço publicado.

## Dados na nuvem (Supabase)

- Produtos, vendas e parcelas ficam no Supabase (tabelas `vf_products`, `vf_sales` e `vf_rentals`), ligados à sua conta de login.
- É preciso criar uma conta (e-mail e senha) na primeira vez. Cada conta só enxerga os próprios dados (RLS).
- O app funciona sem internet depois do primeiro login: ele guarda uma cópia dos dados no aparelho e envia as alterações pendentes quando a conexão voltar. Para ver no celular o que foi alterado em outro aparelho, recarregue a página com internet.
- Para instalar como app: abra o endereço no celular e use "Adicionar à tela inicial" (ou "Instalar app" no Chrome).
- Se duas pessoas alterarem o mesmo item sem internet, vale a última alteração enviada.
- Sair da conta apaga a cópia local; só use o app em aparelho seu.
- Se houver dados antigos salvos no navegador, o app oferece enviá-los para a nuvem no primeiro login.
- O app usa só a chave pública (publishable) do Supabase, que pode ficar no código. Nunca coloque a chave `service_role` aqui.
- Depois de criar a sua conta, desative novos cadastros em Authentication > Sign In / Providers no painel do Supabase.
- Não envie cópias de segurança JSON com dados de clientes para um repositório público.
- Não existe bloqueio remoto de celulares.

## Aluguel

Na aba **Aluguel** você cadastra o aparelho alugado, o valor dele e a porcentagem cobrada por mês. A mensalidade é o valor do aparelho vezes a porcentagem. O aparelho sai do estoque enquanto está alugado e volta quando o aluguel é encerrado. Os pagamentos são registrados mês a mês, em ordem, e cada aluguel tem recibo para imprimir ou compartilhar.

O app calcula juros simples: a taxa mensal é aplicada ao valor original por cada mês do prazo, sem juros sobre juros. A última parcela pode ter ajuste de centavos para fechar o total. Confira as informações contratuais aplicáveis ao seu negócio.
