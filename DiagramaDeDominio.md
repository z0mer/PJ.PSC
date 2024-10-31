```mermaid

classDiagram
    class Motorista {
        .(Representa um usuário do sistema que busca serviços para seu veículo.)
        -id: int
        -nome: string
        -email: string
        -senha: string
        -telefone: string
    }
    class Veiculo {
        .(Representa um veículo cadastrado no sistema por um motorista.)
        -id: int
        -motorista_id: int
        -marca: string
        -modelo: string
        -ano: int
    }
    class Manutencao {
        .(Representa um registro de manutenção realizada em um veículo.)
        -id: int
        -veiculo_id: int
        -data: date
        -tipo: string
        -descricao: string
    }
    class Prestador {
        .(Representa um prestador de serviços automotivos cadastrado na plataforma.)
        -id: int
        -nome: string
        -email: string
        -senha: string
        -telefone: string
        -tipo_servico: string
        -area_atendimento: string
    }
    class Servico {
        .(Representa um tipo de serviço oferecido por um prestador.)
        -id: int
        -prestador_id: int
        -nome: string
        -descricao: string
        -categoria: string
    }
    class Localizacao {
        .(Armazena coordenadas geográficas. Usada para representar a localização de motoristas e prestadores.)
        -id: int
        -latitude: float
        -longitude: float
    }
    class Solicitacao {
        .(Representa uma solicitação de serviço feita por um motorista a um prestador.)
        -id: int
        -motorista_id: int
        -prestador_id: int
        -servico_id: int
        -data_hora: datetime
        -status: string
    }
    class Avaliacao {
        .(Representa a avaliação de um serviço prestado, feita pelo motorista.)
        -id: int
        -solicitacao_id: int
        -nota: int
        -comentario: string
    }

    Motorista "1" -- "*" Veiculo : possui
    Veiculo "1" -- "*" Manutencao : possui
    Prestador "1" -- "*" Servico : oferece
    Solicitacao "1" -- "1" Avaliacao : possui
    Solicitacao "*" -- "1" Motorista : feita por
    Solicitacao "*" -- "1" Prestador : atende
    Solicitacao "*" -- "1" Servico : solicita

```

