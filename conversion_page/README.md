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
  
  Realizado o teste de hipótese para um teste bicaudal, nós encontramos um p-valor de 0.0477 com um nível de significância de 0.05. Assim, nós falhamos em rejeitar a hipótese nula. Ou seja, aceitamos a hipótese nula e concluímos que ambdas as página possuem a mesma taxa de conversão.

# 5. Respondendo as Questões de Negócio.

**1.** A conversão da nova página é realmente melhor do a conversão da página atual?

  - A resposta é não. A sugestão a se dar ao time de negócio é que refaçam o design da página novamente com o objetivo de melhorar a taxa de conversão, ou, realizar uma nova reamostragem que tomaria mais tempo para coleta gerando mais custos para a empresa.
  
**2.** Qual o potencial de número de vendas que a nova página pode trazer?

  - Como o nosso teste nos disse que a página atual e a nova possuem a mesma taxa de conversão, então o potencial de vendas se mantém o mesmo da página antiga.

**3.** Qual o faturamento total na venda do teclado bluetooth através da nova página?

- Como o nosso teste nos disse que a página atual e a nova possuem a mesma taxa de conversão, então o faturamento total de vendas da página nova se mantém o mesmo em relação ao teclado bluetooth.

# 6. Resultados de Negócio

   Em termos de negócio, será comunicado a equipe de designers que não houve diferença na taxa de conversão entre as páginas e, para que se tenha uma taxa de conversão que se torne observável, pode ser tomada as seguintes atitudes:
    
   **1.** A equipe de designers fazer uma nova página com maior qualidade para que a taxa de conversão seja mais perceptível.
    
   **2.** Realizar uma nova amostragem com uma maior quantidade de visitantes para verficar a efetividade da página.
 

# 7. Próximos Passos
  
  Uma vez que sabemos que a página não obteve a taxa de conversão esperada e já informado a equipe de negócio as atitudes a serem tomadas, para complementar a tomada de decisão da empresa seria feito um levantamento dos custos de criar uma página nova, de coletar as amostragem e de nossa consultoria para informar qual é a taxa de conversão mínima que a nova página tem que ter em relação a página antiga para que, no mínimo, custeie a construção da nova página.
  
