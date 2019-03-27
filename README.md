# Labtrans-front-end
Tecnologias utilizadas:
  JSF - Utilizada devido à sua preferência para o projeto e devido à experiência (breve) anterior.
  Primefaces - Utilizada devido à sua simplicidade e possbilidade de estilização de páginas, e devido a experiência anterior.
  Ajax - Utilizada como necessidade para a renderização e atualização de componentes sem troca de páginas
  JavaScript - Utilizada brevemente dentro do Primefaces para a renderização client-side de componentes já estabelecidos
  
  Funcionamento:
    Listagem de reservas -
      gerenciada pela página listar.xhtml (aberta como listar.jsf).
      Na abertura da página, todas as reservas são listadas.
      Todas as reservas podem ser selecionadas individualmente (também possúi caixa para seleção de todas) através de caixas de seleção       na parte esquerda da lista.
    Edição de registro na listagem
      Também na página listar.xhtml.
      Ao clicar os dados da linha selecionada na listagem de dados (o primeiro selecionado, caso sejam vários) são atribuídos a uma           dialog window similar à página de cadastros para a edição.
      Os dados são enviados ao banco de dados e atualizados conforme seu ID (chave primária, auto-incrementada).
    Exclusão de registro na listagem
      Botão de exclusão na página listar.
      Botão de exclusão abre um dialog window com os dados à serem processados e com a opção de cancelar operação ( Botão "Não" - volta         à página de listar) ou de confirmar a operação (Botão "Sim" - envia os IDs para serem processados).
      Envia os IDs de todas as linhas selecionadas para a função de exclusão, a função cria a sintaxe SQL para cada individual ID             recebido e às envia ao banco de dados para processamento, 1 a 1 em sequência.
    Cadastrar nova reserva
      Página cadastrar.xhtml
      possúi formulário com entradas de texto para cada informação a ser enviada ao banco, todas exceto seleção de café e descrição são       consideradas obrigatórias antes do envio do formulário.
      Envio do formulário é processado pelo beans Controlador e enviado ao banco de dados para a entrada.
      as áreas de Responsável e Descrição são simples caixas de texto para inserção.
      Filial a ser escolhida é um menu de seleção única com valores pré-configurados no back-end.
      Sala a ser escolhida é um menu de seleção única, baseada na filial escolhida anteriormente, com valores pré-configurados no 
      back-end.
      Data e hora de início são escolhidas por um calendário com seleção de dias, horas e minutos pré-formatadas para yyyy-MM-dd HH:mm
      para consistência de dados.
      Data e hora de fim são selecionadas em um menu de escolha única com botões de 1, 2, 3, 4, 6 e 8 horas de reunião, as quais são           utilizadas nas funções de banco de dados (adicionadas em cima da data/hora de início) para servirem efetivamente como datas e hora       de fim sem ocupar mais espaço no banco.
      Café constitui de uma caixa de seleção e um Spinner que vai de 0 a 35, caso a caixa de seleção esteja ativa o número do spinner é       enviado ao banco em um número inteiro com o que foi selecionado, caso a caixa não esteja selecionada, o valor do spinner enviado é       forçado a ser 0, efetivamente comunicando que não há necessidade de café.
      No aperto do botão de Nova Reserva e na função de inserção de dados, a função inicialmente faz uma pesquisa de SELECT no banco de       dados para a checagem de existência de alguma entrada entre a data/hora inicial e a data/hora final, caso exista, a função               imediatamente retorna falsa e não cria uma nova entrada.
    
  
  Dificuldades Encontradas: 
    JSF é naturalmente inviável a ser utilizado para construção RESTful devido à sua natureza de manipulação de dados, como RESTful não foi considerado como um requisito funcional, tal não foi cumprido devido à viabilidade.
    Apesar de possuír 1 ano de experiência com Java EE, JSF foi um certo desafio à se aprofundar porém o aprendizado foi flúido e trouxe resultados rápidamente para a construção do sistema.
    A escolha de layout e aparência das páginas fica por conta do programador, por banana ser uma empresa fictícia, e sem base alguma apesar de providenciar liberdade para a criatividade também se aumenta a dificuldade de desenvolvimento por não possuir escopo de projeto.
  
  
  23/03 - Páginas iniciais (vazias ou quase) criadas, projeto estabelecido
  24/03 - Página de cadastro em construção - ligação com beans para seleção das listas e atribuição de variáveis
          Arquivos Jar do primefaces e JSTL inseridos na pasta WebContent/WEB-INF/lib
          Cabeçalho e Rodapé nos Templates de JSF iniciados (pendendo mudanças).
          Corrigidos diversos erros no código, páginas agora são renderizadas corretamente.
  25/03 - Construída boa parte da página de cadastros, diversos erros corrigidos.
          Projeto reiniciado agora como JSF 2.2 (Antes estava como JSF 2.0)
          Bibliotecas substituídas devido à inutilidade e incompatibilidade
          Adicionado css base para ser utilizado nas páginas futuramente
  26/03 - Terminada página de cadastros, implementação de cadastramento de reuniões completa, pendente estilização de página.
          (re)Criada página de listagem, possúi uma dataTable que recebe todos os dados da tabela
          Tabela da página de listagem agora é interativa, possúi caixas para seleção múltipla de fileiras
          Página de listagem em torno de 70% completa, em breve será a ligação para as funções de edição e exclusão de registros.
          Diversos pequenos ajustes.
  27/03 - Páginas de listagem contendo funções de seleção, edição e exclusão de dados completa, pendente estilização
          Pendente pequeno ajuste com a seleção de local na seção de edição de dados, única função restante para a funcionalidade total do           sistema.
          Diversos pequenos ajustes.
          
     
