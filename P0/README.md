# P0 - primalGit
## Use de LLM para resumir o que tem em cada diretório git do meu pc

### Introdução
Sou uma pessoa criativa e com muitas necessidades igual todo mundo
quando me deparo com a urgência de obter o objeto necessitado, como a maioria, 
procuro soluções que estejam dentro do meu orçamento, infelizmente como o mesmo 
é muito limitado, tenho que sempre colocar a  mão na massa para resolver.

O primalGit (pg) vem para me ajudar a resolver essa necessidade que é saber lendo apenas um texto
todos os projetos que já desenvolvi no passado, assim sei exatamente, o que está em cada diretório 
do meu git e github. Como não quero que os dados sejam lidos IA não locais, irei
desenvolver o mesmo utilizando o modelo gemma3.

### Fluxo de trabalho
O pg é uma aplicação cli que gera um relatório em formato markdown com o resumo de no máximo 100 caracteres sobre o projeto.
Ele faz isso percorrendo cada diretório e coletando os 1200 caracteres inicias do arquivo README.md , caso não tenha o mesmo
o pg retorna o endereço relativo e não relativo do diretório e a mensagem "não tem o README.md -> faça o README.md e rode novamente".

### Metodologia
O pg envia por stream para a llm gemma3 os primeiros 1200 caracteres e pega o retorno do mesmo e acrescenta no arquivo relatorio.md no diretório raiz onde fica o diretório do git
O sistema será desenvolvido em python 3.14.10 utilizando ambiente virtual.
O acesso da linguagem llm será feita por api local 
