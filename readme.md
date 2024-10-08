# Guia de usuário e desenvolvedor do appGENALIM

FGV - Innovation Lab

---

**Ao final deste manual o leitor estará apto a responder:**

*Por que a ferramenta foi criada?*

*Como operar a ferramenta?*

*Como corrigir ou modificar a ferramenta?*

**Nome do app:** *appGENALIM*

**Cliente:** *FGV - IBRE - SCI - NIP*

**Última atualização:** 28-11-2018

**Responsável:** *Fellipe Carvalho Gomes* 

Informações da sessão:

```
> sessionInfo()
R version 3.5.0 (2018-04-23)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows 7 x64 (build 7601) Service Pack 1

Matrix products: default

locale:
[1] LC_COLLATE=Portuguese_Brazil.1252 
[2] LC_CTYPE=Portuguese_Brazil.1252   
[3] LC_MONETARY=Portuguese_Brazil.1252
[4] LC_NUMERIC=C                      
[5] LC_TIME=Portuguese_Brazil.1252    

attached base packages:
[1] stats     graphics 
[3] grDevices utils    
[5] datasets  methods  
[7] base     

other attached packages:
 [1] magick_1.9         
 [2] webshot_0.5.0      
 [3] ReporteRs_0.8.10   
 [4] ReporteRsjars_0.0.4
 [5] formattable_0.2.0.1
 [6] ggplot2_3.1.0      
 [7] tibbletime_0.1.1   
 [8] readr_1.3.1        
 [9] zip_1.0.0          
[10] DT_0.5.3           
[11] tidyr_0.8.3        
[12] kableExtra_0.9.0   
[13] dplyr_0.8.0.1      
[14] purrr_0.2.5        
[15] data.table_1.11.4  
[16] shinyWidgets_0.4.8 
[17] magrittr_1.5       
[18] forecast_8.4       
[19] zoo_1.8-4          
[20] lubridate_1.7.4    
[21] stringr_1.3.1      
[22] rmarkdown_1.10     
[23] knitr_1.20         
[24] shiny_1.2.0        

loaded via a namespace (and not attached):
 [1] tseries_0.10-45  
 [2] httr_1.3.1       
 [3] jsonlite_1.6     
 [4] viridisLite_0.3.0
 [5] uroot_2.0-9      
 [6] R.utils_2.6.0    
 [7] assertthat_0.2.0 
 [8] TTR_0.23-3       
 [9] yaml_2.2.0       
[10] gdtools_0.1.7    
[11] pillar_1.3.1     
[12] backports_1.1.2  
[13] lattice_0.20-35  
[14] glue_1.3.0       
[15] quadprog_1.5-5   
[16] uuid_0.1-2       
[17] digest_0.6.18    
[18] promises_1.0.1   
[19] rvest_0.3.2      
[20] colorspace_1.4-1 
[21] R.oo_1.22.0      
[22] htmltools_0.3.6  
[23] httpuv_1.5.0     
[24] plyr_1.8.4       
[25] timeDate_3043.102
[26] pkgconfig_2.0.2  
[27] xtable_1.8-2     
[28] scales_1.0.0     
[29] later_0.8.0      
[30] officer_0.3.2    
[31] tibble_2.0.1     
[32] withr_2.1.2      
[33] urca_1.3-0       
[34] nnet_7.3-12      
[35] lazyeval_0.2.1   
[36] cli_1.0.1        
[37] quantmod_0.4-13  
[38] crayon_1.3.4     
[39] mime_0.6         
[40] evaluate_0.10.1  
[41] R.methodsS3_1.7.1
[42] fansi_0.4.0      
[43] nlme_3.1-137     
[44] xts_0.11-1       
[45] xml2_1.2.0       
[46] tools_3.5.0      
[47] hms_0.4.2        
[48] munsell_0.5.0    
[49] packrat_0.4.9-3  
[50] compiler_3.5.0   
[51] tinytex_0.8      
[52] rlang_0.3.2      
[53] grid_3.5.0       
[54] rstudioapi_0.8   
[55] htmlwidgets_1.3  
[56] base64enc_0.1-3  
[57] gtable_0.2.0     
[58] fracdiff_1.4-2   
[59] curl_3.3         
[60] R6_2.4.0         
[61] rvg_0.1.9        
[62] utf8_1.1.4       
[63] rprojroot_1.3-2  
[64] rJava_0.9-10     
[65] stringi_1.2.4    
[66] parallel_3.5.0   
[67] Rcpp_1.0.0       
[68] png_0.1-7        
[69] tidyselect_0.2.5 
[70] xfun_0.3         
[71] lmtest_0.9-36   
```


# Introdução 

---

Este documento é um manual 2 em 1 que busca atender usuários e desenvolvedores do aplicativo appGENALIM.

  * A seção [Como usar a ferramenta? (para **usuários**)](#usuario) é voltada aos **usuários** que acessarão a ferramenta sem precisar entender o que há por trás dela. 

  * A seção [Como editar a ferramenta? (para **desenvolvedores**)](#desenvolvedor) é destinada a **desenvolvedores** que buscam modificar a ferramenta, seja para fazer alguma correção ou melhoria.
  
  Os autores buscaram construir a ferramenta de tal modo que o funcionamento básico fosse intuitivo aos usuários. Acreditando no sucesso desse objetivo, imagino que você seja um **desenvolvedor** em busca de informações sobre a edição do aplicativo. Este documento não tem como finalidade substituir um treinamento que capacite o uso avançado das ferramentas utilizadas, porém diversas referências para consultas serão deixadas ao longo do documento.

**Hitchhiker, grab your towel and don't panic!** O manual foi produzido com a finalidade de te guiar em qualquer modificação da ferramenta sem que você precise da ajuda de ninguém, mas, caso necessário, a equipe de desenvolvedores ficará muito feliz em responder seu e-mail:

  * <gustavo.lopo@fgv.br>
  * <fellipe.gomes@fgv.br>
  * <luiz.passos@fgv.br>
  
Críticas e sugestões também são bem-vindas.

## Síntese do projeto

Todo mês o NIP produz um relatório para avaliar o índice de gêneros alimentícios e bebidas. Antes da existência dessa ferramenta, os relatórios eram produzidos de maneira manual e envolviam basicamente as seguintes etapas:

  1. Obter os dados manualmente pelo sistema
  2. Realizar as análises
  3. Confeccionar os gráficos e tabelas
  4. Escrever e formatar o relatório
  5. Exportar o relatório em PDF
  
Como os relatórios gerados a cada mês contêm os mesmos objetos (gráficos de linhas, barras e tabelas), variando apenas a data de referência da amostra coletada, projetou-se a automação das etapas de 1 a 5. Espera-se com isso acelerar a produção dos relatórios e evitar possíveis erros decorrentes de manipulação humana dos arquivos.

### Limitações atuais do aplicativo (21/12/2018)

Antes de prosseguir, é importante que você saiba que a consulta direta ao banco de dados[^db] via SQL[^SQL] ainda está **indisponível**. No momento ela só está disponível para os [desenvolvedores do aplicativo](#desenvolvedores_bbmp).

A razão disso é que o acesso ainda está em desenvolvimento e por enquanto só é possível o acesso local de forma individual. Futuramente esperamos que este acesso possa ser feito de forma geral. Isto é, qualquer pessoa com um login poderá utilizar o aplicativo hospedado no servidor.

### Próximos passos para o desenvolvimento

O acesso à base de dados no servidor ainda está indisponível e por conta disso as seguintes tarefas ainda estão pendentes e devem ser concluídas após a [liberação do acesso geral](#limitações).

  * Os dados obtidos do banco de dados via SQL são (d-1), isto é, são os dados de preço do dia anterior. Solicitar a TIC os dados disponibilizados em d, isto é, no dia para que o relatório gere os resultados mais atuais possíveis.
  * Combinar com a área que faz uso do aplicativo o momento para o fechamento dos cálculos realizados na base SIS[^SIS].
  

# Como usar a ferramenta? (para **usuários**)

---

## Obter dados

**Atenção:** Como a conexão direta com o banco de dados ainda **não está disponível**, será necessário fazer o input manual. São 5 arquivos de entrada no total - 3 arquivos exportados do SIS e 2 séries do IGP - veja:
 
  * ALIPRAT (SIS)
  * ALIATA (SIS)
  * ALIVAR (SIS)
  * IPA (nº da série: 1427032)
  * IPC-RJ (nº da série: 1406445)
  
Os nomes destes arquivos devem estar nomeados exatamente como (letras minúsculas, sem espaço e em formato `csv`):

  - `aliata.csv`
  - `aliprat.csv`
  - `alivar.csv`
  - `ipa.csv`
  - `ipcrj.csv`
  
## Manipulação inicial dos dados obtidos  

Exemplo de como são estes arquivos e como manipulá-los:

![](src/img_readme/rbind1.gif)

*Exemplo de manipulação de: ALIATA, ALIVAR, ALIPRAT*

![](src/img_readme/rbind2.gif)

*Exemplo de manipulação de: IPA, IPCRJ*

Portanto, para ambos os casos, cada nova base de dados obtida por mês deverá ser acrescentada ao final da última linha da base csv que contém os resultados dos meses passados.

## Processamento dos dados 

Para dar início à produção, abra o aplicativo, insira a **data** que constará na carta e insira o **número do relatório** que aparecerá na capa do pdf (note que essas instruções também são apresentadas no corpo do aplicativo).

Além da data e do número do relatório insira os dados que você acaba de manipular no passo anterior e insira no app da seguinte forma:

![](src/img_readme/processar_local.gif)

Pressionar o botão `Gerar Relatório` para que a rotina de análises seja executada.

Quando a tarefa terminar a seguinte mensagem será exibida:

![](src/img_readme/sucesso.gif)

Após a mensagem de que todos os objetos do relatório foram criados com sucesso, basta clicar em `Download` e fazer o download do relatório:

![](src/img_readme/download.gif)

## Produto final

Ao final do processo, o relatório disponível para a entrega para o cliente terá a seguinte forma:

![](src/img_readme/relatorio_final.gif)


# Como editar a ferramenta? (para **desenvolvedores**) 

---

## Quem está apto a editar esse aplicativo?

O aplicativo foi pensado com dois conceitos desafiadores por trás:

* O aplicativo deverá ser facilmente editado.
* A edição não demandará um especialista em TI, podendo ser feita por um "cientista de dados iniciante". Como diria o famoso lema do Chef Gusteau, "qualquer um pode cozinhar" ([spoiler](https://www.youtube.com/watch?v=wasHFSVP6vQ/)).

Essas premissas foram buscadas até as últimas consequências e esperamos que um estagiário dedicado com pouco tempo de faculdade esteja apto a cozinhar. Segue descrição dos conhecimentos mínimos para cada tarefa.

Boa vontade, e talvez um pouco de sagacidade, será suficiente para editar a carta do relatório ou qualquer trecho de texto corrido. Conhecimentos em programação não serão necessários aqui.

Conhecimento básico em linguagem de programação [R](https://www.r-project.org/) será necessário, caso deseje modificar alguma manipulação de dados e conhecimento básico da linguagem [$\LaTeX$](https://www.latex-project.org/), caso deseje modificar o documento PDF.

Para usuários mais experientes, que tenham interesse em modificar funcionalidades da ferramenta, será necessário algum conhecimento em [Shiny](https://shiny.rstudio.com/) e no caso da necessidade de modificar o estilo/aparência da ferramenta será necessário conhecimento básico da técnica de linguagem de programação web [CSS](https://pt.wikipedia.org/wiki/Cascading_Style_Sheets).

Isso é possível devido à arquitetura do aplicativo que pode ser segmentada em 3 compartimentos:

  i) Código para gerar os objetos do relatório (gráficos, tabelas, figuras e outros).
  ii) Código para compilar o documento PDF com os objetos gerados.
  iii) Código para gerar a interface amigável ao usuário que irá operar a ferramenta.

## Estrutura do diretório

Veja a seguir como a pasta está organizada e sua descrição:
 
```
.
├─ appgenalim.Rproj.R            (Arquivo para abrir e organizar o projeto)        
├─ global.R                      (Configuracoes gerais do app)        
├─ ui.R                          (Interface do usuario)        
├─ server.R                      (Servidor do app)        
├─ src/                          (dependencias p/ processamento do app)
│   └─ img_output/               (Imagens geradas pelo script generate_image_by_local.R)
│   └─ img_readme/               (Imagens para readme)
│   └─ temp_zip/                 (Arquivos temporarios para download no .zip de apoio)
│   └─ templates/                (Imagens para template do relatorio pdf final)
│   └─ functions/                (Funcoes desenvolvidas para o uso do app)
│   └─ generate_image_by_local.R (Script que gera imagens do relatorio)
│   └─ report.Rmd                (Arquivo Rmarkdown que compila o relatorio .pdf)
├─ www                           (Dependencias p/ customizar o app)
│   └─ css                       (Pasta com arquivo css)
│   └─ fonts                     (Arquivos de formatacao do css)
│   └─ images                    (Imagens utilizadas no css)
│   └─ template.html             (Template html para app)
├─ data                          (Backup de arquivos utilizados como carga para o app e outputs)
└─ readme.md                     (Este manual)
```

Os arquivos que você provavelmente terá interesse em editar são:

  * **global.R**: Arquivo que contem configurações de inicialização do app como carregar pacotes, carregar dependências, informações de login etc
  * **ui.R**: É o script que compila a interface do usuário
  * **server.R**: É o script que renderiza os scripts de acordo com a interação do usuário
  * **generate_image_by_local.R**: Script que é renderizado quando o usuário pressiona o botão `Gerar Relatório`, este arquivo você deve editar caso deseje fazer alterações nos gráficos e tabelas do relatório, você verá mais informações em: [Gráficos](#graficos) e [Tabelas](#tabelas)
  * **report.Rmd**: é o arquivo que você deve editar caso deseje fazer alguma alteração no texto ou na aparência do arquivo PDF, você verá mais informações em: [Conteúdo do texto](conteudo_texto)

## Como o aplicativo funciona?

O esquema seguinte sintetiza a lógica do aplicativo:

![](src/img_readme/pipeline_app.png)

É possível notar que na primeira etapa ocorre a **Entrada** dos dados, que pode ser por acesso direto ao banco de dados (que se encontra **indisponível** até o momento) ou através do input manual dos dados (como apresentado na seção [Como usar o aplicativo](como_usar_o_app)).

Na parte da **Execução** do app temos os scripts `ui.R`, `server.R` e `global.R` que contém informações da interface do usuário e do servidor e chama as rotinas `generate_image_by_local.R` e `report.Rmd` que criam os objetos para os relatórios. Esses objetos criados são salvos temporariamente na pasta `src/img_output/`.

Junto com o template do relatório, que está na pasta `src/templates/template_pdf`, esses objetos são combinados no script final `report.Rmd` que gera o documento `report.pdf` para download na **Saída** do app.

# Realizar alterações

---

### Ambiente do RStudio 

A linguagem de programação R, como muitas outras linguagens de programação, trabalha com o conceito de [pacotes](http://r-pkgs.had.co.nz/intro.html) que reúnem códigos, dados, documentação, testes e são fáceis de compartilhar com outras pessoas.

Neste projeto foram utilizadas versões específicas de pacotes do R e suas versões podem ser conferidas no documento ao final deste documento.

### Gráficos 

Referência para ajudar a entender como utilizar o ggplot2 e gerar gráficos elegantes: <https://bookdown.org/rdpeng/exdata/the-ggplot2-plotting-system-part-1.html>

Os gráficos do texto são gerados pelo script `generate_image_by_local.R`. No início do script é feita a leitura e a manipulação dos dados e em seguida inicia-se a seção de `# #### Figuras #### #` onde as figuras do relatório são geradas (na mesma ordem que aparecem no relatório). Veja um esquema para facilitar o entendimento:

![](src/img_readme/pipeline_figuras.png)
    
Os arquivos gerados aqui são temporariamente armazenados na pasta: `src/img_output` para serem obtidos posteriormente e inseridos no relatório PDF

### Tabelas

Referência para ajudar a entender como utilizar o Flextable para gerar as tabelas: <https://davidgohel.github.io/ReporteRs/articles/FlexTable.html>

As tabelas são geradas de maneira muito semelhante aos gráficos. Todas as tabelas que aparecem no relatório PDF são geradas pelo script: `generate_image_by_sql.R`, também na seção `#### Figuras ####`, como mostrado no esquema a seguir:

![](src/img_readme/pipeline_figuras2.png)

Os arquivos gerados aqui também são temporariamente armazenados na pasta `src/img_output` para serem obtidos posteriormente e inseridos no relatório PDF.

### Conteúdo do texto


No momento que os dados já foram obtidos e todos os objetos que irão fazer parte do relatório já estão prontos, chega a hora de juntar tudo em um único arquivo RMarkdown. Mais informações sobre RMarkdown na página oficial em <https://rmarkdown.rstudio.com/> e no livro do autor do pacote: <https://bookdown.org/yihui/rmarkdown/>.

**Mas por que RMarkdown?**

Arquivos RMarkdown (com a extensão `.Rmd`, como `report.Rmd`) permitem que o desenvolvedor una em um único documento “pedaços” de texto (Utilizando linguagens apropriadas para alta formatação, como `Markdown`,`LaTeX`, `CSS` dentre outros ) e “pedaços” de código (como `R`, `Python`, `SQL` etc), possibilitando a criação de um documento que faz o uso de rotinas elaboradas por diferentes desenvolvedores, utilizando diferentes linguagens de programação e obtendo o melhor de cada uma delas.


Para alterações no conteúdo do texto, basta abrir o arquivo `report.Rmd` e fazer as alterações necessárias no texto e clicar em `Run app`, como ilustrado no gif da seção [Como usar o aplicativo](#como_usar_o_app)

![](src/img_readme/pipeline_texto.png)

### Aparência do documento

Para alterar as imagens do template (cabeçalho, rodapé, logo, etc.)  acesse a pasta `dep/img_template_pdf` e substitua a imagem indesejada por um arquivo  homônimo com a mesma extensão.

# Como fazer novas publicações no Servidor Interno da FGV (em um contêiner Docker)

---

Para hospedar uma nova versão do aplicativo no servidor interno da FGV em um contêiner Docker serão necessários alguns passos:

1.	Tenha certeza de todas as funcionalidades da ferramenta estão funcionando de acordo com o esperado
2.	Após isso, junte todos os arquivos necessários para o funcionamento em um arquivo .zip
3.	Envie este arquivo zip para o responsável na TIC pelas publicações (em caso de dúvidas à quem enviar, [entre em contato com os desenvolvedores](#desenvolvedores_bbmp))
4.	Caso o arquivo seja grande demais para enviar por e-mail, coloque os arquivos em um pendrive e leve-os para o responsável pela publicação
5.	Lembre-se sempre de enviar junto ao zip um documento .txt com as informações da última sessão R na qual o aplicativo funcionou (para obter tal informação, rode no console do R o comando: `sessionInfo()`

# FAQ

---

*Quais precauções devo tomar ao editar o aplicativo?*

Como mencionado na seção [Como fazer as alterações mencionadas com segurança?](#fazer_alteracoes) é altamente recomendado que o responsável pelas alterações desta ferramenta faça uma cópia de segurança da última versão funcionando (Selecionar, Ctrl+C, Ctrl+V).

*Como editar a carta?*

  * Releia a seção [Conteúdo do texto](#conteudo_texto)

*Como editar a imagem da capa?*

  * Releia a seção [Conteúdo do texto](#conteudo_texto)

*Como mudar o rodapé ou cabeçalho?*

  * Releia a seção [Conteúdo do texto](#conteudo_texto)

*Como alterar uma figura do relatório?*

  * Releia a seção [Gráficos](#graficos)

*Como mudar um pedaço de texto do relatório?*

  * Releia a seção [Conteúdo do texto](#conteudo_texto)

*Como sei se minha edição no código deu certo?*

  * Releia a seção [Como testar as alterações?](#testar_alteracoes)

*Estou com problemas com os pacotes do R, como resolver?*

  * Releia a seção [Ambiente do RStudio](#ambiente_rstudio)

# Autores

---

O aplicativo foi desenvolvido pelo BBMP da FGV IBRE. Trabalharam nesse projeto:

  * Gustavo Lôpo Andrade
  * Fellipe Gomes
  * Luiz Fernando Passos
  
*Li tudo e ainda estou inseguro para editar a ferramenta.*

  * Leia novamente, pesquise sua dúvida no [Stackoverflow](https://stackoverflow.com/), [deixe sua dúvida para o desenvolvedor do pacote no Github](https://help.github.com/articles/creating-an-issue/), leia as documentações dos pacotes no [help do R](https://www.r-project.org/help.html), pesquise no [Google do R](https://rseek.org/)... Respire fundo e may the force be with you!
  
# Glossário

[^SIS]: Sistema de Índices Setoriais: é um local onde são calculados índices. 

[^db]: O termo genérico "banco de dados" diz respeito ao armazenamento de informações de uma forma geral. Geralmente um software que é instalado em um computador (servidor) e tem a função de gerenciar um ou mais bancos de dados.

[^SQL]: A SQL — Structured Query Language, ou linguagem estruturada de consultas — é a linguagem padrão dos chamados Bancos de Dados Relacionais que, por sua vez, são bancos de dados estruturados em forma de colunas e linhas, também chamadas de tuplas, tendo seus dados armazenados em tabelas.

[^input]: O termo é muito utilizado na área da Tecnologia da Informação (TI). Na área da Tecnologia da Informação, existem três fases necessárias para o desenvolvimento de um trabalho: a entrada (INPUT), o processamento e a saída (OUTPUT). A fase de entrada é caracterizada pelo ato de fornecer os dados que o computador irá trabalhar durante o processamento para, finalmente, produzir as informações de saída.