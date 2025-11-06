# Diagramas

Teste o código dos diagramas em [https://mermaid.live](https://mermaid.live)

## De classe

classDiagram
    class Usuario {
        +int idUsuario
        +string nome
        +string email
        +string senha
        +string cpf
        +Date dataCadastro
        +boolean autenticar(email, senha)
        +void atualizarPerfil()
    }
    class Conta {
        +int idConta
        +string tipoConta
        +double saldo
        +double limiteCredito
        +void depositar(valor)
        +void sacar(valor)
        +void transferir(destino, valor)
    }
    class Transacao {
        +int idTransacao
        +string tipo
        +double valor
        +Date data
        +string descricao
        +void registrar()
    }
    class Investimento {
        +int idInvestimento
        +string tipoInvestimento
        +double valorAplicado
        +double rentabilidade
        +Date dataAplicacao
        +double calcularRendimento()
        +void resgatar(valor)
    }
    class Poupanca {
        +double taxaMensal
        +double calcularRendimentoMensal()
    }
    class FundoImobiliario {
        +string codigoFundo
        +double valorCota
        +int quantidadeCotas
        +double calcularValorTotal()
        +void atualizarCotas(qtd)
    }
    class Credito {
        +int idCredito
        +double valor
        +double taxaJuros
        +int parcelas
        +Date dataContratacao
        +double calcularParcela()
        +void quitar()
    }
    class RelatorioFinanceiro {
        +Date periodoInicio
        +Date periodoFim
        +double saldoFinal
        +double totalInvestido
        +double totalCredito
        +string gerarResumo()
        +void exportarPDF()
    }
    Usuario "1" --> "*" Conta : tem
    Usuario "1" --> "*" Investimento : possui
    Conta "*" --> "1" Transacao : possui
    Transacao "*" --> "1" Conta : registrada em
    Investimento "*" --> "1" Usuario : possui
    Investimento <|-- Poupanca : é um
    Investimento <|-- FundoImobiliario : é um
    Conta "1" --> "*" Credito : pode ter
    Usuario "1" --> "1" RelatorioFinanceiro : gera
