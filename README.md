# JSON Viewer

Repositório oficial: https://gitlab.com/tenshizer0/json-viewer

## Objetivo

Este visualizador de JSON tem como objetivo atender os seguintes requisitos

1. "Abra e use" - não precisar de instalação de nenhuma ferramenta extra, além do navegador de internet que já vem por padrão nos maiores sistemas operacionais
2. Robustez - capacidade de abrir arquivos JSON consideravelmente grandes, na casa dos GiB de tamanho

## Estratégia

Para cumprir os objetivos, utilizou-se as seguintes estratégias:

* Visualização em tabela, com atributos dando título às colunas, para facilitar a visualização
* Paginação para listas com muitos itens, para evitar construir muitos elementos HTML
* Navegação em níveis, mostrando apenas os objetos que estão no mesmo nível e na mesma ramificação da árvore JSON, para evitar construir muitos elementos HTML
* Utilizando o VanillaJS para evitar a instalação de ferramentas extras

## Problemas conhecidos

1. Utiliza o JSON.parse(), tornando necessário o carregamento do arquivo inteiro para a memória, antes de que se faça o parsing
2. A visualização em tabela ajuda na visualização de objetos com mesma estrutura, mas prejudica a visualização de JSON não-estruturado