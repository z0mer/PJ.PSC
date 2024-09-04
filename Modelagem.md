<div align = "middle">  
    
# FLUXOS: *NEXT HELP* ❇️

</div>

----
# Cadastro de consumidor

```mermaid
graph LR
    A[Início - Motorista acessa o PSC] --> B{Motorista possui cadastro?}
    B -- Sim --> C(Motorista faz login)
    B -- Não --> D(Motorista inicia cadastro)
    D --> E(Motorista informa dados)
    E --> F(Sistema valida dados)
    F -- Válido --> G(Sistema cria conta)
    G --> C
    F -- Inválido --> H(Sistema solicita correção)
    H --> E
    C --> I(Motorista acessa funcionalidades)
    I --> J{Motorista deseja editar perfil?}
    J -- Sim --> K(Motorista edita dados)
    K --> F
    J -- Não --> I
    I --> L(Fim - Motorista utiliza o PSC)
```

# Cadastro de Prestadores de Serviço

```mermaid
graph LR
    A[Prestador acessa a seção 'Tornar-se um Prestador'] --> B(Sistema exibe tipos de serviço)
    B --> C(Prestador seleciona o tipo de serviço)
    C --> D(Sistema exibe formulário de cadastro específico)
    D --> E(Prestador preenche informações - dados pessoais, área de atuação, especialidades, etc.)
    E --> F(Sistema valida informações)
    F -- Válido --> G(Prestador define detalhes do serviço preços, disponibilidade, etc.)
    G --> H(Sistema revisa e aprova o cadastro)
    H -- Aprovado --> I(Sistema notifica o prestador sobre a aprovação)
    I --> J(Fim - Cadastro completo, prestador apto a receber solicitações)
    H -- Pendente --> K(Sistema solicita informações adicionais ou correções)
    K --> E
    F -- Inválido --> L(Sistema informa erro e solicita correção)
    L --> E
```

# Busca e Contato com Prestadores de Serviços

```mermaid
graph LR
    A[Motorista solicita serviço] --> B(Sistema exibe opções de busca)
    B --> C{Motorista filtra resultados?}
    C -- Sim --> D(Motorista aplica filtros)
    D --> B
    C -- Não --> E(Sistema exibe lista de prestadores)
    E --> F{Motorista escolhe um prestador?}
    F -- Sim --> G(Sistema exibe perfil do prestador)
    G --> H{Motorista decide contatar?}
    H -- Sim --> I(Motorista contata prestador)
    H -- Não --> E
    F -- Não --> J(Motorista finaliza busca)
    I --> K(Comunicação estabelecida)

```

#  Acesso a Tutoriais de Autoajuda

```mermaid
graph LR
    A[Motorista acessa seção de tutoriais] --> B(Sistema exibe categorias de tutoriais)
    B --> C{Motorista busca tutorial específico?}
    C -- Sim --> D(Motorista informa palavra-chave)
    D --> E(Sistema exibe resultados da busca)
    C -- Não --> E
    E --> F{Motorista encontra tutorial desejado?}
    F -- Sim --> G(Motorista acessa conteúdo do tutorial)
    G --> H(Motorista finaliza leitura/visualização)
    F -- Não --> I(Motorista retorna à lista de categorias)
    I --> B
    H --> J(Fim - Motorista sai da seção de tutoriais)
```

# Cadastro de Tutoriais

```mermaid
graph LR
    A[Criador acessa painel administrativo] --> B(Sistema exibe opção 'Criar Tutorial')
    B --> C(Criador escolhe categoria)
    C --> D(Sistema exibe formulário de cadastro)
    D --> E(Criador preenche informações do tutorial)
    E --> F{Vídeo?}
    F -- Sim --> G(Criador envia vídeo)
    G --> H(Sistema valida aspectos técnicos e legais do vídeo)
    H -- Válido --> I(Criador adiciona conteúdo - texto, imagens)
    H -- Inválido --> M(Sistema informa erro e solicita novo envio)
    M --> G
    F -- Não --> I
    I --> J(Sistema publica tutorial com aviso 'Em Avaliação') 
    J --> K{Motoristas interagem com o vídeo?}
    K -- Sim --> L(Sistema atualiza Pontuação de Credibilidade)
    L --> N{Pontuação alta?}
    N -- Sim --> O(Vídeo destacado e recomendado)
    N -- Não --> P(Vídeo disponível normalmente)
    K -- Não --> P
    O --> P
```

#  Avaliação de Prestadores e Feedback

```mermaid
graph LR
    A[Motorista utiliza serviço de um prestador] --> B{Motorista deseja avaliar o serviço?}
    B -- Sim --> C(Sistema exibe formulário de avaliação)
    C --> D(Motorista preenche avaliação - nota, comentário)
    D --> E(Sistema registra avaliação)
    E --> F(Sistema agradece feedback)
    F --> G(Fim - Avaliação enviada com sucesso)
    B -- Não --> G
```

# Gerenciamento de Pagamento

``` mermaid
graph LR
    A[Serviço Finalizado] --> B{Pagamento pelo aplicativo?}
    B -- Sim --> C(Motorista escolhe método de pagamento)
    C --> D(Sistema processa pagamento)
    D -- Sucesso --> E(Sistema notifica motorista e prestador)
    D -- Falha --> F(Sistema informa erro ao motorista)
    E --> G(Fim - Pagamento realizado)
    F --> H(Motorista tenta novamente ou cancela)
    B -- Não --> I(Motorista acerta pagamento com prestador)
    I --> J(Fim - Pagamento externo) 
```

# Cadastro e Gestão de Perfil da Mecânica

```mermaid
graph LR
    A[Mecânica acessa o PSC] --> B{Mecânica possui cadastro?}
    B -- Sim --> C(Mecânica faz login)
    B -- Não --> D(Mecânica inicia cadastro como prestadora)
    D --> E(Mecânica informa dados - especialidades, área de atendimento, etc.)
    E --> F(Sistema valida dados)
    F -- Válido --> G(Sistema cria perfil da mecânica)
    G --> C
    F -- Inválido --> H(Sistema solicita correção)
    H --> E
    C --> I(Mecânica acessa painel de controle)
    I --> J{Mecânica deseja editar perfil?}
    J -- Sim --> K(Mecânica edita dados do perfil)
    K --> F
    J -- Não --> I
    I --> L{Gerenciar serviços?} 
    L -- Sim --> M(Mecânica define disponibilidade, preços, etc.)
    L -- Não --> I
    M --> I
    I --> N(Fim - Mecânica encerra sessão)
```

# Recebimento e Gestão de Solicitações de Serviço

```mermaid
graph LR
    A[Nova solicitação de serviço recebida] --> B(Sistema notifica a mecânica)
    B --> C(Mecânica visualiza detalhes da solicitação - localização, tipo de serviço)
    C --> D{Mecânica aceita a solicitação?}
    D -- Sim --> E(Mecânica informa dados adicionais - tempo estimado, etc.)
    E --> F(Sistema confirma serviço com o motorista)
    F --> G(Mecânica realiza o serviço)
    G --> H(Fim - Serviço concluído)
    D -- Não --> I(Mecânica recusa a solicitação)
    I --> J(Sistema notifica o motorista sobre a recusa)
    J --> K(Fim - Solicitação recusada) 
```

# Acompanhamento de Pagamentos

```mermaid
graph LR
    A[Serviço Concluído] --> B{Pagamento pelo aplicativo?}
    B -- Sim --> C(Sistema notifica mecânica sobre pagamento)
    C --> D(Fim - Pagamento confirmado)
    B -- Não --> E(Mecânica acerta pagamento com o motorista)
    E --> F(Fim - Pagamento acertado externamente)
```


