# E-Commerce Eletronic House

<img src="https://github.com/jefferson-datascience/project_eletronic_house/blob/main/images/logo_eletronic_house.jpg" alt="logo" style="zoom:80%;" />

O objetivo deste projeto é realizar um teste A/B para informar ao Head de Designers e o seu time e o formulário de pagamento manual tem uma maior conversão na finalização das compras do que o formulário com o preenchimento automático.

O contexto de negócio é fictício. Todavia, o planejamento, execução, desenvolvimento e implementação da solução seguem todos os passos de um projeto real.

Os dados do problema de negócio estão disponíveis no meu drive: https://drive.google.com/file/d/1oUJLeAgSaUI7CA-0F14KG0FzXEim7pSe/view

#### This project was made by Jefferson Henrique Candido.

# 1. Problema de Negócio.

  A Electronic House é um comercio online ( e-commerce ) de produtos de informática para casas e escritórios. Os clientes podem comprar mouses, monitores, teclados, computadores, laptops, cabos HDMI, fones de ouvido, cameras webcam, entreoutros, através de um site online e recebem os produtos no conforto de suas casas.

Os produtos não são vendidos somente no Brasil, a Eletronic House está presente em diversos países da Europa e da América do Norte. O Diretor de Produtos Global pediu ao Head de Design que desenvolvesse uma nova forma de finalizar a compra com cartão de crédito, sem a necessidade do cliente preencher manualmente todas as informações do cartão e que funcionasse em todos os países. Depois de meses desenvolvendo esse dispositivo, o time de Desenvolvimento Backend entregou uma solução de pagamentos, na qual 90% das informações do formulário eram preenchido automaticamente.

O Head de Designer gostaria de medir a efetividade do novo dispositivo de preenchimento automático dos dados do cartão de crédito na página de vendas e reportar os resultados ao Diretor de Produtos Global, para concluir se a nova forma de pagamento é realmente melhor do que a antiga.

As duas páginas foram colocadas no ar e durante alguns meses o time de Front-End desenvolveu uma automação que atribui um rótulo para cada cliente, mostrando qual a página de vendas aquele determinado cliente estava visualizando.

Todos esses dados foram armazenados em um banco de dados e podem ser acessados pelos times da Electronic House.

Depois de alguns meses de experimento, o time de Designers da Electronic House, precisa avaliar os resultados do experimento realizado, a fim de concluir qual era a forma de pagamento mais eficaz. Porém, o time não possui as habilidades necessárias para avaliar os dados e concluir o experimento. Nesse contexto, a empresa precisa dos nossos serviços de Cientista de Dados para ajudar o time de Designers a validar a efetividade do novo meio de pagamento, com mais confiança e rigidez na análise.

Conversando com O head de Designers, descobriu-se que o lift esperado é de 8% na média de gastos.

O Head de Designer tem a seguinte questão de negócio:
 
 1. Qual a melhor forma de pagamento: Preenchimento Manual ou Automático do formulário de dados do cartão de crédito?
 
 ## Planejamento da Solução?
 
**Qual vai ser a solução para o problema?** A solução para esse problema é uma aplicação de teste A/B em uma amostra de clientes que utilizaram o formulário automático e manual.
 
**Qual vai ser o produto final?** O produto final será um relatório com as questões de negócios respondida.

# 2. Suposições de Negócio

|   Atributos   |                                                        Descrição                                             |
|---------------|--------------------------------------------------------------------------------------------------------------|
|    **uid**    |                                            Identificador único do Usuário                                    |
|  **country**  |                                     País em que o usuário preecheu o formulário                              |
|   **gender**  |                                                Gênero do Usuário                                             |
|   **spent**   |                                          Quantidade gasta pelo cliente                                       |
|  **purhases** |                                         Quantidade de compras realizadas                                     |
|    **date**   |                                         data em que a compra foi realizada                                   |
|   **group**   | GRP A: Grupo em que foi exibido o formulário manual; GRP B: Grupo em que foi exibido o formulário automático |
|   **device**  |                I: Compra foi realizada através do site; A: Compra foi realizada através do App               | 


# 3. Estratégia de Solução

**Etapa 00. Carregamento dos Dados:** Carregar os dados, Visualização Geral dos Dados.

**Etapa 01. Escolha do Teste:** Escolher do Tipo de Teste que será utilizado para resolver o problema de negócio.

**Etapa 02. Design de Experimento:** Formulação das hipóteses nula, hipótese alternativa e definição da métrica e determinação do tamanho da amostra.

**Etapa 03. Preparação e Coleta dos Dados de Amostragem:** Verificação de dados nulos e duplicidade de flags e homogeneidade dos dados. Em  seguida, separação dos grupos controle e tratamento, coleta das amostragem e cálculo das taxas de conversões.

**Etapa 04. Teste de Hipótese:** Determinação da melhor inferência, cálculo do p-valor e validação das hipóteses nula e alternativa.

**Etapa 05. Conclusão do Teste:** Apresentar o relatório respondendo a questão de negócio.

# 4. Conclusão do Teste

Não conseguimos seguir com o experimento na Espanha, Grã-Bretanha, Turquia, Alemanha, França, Austrália e Canadá, pois faltam dados para realizar a amostra. Tanto para os dados do site quanto para os dados do App. Conseguimos das prosseguimento com os dados somente do Brasil, México e Estado Unidos.

Para os Dados do Site, foi formulada as seguintes hipóteses:

**Hipótese Nula:** O preechimento automático e o preenchimento manual possuem a mesma média de quantidade gasta pelo site.

**Hipótese Alternativa:** O preechimento automático e o preenchimento manual possuem média de compras finalizadas diferentes pelo site.

Nos dados do site do Brasil, México e Estados Unidos falhamos em rejeitar a hipótese nula, onde os p-valores são, respectivamente, 0.5904, 0.992 e 0.5490 com um nível de significância de 0.05. 

Para os Dados do App, foi formulada as seguintes hipóteses:

**Hipótese Nula:** O preechimento automático e o preenchimento manual possuem a mesma média de quantidade gasta pelo app.

**Hipótese Alternativa:** O preechimento automático e o preenchimento manual possuem média de compras finalizadas diferentes pelo app.

Nos dados do site do Brasil, México e Estados Unidos também falhamos em rejeitar a hipótese nula, onde os p-valores são, respectivamente, 0.2209, 0.284 e  0.3616 com um nível de significância de 0.05. 


# 5. Respondendo as Questões de Negócio

Como não há dados suficiente da Espanha, Grã-Bretanha, Turquia, Alemanha, França, Austrália e Canadá para realizar a amostra, informamos ao Head de Designers que não há dados suficientes para para realizar a inferência sobre esses países e que pode ser adota a seguinte estratégia:

1. Realizar uma maior coleta de dados. 
    
    - Nessa situação, é importante ter em mente qual vai ser o custo desta coleta de mais amostras para que se tenha uma quantidade mínima para observar se há um lift de 8% na média de gastos dos clientes.

Para os dados do Brasil, México e Estados Unidos, não houve diferença na média de gastos utilizando o formulário automático ou manual, tanto pelo site quanto pelo app.

Nesse contexto, podemos tomar a seguinte atitude com o Head de Designers.

1. Informar ao Head de Designers para solicitar a sua equipe uma melhoria no design do formulário automático.

    - Nessa situação, com uma melhoria no formulário, é esperado que se observe um efeito maior na quantidade média de gastos, isto é, um maior lift esperado em relação ao formulário manual.
    
    
2. Informar ao Head de Designers para solicitar uma nova amostragem.
    
    - Nessa situação, é primordial saber os custos e o tempo necessário para se realizar uma nova coleta de dados, pois com essas informações saberemos se com o lift esperado do formulário automático valerá a pena realizar essa nova coleta de dados.

# 7. Próximos Passos

  Os próximos passos desse projeto é levantar os custos de todo o processo de produção da página até o processo de coleta de amostra para saber o quanto que tem que ser o mínimo de lift dessa nova página para que se pague os custos de todo esse processo e além disso se obtenha o faturamento esperado.
