# Recibo Fácil

Aplicação simples para preencher, visualizar e imprimir recibos. Inclui cartão de crédito parcelado, frequência mensal ou quinzenal, vencimentos editáveis e taxa de juros mensal configurável.

## Cálculo dos juros

A taxa mensal informada é aplicada sobre o valor original em cada período até a última parcela (juros simples). No parcelamento quinzenal, cada período equivale a meio mês. O valor com juros é dividido pelas parcelas, com eventual ajuste de centavos na última. A taxa não é impressa no recibo; os valores das parcelas já incluem os juros.

## Publicar com GitHub Pages

1. Crie um repositório no GitHub.
2. Envie `index.html` e este `README.md` para a raiz do repositório.
3. Abra **Settings → Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**.
5. Escolha a branch `main` e a pasta `/(root)`, depois clique em **Save**.
6. O GitHub mostrará o endereço do site nessa mesma página após publicar.

O app roda no navegador e não envia os dados do recibo para um servidor.
