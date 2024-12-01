## Modelo de Domínio Detalhado do Next Help:


**Classes e Atributos:**

**1. Motorista:**

* `id`: Identificador único (int, chave primária)
* `nome`: Nome completo (string, não nulo)
* `email`: Endereço de email (string, único, não nulo)
* `senha`: Hash da senha (string, não nulo)
* `telefone`: Número de telefone (string)
* `data_cadastro`: Data e hora do cadastro (datetime)
* `ultimo_login`: Data e hora do último login (datetime)
* `ativo`: Indica se o motorista está ativo na plataforma (boolean)
* `localizacao_id`: ID da localização do motorista (int, chave estrangeira, opcional)


**2. Veículo:**

* `id`: Identificador único (int, chave primária)
* `motorista_id`: ID do motorista proprietário (int, chave estrangeira, não nulo)
* `marca`: Marca do veículo (string, não nulo)
* `modelo`: Modelo do veículo (string, não nulo)
* `ano`: Ano de fabricação (int, não nulo)
* `placa`: Placa do veículo (string, único)
* `chassi`: Número do chassi (string, único)
* `cor`: Cor do veículo (string)
* `foto`: URL da foto do veículo (string, opcional)


**3. Manutenção:**

* `id`: Identificador único (int, chave primária)
* `veiculo_id`: ID do veículo (int, chave estrangeira, não nulo)
* `data`: Data da manutenção (date, não nulo)
* `tipo`: Tipo de manutenção (string, ex: "Preventiva", "Corretiva", não nulo)
* `descricao`: Descrição do serviço realizado (string)
* `quilometragem`: Quilometragem do veículo na data da manutenção (int)
* `custo`: Custo da manutenção (decimal, opcional)
* `localizacao_id`: ID do local onde a manutenção foi realizada (int, chave estrangeira, opcional - permite registrar oficina, etc.)


**4. Prestador:**

* `id`: Identificador único (int, chave primária)
* `nome`: Nome do prestador/empresa (string, não nulo)
* `email`: Endereço de email (string, único, não nulo)
* `senha`: Hash da senha (string, não nulo)
* `telefone`: Número de telefone (string, não nulo)
* `tipo_servico`: Tipos de serviço oferecidos (string, ex: "Mecânico, Elétrica",  pode ser uma lista ou tags)
* `descricao`: Descrição detalhada dos serviços (string)
* `avaliacao_media`: Média das avaliações recebidas (decimal, calculada dinamicamente)
* `localizacao_id`: ID da localização principal do prestador (int, chave estrangeira)
* `raio_atendimento`: Raio de atendimento em km (int, opcional)
* `fotos`: URLs de fotos do prestador/estabelecimento (string, opcional, pode ser uma lista)
* `cnpj_cpf`: CNPJ ou CPF (string, único)
* `ativo`: Indica se o prestador está ativo na plataforma (boolean)



**5. Serviço:**

* `id`: Identificador único (int, chave primária)
* `prestador_id`: ID do prestador que oferece o serviço (int, chave estrangeira, não nulo)
* `nome`: Nome do serviço (string, não nulo)
* `descricao`: Descrição detalhada do serviço (string)
* `categoria`: Categoria do serviço (string, ex: "Mecânica", "Elétrica", "Guincho")
* `preco`: Preço médio do serviço (decimal, opcional)


**6. Localização:**

* `id`: Identificador único (int, chave primária)
* `latitude`: Latitude (float, não nulo)
* `longitude`: Longitude (float, não nulo)
* `endereco`: Endereço completo (string, opcional)
* `cidade`: Cidade (string, opcional)
* `estado`: Estado (string, opcional)



**7. Solicitação:**

* `id`: Identificador único (int, chave primária)
* `motorista_id`: ID do motorista (int, chave estrangeira, não nulo)
* `prestador_id`: ID do prestador (int, chave estrangeira, não nulo)
* `servico_id`: ID do serviço (int, chave estrangeira, não nulo)
* `data_hora`: Data e hora da solicitação (datetime, não nulo)
* `status`: Status da solicitação (string, ex: "Pendente", "Aceita", "Em andamento", "Concluída", "Cancelada", não nulo)
* `descricao_problema`: Descrição do problema relatado pelo motorista (string)
* `localizacao_id`: ID da localização do problema (int, chave estrangeira)
* `valor_final`:  Valor final cobrado pelo serviço (decimal, opcional, preenchido após a conclusão)


**8. Avaliação:**

* `id`: Identificador único (int, chave primária)
* `solicitacao_id`: ID da solicitação (int, chave estrangeira, não nulo)
* `nota`: Nota (int, ex: de 1 a 5)
* `comentario`: Comentário do motorista (string, opcional)
* `data_avaliacao`: Data e hora da avaliação (datetime)


**Relacionamentos (com multiplicidades):**

* Motorista *1 --- * Veículo
* Veículo *1 --- * Manutenção
* Prestador *1 --- * Serviço
* Motorista *1 --- * Solicitação
* Prestador *1 --- * Solicitação
* Serviço *1 --- * Solicitação
* Solicitação 1 --- 1 Avaliação
* Motorista *0..1 --- 1 Localização (opcional, localização principal do motorista)
* Prestador 1 --- 1 Localização (localização principal do prestador)
* Manutenção *0..1 --- 1 Localização (opcional)
* Solicitação 1 --- 1 Localização (localização do problema)


