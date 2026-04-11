---
permalink: /
title: "O Academic Pages é um modelo do GitHub Pages pronto para ser copiado, destinado a sites pessoais de caráter acadêmico"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Esta é a página inicial de um site que utiliza o modelo [Academic Pages template](https://github.com/academicpages/academicpages.github.io) e é hospedado no GitHub Pages. O [GitHub pages](https://pages.github.com) é um serviço gratuito no qual sites são criados e hospedados a partir de código e dados armazenados em um repositório do GitHub, sendo atualizados automaticamente sempre que um novo commit é feito no repositório. Este modelo foi derivado do [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/) criado por Michael Rose, e depois ampliado para oferecer suporte aos tipos de conteúdo que acadêmicos costumam ter: publicações, palestras, ensino, portfólio, posts de blog e um currículo gerado dinamicamente. Curiosamente, esses mesmos recursos também o tornam um excelente modelo para qualquer pessoa que precise apresentar um site profissional!

Você pode fazer um fork deste modelo agora mesmo, modificar as configurações e os arquivos em Markdown, adicionar seus próprios PDFs e outros conteúdos, e ter seu próprio site gratuitamente, sem anúncios!

## A data-driven personal website
======

Assim como muitos outros modelos do GitHub Pages baseados em Jekyll, o Academic Pages faz com que você separe o conteúdo do site de sua forma. O conteúdo e os metadados do seu site ficam em arquivos Markdown estruturados, enquanto vários outros arquivos compõem o tema, definindo como transformar esse conteúdo e metadados em páginas HTML. Você mantém esses diversos arquivos Markdown (.md), YAML (.yml), HTML e CSS em um repositório público no GitHub. Cada vez que você faz um commit e envia uma atualização para o repositório, o serviço [GitHub pages](https://pages.github.com/) cria páginas HTML estáticas com base nesses arquivos, que são hospedadas gratuitamente nos servidores do GitHub.

Muitos dos recursos de sistemas de gerenciamento de conteúdo dinâmico (como o Wordpress) podem ser alcançados dessa forma, utilizando uma fração dos recursos computacionais e com muito menos vulnerabilidade a ataques de hackers e DDoS. Você também pode modificar o tema à vontade sem precisar alterar o conteúdo do seu site. Se você chegar a um ponto em que tenha quebrado algo no Jekyll/HTML/CSS além de conserto, seus arquivos Markdown que descrevem suas palestras, publicações etc. estarão seguros. Você pode reverter as alterações ou até mesmo excluir o repositório e começar do zero — apenas certifique-se de salvar os arquivos Markdown! Você também pode escrever scripts que processem os dados estruturados do site, como [this one](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), que analisa os metadados em páginas sobre palestras para exibir [a map of every location you've given a talk](https://academicpages.github.io/talkmap.html).

Para usuários que precisam de funcionalidades mais avançadas, o modelo também oferece suporte às seguintes ferramentas populares:
- [MathJax](https://www.mathjax.org/) para equações matemáticas  
- [Mermaid](https://mermaid.js.org/) para criação de diagramas  
- [Plotly](https://plotly.com/javascript/) para geração de gráficos

## Getting started
======

1. Crie uma conta no GitHub, caso ainda não tenha uma, e confirme seu e-mail (obrigatório!)
1. Faça um fork deste modelo clicando no botão "Use this template" no canto superior direito: [this template](https://github.com/academicpages/academicpages.github.io)
1. Vá até as configurações do repositório (última aba à direita na barra que começa com "Code", abaixo de "Unwatch"). Renomeie o repositório para "[seu nome de usuário do GitHub].github.io", que também será a URL do seu site.
1. Configure as definições globais do site e crie conteúdo e metadados (veja abaixo — consulte também [this set of diffs](https://archive.is/3TPas), que mostra quais arquivos foram alterados para configurar [an example site](https://getorg-testacct.github.io) para um usuário com o nome "getorg-testacct")
1. Faça upload de quaisquer arquivos (como PDFs, arquivos .zip, etc.) para o diretório files/. Eles aparecerão em https://[seu nome de usuário do GitHub].github.io/files/example.pdf  
1. Verifique o status acessando as configurações do repositório, na seção "GitHub Pages"
Site-wide configuration
------
O principal arquivo de configuração do site está no diretório base em [_config.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_config.yml), que define o conteúdo das barras laterais e outros recursos globais do site. Você precisará substituir as variáveis padrão por informações sobre você e sobre o repositório do seu site no GitHub. O arquivo de configuração do menu superior está em [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml). Por exemplo, se você não tiver um portfólio ou posts de blog, pode remover esses itens do arquivo navigation.yml para que eles não apareçam no cabeçalho.

## Create content & metadata
------
Para o conteúdo do site, há um arquivo Markdown para cada tipo de conteúdo, que são armazenados em diretórios como _publications, _talks, _posts, _teaching ou _pages. Por exemplo, cada palestra é um arquivo Markdown no diretório [_talks directory](https://github.com/academicpages/academicpages.github.io/tree/master/_talks).

No topo de cada arquivo Markdown há dados estruturados em YAML sobre a palestra, que o tema irá processar para realizar várias funcionalidades interessantes. Esses mesmos dados estruturados sobre uma palestra são usados para gerar a lista de palestras na [Talks page](https://academicpages.github.io/talks), cada [individual page](https://academicpages.github.io/talks/2012-03-01-talk-1) de palestras específicas, a seção de palestras na [CV page](https://academicpages.github.io/cv) e o [map of places you've given a talk](https://academicpages.github.io/talkmap.html) (caso você execute este [python file](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) ou este [Jupyter notebook](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), que cria o HTML do mapa com base no conteúdo do diretório _talks).

**Markdown generator**

O repositório inclui [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator) que converte um CSV contendo dados estruturados sobre palestras ou apresentações em arquivos Markdown individuais, que serão formatados corretamente para o modelo Academic Pages. Os CSVs de exemplo nesse diretório são os que foram usados para criar o site pessoal em stuartgeiger.com. Meu fluxo de trabalho usual é manter uma planilha com minhas publicações e palestras, depois executar o código nesses notebooks para gerar os arquivos Markdown e, em seguida, fazer commit e enviá-los para o repositório no GitHub.

## How to edit your site's GitHub repository
------
Muitas pessoas usam um cliente git para criar arquivos em seus computadores locais e depois enviá-los para os servidores do GitHub. Se você não estiver familiarizado com git, pode editar diretamente esses arquivos de configuração e Markdown pela interface do github.com. Navegue até um arquivo (como [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md)) e clique no ícone de lápis no canto superior direito da visualização do conteúdo (à direita dos botões "Raw | Blame | History"). Você pode excluir um arquivo clicando no ícone de lixeira ao lado do ícone de lápis. Também é possível criar novos arquivos ou fazer upload de arquivos navegando até um diretório e clicando nos botões "Create new file" ou "Upload files".

Exemplo: editando um arquivo Markdown para uma palestra  
![Editing a Markdown file for a talk](/images/editing-talk.png)

Para mais informações
------
Mais informações sobre como configurar o Academic Pages podem ser encontradas em [the guide](https://academicpages.github.io/markdown/), na [growing wiki](https://github.com/academicpages/academicpages.github.io/wiki), e você também pode [ask a question on GitHub](https://github.com/academicpages/academicpages.github.io/discussions). Os [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (do qual este tema foi derivado) também podem ser úteis.
