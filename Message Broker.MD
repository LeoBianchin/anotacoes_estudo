# Message Broker

Um *Message Broker* é um tipo de serviço específico responsável por fazer a integração entre microsserviços por meio de mensagens.

Um exemplo de broker de mensagens é o RabbitMQ.

Construído como um projeto separado, os microsserviços do projeto que precisarem de integrar com outros microsserviços publicarão mensagens para o broker, e os serviços que estiverem "escutando" essa lista específica irá receber e executar o fluxo normal da aplicação.



