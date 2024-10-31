```mermaid
graph TD
    Next_Help[Next_Help]
    
    Motorista[Motorista]
    Motorista -->|Cadastrar-se| Next_Help
    Motorista -->|Cadastrar Veículo| Next_Help

    LoginMotorista[Login Motorista]
    Next_Help --> LoginMotorista

    LoginMotorista -->|Buscar Prestador| FuncionalidadesMotorista
    LoginMotorista -->|Visualizar Detalhes do Prestador| FuncionalidadesMotorista
    LoginMotorista -->|Solicitar Serviço| FuncionalidadesMotorista
    LoginMotorista -->|Avaliar Prestador| FuncionalidadesMotorista
    LoginMotorista -->|Acessar Tutoriais| FuncionalidadesMotorista
    LoginMotorista -->|Gerenciar Perfil| FuncionalidadesMotorista
    FuncionalidadesMotorista[Funcionalidades] -->|Sair| SairMotorista

    SairMotorista[Sair]

    Prestador[Prestador]
    Prestador -->|Cadastrar-se| Next_Help
    Prestador -->|Gerenciar Perfil| Next_Help

    LoginPrestador[Login Prestador]
    Next_Help --> LoginPrestador

    LoginPrestador -->|Visualizar Solicitações| FuncionalidadesPrestador
    LoginPrestador -->|Aceitar/Recusar Solicitação| FuncionalidadesPrestador
    LoginPrestador -->|Atualizar Status do Serviço| FuncionalidadesPrestador
    LoginPrestador -->|Gerenciar Perfil| FuncionalidadesPrestador
    FuncionalidadesPrestador[Funcionalidades] -->|Sair| SairPrestador

    SairPrestador[Sair]

```
