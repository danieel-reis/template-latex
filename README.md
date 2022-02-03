# template-latex
Template para dissertação e tese em Latex desenvolvido pelos Discentes do PPGCC - UFMG

## Utilização da classe no Overleaf

Para a utilização da classe no [Overleaf](https://overleaf.com) é necessário:
- Fazer o _upload_ dos arquivos `ppgccufmg.cls` e `ppgccufmg.bst` para o projeto no Overleaf e;
- O pacote `inputenc` deve ser importado passando-se o argumento `utf8` para que não haja problemas com pontuações em português. Exemplo:
  ```
  \usepackage[utf8]{inputenc}
  ```
## Utilização no TeXstudio (compilação local)

Para utilização da classe com o programa [TeXstudio](https://www.texstudio.org/), onde compila-se o documento localmente, é necessário:
- Ter os arquivos `ppgccufmg.cls` e `ppgccufmg.bst` no mesmo diretório que o arquivo `.tex` principal e;
- Recomenda-se a instalação do pacote `texlive-full`, presente na maioria das distribuições Linux (e.g., para instalar no Ubuntu, deve-se executar o comando `sudo apt install texlive-full` no terminal). 

## Documentação

As alterações realizadas na versão 1.60 por Vilar Neto não contam com documentação. Há uma issue ([#5](https://github.com/discentesppgcc/template-latex/issues/5)) aberta para que a documentação possa ser atualizada corretamente conforme a padronização do Latex. Sendo assim, para dúvidas gerais sobre a classe recomenda-se consultar a documentação da versão 1.60 (`documentos/documentacao_v1_60.pdf`). Qualquer dúvida relacionada às alterações realizadas pós versão 1.60 recomenda-se consultar a Issue [#4](https://github.com/discentesppgcc/template-latex/issues/4).

---
# Diferenças para a versão 1.60 por Vilar Neto

- A formatação de grande parte do documento foi alterada para que atendesse a todas as diretrizes para normalização de trabalhos acadêmicos da UFMG determinadas pelo Repositório Institucional da UFMG (versão 2020). Todas as alterações estão documentadas na Issue [#4](https://github.com/discentesppgcc/template-latex/issues/4).
- O formato padrão das páginas definido pela biblioteca é o de página única (ao contrário do formato de livro com páginas  esquerda e à direita). Para definir o documento como sendo de página única deve-se passar o argumento `oneside` no comando que define o tipo de documento. Exemplo:
  ```
  \documentclass[phd, oneside]{ppgccufmg}
  ```
- A data do documento agora é somente o ano, e não mais mês-ano como anteriormente. Exemplo
  ```
  \ppgccufmg{
     ...
     date={2022}
  }
  ```
  
- As palavras-chave do resumo e _abstract_, segundo as diretrizes, devem ser redigidas com a inicial maiúscula, separadas entre si com ponto final e finalizadas também com ponto final. Exemplo:

  Resumo em português:
  ```
  \ppgccufmg{
     ...
     keywords={Visão Computacional. Redes. Sabotagens.}
  }
  ```
  
  Abstract (comando `\keywords{}` passado no fim arquivo `.tex` contendo o abstract):
  ```
  \keywords{Computer Vision. Networks. Sabotage.}
  ```

## Informações adicionais

- Para as referências ficarem entre colchetes, deve-se adicionar o comando `\setcitestyle{square}` logo após `\usepackage{natbib`} e usar `\citep` ao invés de `\cite`.
- Não passar o parâmetro `square` ao incluir o pacote `natbib`, i.e., não incluir o pacote utilizando o comando `\usepackage[square]{natbib}`.


## Informações técnicas sobre a classe

- Me parece que não se pode usar o argumento `square` do pacote `natbib` (`\usepackage[square]{natbib}`), pois isto gera um erro ao compilar. Deve-se portanto incluir o pacote no arquivo `.tex` principal utilizando `\usepackage{natbib}`.
