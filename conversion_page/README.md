# E-Commerce Eletronic House

<img src="https://github.com/jefferson-datascience/project_eletronic_house/blob/main/images/logo_eletronic_house.jpg" alt="logo" style="zoom:80%;" />

O objetivo deste projeto é realizar um teste A/B para informar ao time de marketing e o time de negócio qual página tem uma maior conversão de compras de um teclado bluetooth.

O contexto de negócio é fictício. Todavia, o planejamento, execução, desenvolvimento e implementação da solução seguem todos os passos de um projeto real.

Os dados do problema de negócio estão disponíveis no kaggle: https://www.kaggle.com/datasets/zhangluyuan/ab-testing?resource=download


# 1. Problema de Negócio

A Electronic House é um comercio online ( e-commerce ) de produtos de informática para casas e escritórios. Os clientes podem comprar mouses, monitores, teclados, computadores, laptops, cabos HDMI, fones de ouvido, cameras webcam, entre outros, através de um site online e recebem os produtos no conforto de suas casas. O time de UX designers vem trabalhando em uma nova página de vendas, com o objetivo de aumentar a taxa de conversão de um produto da loja, um teclado bluetooth. O product manager (gerente de produto) disse que a taxa de conversão da página atual é de 13% em média, no último ano.

O objetivo do product manager é aumentar a taxa de conversão em 2%, ou seja, a nova página de vendas, desenvolvida pelo time de UX, seria um sucesso se a sua taxa de conversão fosse de 15%. O teclado bluetooth possui um preço de venda de R$ 4.500,00 à vista ou parcelado em 12% sem juros no cartão de crédito.

Antes de trocar a página de vendas antiga pela nova, o product manager gostaria de testar a efetividade da nova página em um grupo menor de clientes, a fim de correr menos riscos de queda da conversão, caso a página nova mostre uma conversão pior do que a página atual.

Dessa forma, nosso objetivo como Cientista de Dados na Eletronic, é auxiliar o time de Designers da nova página, a validar a sua efetividade de uma maneira mais segura, com mais confiança e rigidez na análise. Além disso, o time de Designers tem as segunites questões de negócio:

**1.** A conversão da nova página é realmente melhor do a conversão da página atual?

**2.** Sendo a página nova melhor que a antiga, qual o potencial de número de vendas que a nova página pode trazer?

**3.** Sendo a página nova melhor que a antiga, qual o faturamento total na venda do teclado bluetooth através da nova página?

## Planejamento de Solução?

**Qual a solução para o problema?** A solução para esse problema é a aplicação de um teste A/B sobre uma amostra dos cliente da empresa. 

**Como vai ser o produto final?** Vai ser um relatório com as questões de negócio respondidas.


# 2. Suposições de negócio.

|   Atributos  |                                                     Descrição                                                   | 
|--------------|-----------------------------------------------------------------------------------------------------------------|
|  user_id     |                                          Identificador do usuário                                               |
| timestamp    |                                  Registro do horário em que o usuário acessou a página                          |
|   group      |       **control:** Visitante está no grupo de controle; **treatment:** Visitante está no grupo de tratamento    |      
| landing_page | **old_page:** Página antiga foi apresentada ao visitante; **new_page:** página nova foi apresentada ao visitante|
|  conversion  | **1:** Visitante adquiriu o teclado bluetooth;  **0:** Visitante não adquiriu o teclado.                        | 

# 3. Estratégia de Resolução

**Etapa 00. Carregamento dos Dados:** Primeiramente, carregamos os dados e analisamos brevemente os dados. 

**Etapa 01. Escolha do Teste:** Escolha do Teste que será utilizado para validar a efetivade da nova página.

**Etapa 02. Design de Experimento:** Formulação da hipótese nula, hipótese alternativa, definação da métrica, escolha dos parâmetros para determinar o tamanho da amostra.

**Etapa 03. Coleta e Preparação dos Dados de Amostra:** Preparação dos dados, coleta dos dados de amostra, remoção da duplicidade das flags, amostragem aleatória dos grupos de tratamento e controle. 

**Etapa 04. Teste de Hipótese:** Teste para verificar se a página nova possui uma taxa de conversão diferente da taxa de conversão da página atual. 

# 4. Conclusão do Teste 

No nosso teste, foi assumido duas hipóteses. São elas:

  **Hipótese Nula:** A página antiga e a página nova têm a mesma taxa de conversão, isto é, ambas possuem 13%.

  **Hipótese Alternativa:** A página com o design novo tem uma taxa de conversão diferente de 13%.(Teste Bicaudal.)
  
  Realizado o teste de hipótese para um teste bicaudal, nós encontramos um p-valor de 0.0477 com um nível de significância de 0.05. Assim, rejeitamos a hipótese nula e concluímos que as páginas possuem taxa de conversão diferentes. Melhor ainda, conseguimos concluir que a taxa de conversão da página nova é maior que a antiga e está com uma taxa de conversão em torno de 13.8%, logo, um lift de 0.8% em relação a página antiga.

# 5. Respondendo as Questões de Negócio.

**1.** A conversão da nova página é realmente melhor do a conversão da página atual?
    
- Após realizado os testes, concluímos que a página com o novo design é realmente melhor que a página atual. De forma mais detalhada de acordo com os teste, é esperado uma melhora de 0.8% na taxa de conversão da página nova em relação a página antiga, pois a página nova possui uma taxa de conversão maior que atual que é 13% e a taxa de conversão da nova página é menor que 13,9%, segundo os testes estatísticos realizados.

**2.** Qual o potencial de número de vendas que a nova página pode trazer?

- Segundo os dados da empresa, com a página antiga, nós tivemos uma taxa de conversão de 13%, na média, no último ano com a venda de teclado bluetooth, isto é, a cada 100.000 acessos, podemos dizer que foram vendido 13.000 teclados bluetooth, ou seja, temos um faturamento de R$ 58.800.00
- Com a nova página atuando, é esperado um lift de 0.8% na taxa de conversão. Logo, para cada 100.000 acessos, podemos dizer que se espera uma venda de 800 teclados bluetooth a mais, ou seja, temos uma estimativa de aumento no faturamento de R$ 3.600.000.

**3.** Qual o faturamento total na venda do teclado bluetooth através da nova página?
    
- Como não temos informações sobre a quantidade média de acessos anualmente, esperasse que a cada 100.000 acessos tenhamos um faturamento total de R$ 62.100.00 com a nova página.
    

# 6. Resultados de Negócio

   Para o negócio, é esperado um aumento de faturamento de R$ 3.600.00
 

# 7. Próximos Passos
  
  Os próximos passos é monitorar a nova página e analisar a taxa de conversão de compra do teclado Bluetooth.
  
**Clique aqui para acessar o código e o desenvolvimento do projeto:** https://github.com/jefferson-datascience/project_eletronic_house/blob/main/conversion_page/notebooks/eletronic_house_page_conversion.ipynb
  
