# Metadados

* **Título**: ChainForge: A Visual Toolkit for Prompt Engineering and LLM Hypothesis Testing
* **Autores**: Ian Arawjo, Chelse Swoopes∗, Priyan Vaithilingam∗, Martin Wattenberg, Elena L. Glassman 
* **Instituição(ões) envolvida(s) na pesquisa**: Harvard University
* **Ano de publicação**: 2024
* **Link para acesso**: [arxiv.org/pdf/2309.09128](https://arxiv.org/pdf/2309.09128)

# Qual o problema?

Avaliar as saídas de modelos de linguagem grandes (LLMs) é um desafio significativo, especialmente para aqueles que não possuem formação em programação, como auditores que buscam identificar viéses. A dificuldade fica clara quando a fase de engenharia de prompts e a escolha do modelo são realizadas separadamente, frequentemente em diferentes ferramentas, o que complica o pipeline de desenvolvimento. Além disso, encontrar um prompt que produza saídas consistentes e de qualidade se tornou uma tarefa onerosa, gerando até um mercado próprio. 
As ferramentas disponíveis para avaliação geralmente são fechadas ou focadas em domínios específicos, exigindo conhecimentos técnicos. Os LLMs, por serem considerados "caixas pretas", dificultam ainda mais a avaliação devido à sua baixa explicabilidade e à impossibilidade de serem testados em todos os casos de uso possíveis. A escolha do modelo adequado também se torna um desafio adicional, especialmente em cenários vulneráveis a ataques de injeção de prompt, em que múltiplos testes são necessários para identificar qual modelo é menos suscetível.


# Qual a solução?

## Como os autores tentam resolver o problema? Criando um algoritmo novo? uma metodologia? uma ferramenta? 
A solução apresentada pelos autores é o ChainForge, uma ferramenta visual de código aberto projetada para facilitar a engenharia de prompts e a realização de testes de hipóteses em LLMs. Permite que usuários, mesmo sem conhecimentos técnicos avançados, realizem uma avaliação sistemática do comportamento dos LLMs, unindo os aspectos de exploração e avaliação. 

Oferece as funcionalidades de:
* **Comparação cruzada de modelos:** Permite que os usuários testem diferentes LLMs com os mesmos prompts, facilitando a escolha do modelo mais adequado.
* **Design iterativo de templates:** Usuários podem criar templates de prompts que incorporam variáveis, permitindo uma abordagem mais sistemática na geração de respostas.
* **Avaliação sistemática:** O sistema suporta o envio de múltiplas consultas parametrizadas e ajuda na navegação e pontuação das respostas, permitindo uma análise mais eficiente.

Combinando a usabilidade das ferramentas de programação visual com recursos poderosos, como o envio simultâneo do mesmo prompt para múltiplos LLMs, busca tornar mais acessível e eficiente a experimentação e caracterização do comportamento dos LLMs.


## Quais são os detalhes técnicos dessa solução? O que chama mais atenção? Qual a ideia geral e o que deve ser discutido em mais detalhes?

Tem a seguinte estrutura que oferece flexibilidade para diferentes estilos de uso e objetivos dos usuários:
* **Seleção de Modelo:** Facilita a comparação do comportamento entre diferentes LLMs, permitindo que os usuários avaliem rapidamente as mudanças entre modelos base e ajustados.
* **Design de Templates de Prompts:** Ajuda na criação de templates que utilizam variáveis, assegurando que os prompts gerem saídas consistentes em diversos contextos.
* **Avaliação Sistemática:** Permite o envio de múltiplas consultas parametrizadas, facilitando a navegação e a pontuação das respostas, o que evita a sobrecarga da inspeção manual.
* **Improvisação:** Suporta testes on-demand, permitindo que os usuários ajustem prompts, troquem modelos ou mudem critérios de avaliação conforme novas hipóteses surgem durante a exploração.

Permite a **comparação cruzada de modelos**, possibilitando que usuários testem diferentes LLMs com os mesmos prompts, o que ajuda na seleção do modelo mais adequado. Além disso, o design iterativo de templates permite a criação de prompts com variáveis, promovendo uma abordagem sistemática na geração de respostas.

A ferramenta também oferece recursos como a possibilidade de adicionar nós e conectá-los, com quatro tipos de nós — entradas, geradores, avaliadores e visualizadores — permitindo uma configuração flexível para atender às necessidades dos usuários. A capacidade de enviar múltiplos prompts para diferentes LLMs simultaneamente, junto com a organização hierárquica das variáveis dos prompts, destaca seu poder combinatório e aborda o “problema do multiverso” na comparação de modelos e variáveis em avaliações múltiplas.


# Como foi avaliado?

A avaliação foi realizada por meio de estudos qualitativos envolvendo participantes com diferentes níveis de experiência em programação e LLMs. Os autores conduziram entrevistas e estudos em laboratório para entender como os usuários aplicaram a ferramenta em tarefas relevantes, tanto em contextos propostos por eles quanto em situações do mundo real. Os resultados mostraram que a ferramenta é eficaz para auditoria de viés em modelos e para prototipagem de pipelines de processamento de dados. Além disso, o estudo buscou identificar as forças e limitações da ferramenta, considerando o feedback dos usuários, que também contribuíram para melhorias na interface e na adição de novos recursos.

Durante essa avaliação conduzida, os usuários foram instruídos a fazer um prompt para os modelos GPT-4, Claude-2 e PaLM2 e avaliar as respostas, levando em consideração: a qualidade das respostas, a consistencia das respostas em várias execuções e o quão concisas as respostas eram.

Entretanto, a avaliação de toolkits apresenta suas dificuldades inerentes, pois são difíceis de avaliar no contexto da interação homem-máquina (IHM). O método predominante de avaliação, o estudo de usabilidade controlado, muitas vezes não se adequa a toolkits, pois tendem a focar em um subconjunto restrito das capacidades do toolkit. Isso pode levar a uma compreensão limitada da eficácia geral da ferramenta. 

Não houveram métricas claras.


# Quais são os resultados?
Os participantes tiverem opiniões distinstas sobre a avaliação do prompt e como escolher os modelos de acordo com a sua respostas, concluindo que a escolha entre os modelos depende do contexto e do objetivo do usuário, mas que a ferramenta facilita a comparação entre eles. As opiniões também sugerem que avaliações sistemáticas feitas podem contestar os resultados obtidos com a inspeção manual.


# Resenha crítica

ChainForge é uma boa ferramenta para engenharia de prompts e teste de hipóteses para LLMs, tendo uma interface gráfica simples, sem exigir conhecimentos técnicos avançados. Pode ser usada para avaliar trade-offs, classificar prompts e modelos e revisar hipóteses com mais confiança. 

O design do ChainForge se destaca por permitir a comparação cruzada de modelos, o que facilita a escolha do mais adequado, além de possibilitar a criação de templates de prompts que incorporam variáveis, promovendo uma geração sistemática de respostas. 

No geral é útil, especialmente para usuários que não possuem conhecimento técnico avançado, mas para pipelines avançados de desenvolvimento de soluções com LLMs, pode não ser a mais adequada.

É importante frisar o fato dos autores reforçarem a necessidade do Open Source para esse tipo de projeto, especialmente em uma área que possui alta necessidade de exploração e poucas ferramentas disponíveis.

Existe uma dificuldade em compartilhar os resultados com outras pessoas da equipe após a experimentação, pois a ferramenta não oferece uma maneira fácil de exportá-los.


## Ameaças à validade na avaliação
* Observar mudanças no comportamento dos usuários ao longo de períodos mais longos, como em workshops de várias semanas.
* Reconsiderar o viés de auto-seleção nas entrevistas, em que os participantes podem já ter conhecimento sobre o tema, o que pode ter excluído usuários que não o consideraram útil.


## Trabalhos futuros
* Realizar abordagens quantitativas e controladas em partes da interface para responder a perguntas científicas específicas;
* Aprimorar o sistema base;


# Discussão

* No contexto do projeto, é interessante uma ferramenta que serve para comparar resultados de diferentes modelos?
* É interessante para usuários mais avançados que poderiam fazer o que é proposto utilizando python?

# O que eu tenho a ver com isso?

* Dado que é uma ferramenta para comparação de modelos é interessante no contexto de Engenharia e Prompt, mas acredito que não se aplica para o contexto avalição de LLMs como proposto no projeto.
* A ferramenta é interessante para a comparação de modelos, mas não para a avaliação de LLMs, pois não possui métricas e/ou métodos claros para avaliação.

# Replicação

* Repositório: [github.com/ianarawjo/ChainForge](https://github.com/ianarawjo/ChainForge)
* É possível acessar a ferramenta via web: [chainforge.ai](https://chainforge.ai/)