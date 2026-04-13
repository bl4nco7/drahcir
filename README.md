# Academic Pages
**Academic Pages é um template do GitHub Pages para sites pessoais e profissionais orientados a portfólio.**

![Exemplo do template Academic Pages](images/themes/homepage-light.png "Exemplo do template Academic Pages")

# Primeiros Passos

1. Crie uma conta no GitHub, caso ainda não tenha, e confirme seu e-mail (obrigatório!)
1. Clique no botão "Use this template" no canto superior direito.
1. Na página "New repository", insira o nome do seu repositório público como "[seu usuário do GitHub].github.io", que também será a URL do seu site.
1. Edite a configuração geral do site em `_config.yml` e verifique se o `url` é o mesmo que você definiu no passo anterior e se `repository` reflete o caminho correto do seu repositório.
1. Adicione o conteúdo do seu site e envie arquivos (como PDFs, arquivos .zip, etc.) para o diretório `files/`. Eles estarão disponíveis em https://[seu usuário do GitHub].github.io/files/exemplo.pdf.
1. Verifique o status acessando as configurações do repositório, na seção "GitHub Pages".
1. (Opcional) Use os notebooks Jupyter ou scripts Python na pasta `markdown_generator` para gerar arquivos markdown de publicações e apresentações a partir de um arquivo TSV.

Veja mais informações em https://academicpages.github.io/

### Tutoriais Adicionais

Tutoriais adicionais para trabalhar com o template Academic Pages podem ser encontrados nos seguintes sites:
- https://jayrobwilliams.com/posts/2020/06/academic-website/

## Executando localmente

Quando você estiver trabalhando inicialmente no seu site, é muito útil poder visualizar as alterações localmente antes de enviá-las para o GitHub. Para trabalhar localmente, você precisará:

1. Clonar o repositório e fazer as atualizações conforme descrito acima.

### Usando uma IDE diferente
1. Certifique-se de que você tem ruby-dev, bundler e nodejs instalados
    
    Na maioria das distribuições Linux e no [Windows Subsystem Linux](https://learn.microsoft.com/en-us/windows/wsl/about) o comando é:
    ```bash
    sudo apt install ruby-dev ruby-bundler nodejs
    ```
    Se você vir o erro `Unable to locate package ruby-bundler`, `Unable to locate package nodejs`, execute o seguinte:
    ```bash
    sudo apt update && sudo apt upgrade -y
    ```
    depois tente executar `sudo apt install ruby-dev ruby-bundler nodejs` novamente.

    No MacOS os comandos são:
    ```bash
    brew install ruby
    brew install node
    gem install bundler
    ```

1. Execute `bundle install` para instalar as dependências Ruby. Se ocorrerem erros, exclua o arquivo `Gemfile.lock` e tente novamente.

    Se você vir erro de permissão como `Fetching bundler-2.6.3.gem ERROR:  While executing gem (Gem::FilePermissionError) You don't have write permissions for the /var/lib/gems/3.2.0 directory.` ou `Bundler::PermissionError: There was an error while trying to write to /usr/local/bin.`
    Instale as Gems localmente (recomendado):
    ```bash
    bundle config set --local path 'vendor/bundle'
    ```
    depois tente executar `bundle install` novamente. Se funcionar, você deverá ver uma pasta chamada `vendor` e `.bundle`.

1. Execute `jekyll serve -l -H localhost` para gerar o HTML e servi-lo em `localhost:4000`. O servidor local irá reconstruir automaticamente e atualizar as páginas quando houver mudanças em arquivos Markdown (*.md) e HTML. Já alterações no template principal e na configuração (como `_config.yml`) exigem parar e reiniciar o Jekyll.
    Você também pode tentar `bundle exec jekyll serve -l -H localhost` para garantir que o Jekyll use as dependências específicas da sua máquina local.

Se você estiver usando Linux, pode ser necessário instalar algumas dependências adicionais antes de conseguir executar localmente: `sudo apt install build-essential gcc make`

## Using Docker

Working from a different OS, or just want to avoid installing dependencies? You can use the provided `Dockerfile` to build a container that will run the site for you if you have [Docker](https://www.docker.com/) installed.

You can build and execute the container by running the following command in the repository:

```bash
chmod -R 777 .
docker compose up
```

You should now be able to access the website from `localhost:4000`.

### Using the DevContainer in VS Code

If you are using [Visual Studio Code](https://code.visualstudio.com/) you can use the [Dev Container](https://code.visualstudio.com/docs/devcontainers/containers) that comes with this Repository. Normally VS Code detects that a development container configuration is available and asks you if you want to use the container. If this doesn't happen you can manually start the container by **F1->DevContainer: Reopen in Container**. This restarts your VS Code in the container and automatically hosts your academic page locally on http://localhost:4000. All changes will be updated live to that page after a few seconds.

# Maintenance

Bug reports and feature requests to the template should be [submitted via GitHub](https://github.com/academicpages/academicpages.github.io/issues/new/choose). For questions concerning how to style the template, please feel free to start a [new discussion on GitHub](https://github.com/academicpages/academicpages.github.io/discussions).

This repository was forked (then detached) by [Stuart Geiger](https://github.com/staeiou) from the [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/), which is © 2016 Michael Rose and released under the MIT License (see LICENSE.md). It is currently being maintained by [Robert Zupko](https://github.com/rjzupkoii), and additional maintainers would be welcome.

## Bugfixes and enhancements

If you have bugfixes and enhancements that you would like to submit as a pull request, you will need to [fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo) this repository as opposed to using it as a template. This will also allow you to [synchronize your copy](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork) of the template to your fork as well.

Unfortunately, one logistical issue with a template theme like Academic Pages that makes it a little tricky to get bug fixes and updates to the core theme. If you use this template and customize it, you will probably get merge conflicts if you attempt to synchronize, although [rebasing](https://git-scm.com/docs/git-rebase) the changes from this template will work along with manually [cherry picking](https://git-scm.com/docs/git-cherry-pick) the relevant commits. If you are not comfortable with the Git command line, you can save your various `.yml` configuration files and Markdown files, delete the repository, and fork it again. 

---
<div align="center">
    
![pages-build-deployment](https://github.com/academicpages/academicpages.github.io/actions/workflows/pages/pages-build-deployment/badge.svg)
[![GitHub contributors](https://img.shields.io/github/contributors/academicpages/academicpages.github.io.svg)](https://github.com/academicpages/academicpages.github.io/graphs/contributors)
[![GitHub release](https://img.shields.io/github/v/release/academicpages/academicpages.github.io)](https://github.com/academicpages/academicpages.github.io/releases/latest)
[![GitHub license](https://img.shields.io/github/license/academicpages/academicpages.github.io?color=blue)](https://github.com/academicpages/academicpages.github.io/blob/master/LICENSE)

[![GitHub stars](https://img.shields.io/github/stars/academicpages/academicpages.github.io)](https://github.com/academicpages/academicpages.github.io)
[![GitHub forks](https://img.shields.io/github/forks/academicpages/academicpages.github.io)](https://github.com/academicpages/academicpages.github.io/fork)
</div>
