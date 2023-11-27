Title: Projeto: gerando sites estáticos com Python
Date: 2023-11-23
Category: Tecnologia
Slug: projeto-gerando-sites-estáticos-com-python


Este blog foi feito como Projeto Final do Módulo 2 (Versionamento e Arquivos de Marcação) do curso de DevOps no Vem Ser Tech, parceria entre a Ada Tech e o iFood.

A ideia gira em torno de utilizar a linguagem Python para converter arquivos de marcação (no caso desse blog, Markdown) em um site estático/blog a ser hospedado no Github Pages por meio do Github Actions de forma automatizada. Para isso, optou-se por utilizar o SSG (Static Site Generator/Gerador de Site Estático) [Pelican](https://docs.getpelican.com/en/stable/).

## Início do projeto

Inicialmente, criou-se um repositório remoto "brian-schneider.github.io" no Github, pois esse blog será hospedado como o site principal do Github Pages, e, para isso, seu nome deve ser o mesmo da URL base desse serviço, sendo o mesmo baseado no nome de usuário da conta.

Em seguida, clonou-se esse repositório localmente e criou-se mais duas branchs além da própria main já existente: a "feature/blog" para trabalhar na real criação do blog, e uma "hotfix" para correções pontuais no projeto.

Agora, com o Python 3.8 instalado na máquina e dentro desse repositório recém criado, criou-se um arquivo "requirements.txt" para listar as depedências que serão instaladas no projeto. Assim, o conteúdo desse arquivo é:

```plaintext
pelican[Markdown]==4.5.4
beautifulsoup4==4.9.3
MarkupSafe==1.1.1
importlib-metadata<5.0
pelican-neighbors==1.2.0
```

Onde:

- pelican: gerador de Sites Estáticos baseado em Python;
- beautifulsoup4: pacote Python para análise de documentos HTML e XML. Necessário para alguns dos plugins do pelican;
- MarkupSafe: pacote responsável por criar escapes de caracteres para utilizá-los em HTML e XML, evitando ataques de injeção na aplicação;
- importlib-metadata: biblioteca que fornece acesso aos metadados dos pacotes instalados;
- pelican-neighbors: plugin do Pelican que adiciona a links de Próximo/Anterior aos artigos.

