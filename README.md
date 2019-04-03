- **Classes**:
  - *Iface*: Essa classe funciona como o banco de dados da comunidade, sendo nela onde contém todas as contas e comunidades criadas pelos usuários, assim como é responsavel pela função que permite que o usuário faça login.
  - *Account*: Essa classe é a conta do usuário em si, contém todas as informações do usuário, como: nome, senha, apelido, amigos, comunidades, etc.
  - *Community*: Essa classe funciona como as comunidades da maioria das redes socias, ela é criada por um usuário e permite que ele gerencie-a, podendo adicionar ou remover membros, entre outras funcionalidades.
  - *Message*: Essa classe é basicamente uma mensagem enviada de um usuário para outro, contendo o nome do remetente e o corpo da mensagem.
  - *Iterator (Interface)*: É a interface que permite que o padrão Iterator seja aplicado, contém todas os métodos que serão necessários para essa aplicação.
  - *HashMapIterator & ArrayListIterator*: Estas duas classes implementam a interface Iterator, elas permitem que o usuário navegue através das coleções sem necessáriamente saber como elas foram implementadas, através apenas dos métodos hasNext() e next().
  
- **Principais Métodos**:
  - *Iface*:
    - getInstance(): Este é o método que permite que outras classes instanciem o banco de dados, pois não se podem perder as informações ja contidas nele, portante a instancia deve ser única.
    - addAccount(): Este é o metodo que cria uma nova conta, ele foi colocado nesta classe foi é aqui onde esta o Map que contém todas as contas criadas.
    - readInteger(): Este é o metodo ultilizado no tratamento de exceções, específicamente a do tipo NumberFormatException. Foi colocado nesta classe pois é nesta que é feita a maioria das leituras de inteiros.
    - login(): Este é basicament o método principal do programa, pois é nele que estão contidos praticamente todas as funcionalidades do sistema, ele foi colocado nesta classe pois em munitas destas funcionalidades é necessário acessar uma conta, uma comunidade, etc. Que estão todas armazenadas nesta classe.
  
  - *Account*:
    - addFriend(): Este é o metodo que adiciona uma conta a lista de amigos do usuário, foi colocado nesta classe pois adiciona um Objeto ao Map amigos, que esta localizado nesta classe.
    - addMessage(): Este é o metodo que adiciona uma nova mensagem a lista de mensagens do usuário, foi colocado nesta classe pois adiciona um Objeto ao ArrayList mensagens, que esta localizado nesta classe.
    - addCommunity(): Mesma coisa dos anteriores, porém adiciona uma comunidade ao Map comunidades do usuário.
    - removeFriends(): Este é o metodo que remove a conta do usuário de todas as listas de amizades do seus amigos, no momento de deletar a conta, foi posta nesta classe pois é necessário o acesso ao Map amigos, que esta contigo nesta classe.
  
  - *Community*:
    - checkRequests(): Este é o metodo que permite o dono da comunidade aceitar ou não os usuários que enviaram solicitação de ingresso em sua comunidades, foi posto aqui pois é necessario o acesso ao ArrayList solicitações de entrada, que esta contido nesta classe.
  
  - *Message*:
    - read(): Este é o metodo que seta a flag "Read" para true, o que indica que a mensagem foi lida pelo usuário.
  
  - *HashMapIterator & ArrayListIterator*:
    - hasNext(): Este método informa se a coleção contém um próximo objeto ou está em seu fim.
    - next(): Este método retorna o objeto atual da coleção, na posição que está setada na próprio classe, e após isso incrementa a posição em um.

- **Padrões Utilizados**: Iterator & Singleton.

- **Métodos que ultilizam os Padrões**:
  - *Singleton*: Iface.getInstance() & Main.main().
  - *Iterator*:
    - HashMapIterator: Account.printFriends(), Account.printCommunitys(), Account.removeFromCommunitys(), Account.removeFriends() & Community.printMembers().
    - ArrayListIterator: Iface.login(), Account.checkMessages(), Account.printMessages() & Community.checkRequests().
