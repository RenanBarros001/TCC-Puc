# Trabalho Conclusão de curso

#### Alunos: Renan Barros e Miriane Barros

#### Orientador: Leonardo Mendonza
---
Trabalho apresentado ao curso [BI MASTER] como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão"
!---TCC-Puc

###Resumo

Este trabalho propôs um estudo comparativo de preços entre os valores de aquisição de contratos vigentes de uma empresa do setor de Óleo e Gás e os valores praticados nas transações no mercado americano por meio do relatório Preston Pipe.
Durante a execução contratual, faz-se necessária a comparações dos preços com os valores de mercado para auxiliar na tomada de decisão de continuidade contratual ou início de um novo processo de contratação.
Para tal fim, utilizou-se técnicas e ferramentas especialmente criadas para o tratamento das bases de dados provenientes de diferentes fontes. Os resultados obtidos foram apresentados em um painel em Power BI com objetivo de facilitar a interpretação dos dados e auxiliar o decisor a optar pela alternativa mais econômica para a empresa.


###Introdução

Com o advento da pandemia por meio do COVID-19 e as variações no preço do Brent, as empresas do setor de Óleo & Gás tem adotado ações de resiliência para reduzir os seus custos totais e, assim, viabilizar a execução de projetos de uma forma mais atrativa financeiramente.
Os tubos de produção e de revestimento, denominados pela sigla OCTG (Oil Country Tubular Goods), são materiais essenciais para a construção dos poços de petróleo. Além disso, estima-se que nos reservatórios do pré-sal a sua representatividade no orçamento da construção do poço é de 20 a 30% do total.
Nesse contexto, atuar para que a aquisição desses materiais seja com o menor preço possível é significante para o aumento do Valor Presente Líquido (VPL) dos projetos.
Um dos aspectos que impactam no preço de aquisição dos tubulares é a decisão de continuidade contratual, por meio de aditivos de saldo e prazo, ou planejamento de um processo licitatório para assinatura de um novo contrato.
Para que o gestor tome essa decisão é importante conhecer os preços que os países estão adquirindo os tubulares para avaliar corretamente se o contrato vigente com o fornecedor está aderente às práticas de mercado.
Sendo assim, foi desenvolvida uma rotina de programação na linguagem Phyton para captura, processamento e organização das informações sobre o relatório de mercado Preston Pipe e criado um painel em Power BI para apresentar os resultados alcançados.

###Modelagem

Para a estruturação do banco de dados para a análise comparativa foi utilizado o processo de Extração, Transformação e Carga (ETL – Extraction, Transformation and Load), conforme descrito nos tópicos a seguir: 

1) Extração
A fase de extração, ou seja, coleta de dados, é geralmente complexa visto que os dados podem vir de diferentes fontes de informação. Para isso, deve-se utilizar uma ferramenta que possa ler os diferentes tipos de dados e integrá-los em um mesmo formato.
Os dados a serem extraídos estavam divididos em dois tipos: (1) estruturados, dados dos contratos vigentes de OCTG, que são facilmente lidos e têm uma estrutura bem definida e (2) não estruturados, dados do relatório de mercado Preston Pipe, que são armazenados sem um formato ou estrutura-padrão.
Para extrair os valores dos contratos vigentes de OCTG foi criada uma rotina (Query) no ambiente SAP para obter automaticamente os valores das Planilhas de Preços Unitários (PPU) de cada contrato. A base de dados foi armazenada em uma planilha em Excel para servir de insumo ao painel em Power BI.
O relatório de mercado Preston Pipe é um arquivo em formato PDF em que as informações dos preços dos tubulares estão apresentadas de maneira não estruturada. Sendo assim, para realizar a automação da coleta dos dados foi criada uma rotina com uso de programação em Python para extrair as informações necessárias para análise comparativa com os valores dos contratos da empresa e arquivá-la, de forma estruturada, em uma planilha de Excel (XML).
2) Transformação
Após a extração foi iniciada a transformação dos dados. A etapa de Transformação de dados também engloba o processo de Limpeza dos Dados. A transformação é necessária pois os dados que foram extraídos de diversas fontes não estão integrados, sendo assim necessário a transformação e combinação destas fontes de dados.
Nessa etapa, foram corrigidos, padronizados e tratados os desvios e inconsistências, transformando os dados de acordo com as regras do necessárias para a análise comparativa.
Os dados obtidos para a análise comparativa estavam formatados de maneira tal que não seria possível realizar a comparação. Portanto, inicialmente foi realizada a higienização dos dados de forma a garantir a sua padronização e aumentar o nível de produtividade e potencial de acerto. Na higienização foi realizada a remoção de dados duplicados, normalizar informações, remoção de espaços em branco, deixando a base seguindo um mesmo padrão.
Em seguida, foi realizada a transformação e tratativa dos dados para assegurar a mesma base comparativa em termos de unidade de medida, moeda dos preços, carga tributária e outros fatores.
3) Carga
Por fim, foi realizada a inserção dos dados em um ambiente de Power BI, que foi desenvolvida uma interface amigável em um painel para visualização mais efetiva e intuitiva da análise comparativa dos preços dos contratos de OCTG e os valores de mercado extraídos do Preston Pipe.
Ao utilizar o Power BI foi possível a conexão dos bancos de dados em um único local, possibilitando a vinculação dos conjuntos de dados para a comparação e avaliação.

###Resultados

Neste trabalho foi criado um processo de carga (ETL) utilizando a ferramenta Power BI em conjunto com Phyton para o recebimento de dados de duas fontes: preços dos contratos de OCTG e preços de aquisição no relatório de mercado Preston Pipe.
Os dados foram apresentados em um dashboard no Power BI, que possibilitou a visualização do real enquadramento dos preços dos tubos adquiridos pela empresa em relação aos valores praticados no mercado americano.


###Conclusão

Ao realizar este trabalho final com o tema proposto de Business Intelligence (BI): uso de técnicas e ferramentas para análise comparativa de custos de tubulares foi possível entender de fato a sua importância para as organizações, além de permitir o aprofundamento em conceitos relacionados ao BI.
Pode-se perceber, no entanto, que a implantação de um projeto de BI não é uma tarefa simples, dificultada, no caso em tela, pela má estruturação dos dados. O desenvolvimento de um processo de higienização dos dados aumentará a confiabilidade do banco de dados.
Espera-se que a elaboração do painel em Power BI ofereça ao decisor uma ferramenta para analisar diferentes possibilidades de negócio. Por meio da análise comparativa será possível buscar a solução possivelmente ótima para os preços de aquisição dos tubulares e, assim, reduzir o custo total dos projetos com esse item.

Mesmo com boa parte dos objetivos iniciais cumpridos, é importante ressaltar que muitas outras funcionalidades podem ser incorporadas na ferramenta, como aumentar o campo da análise comparativa considerando o histórico de aquisição dos últimos 5 anos da empresa e incorporação de outros relatórios e índices de mercado utilizados pela indústria.

---

Matrícula: 192.671.160 / 

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*

Repositório pra trabalho final BI Master PUC 2019/2

