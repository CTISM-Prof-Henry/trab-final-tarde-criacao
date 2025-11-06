# Diagramas
Teste o código dos diagramas em [https://mermaid.live](https://mermaid.live)
## De classe
<img width="2597" height="1798" alt="image" src="https://github.com/user-attachments/assets/de4c067e-0fc2-4c3a-8c8d-03a2ea4e441b" />

```
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

```
## De caso de uso
<img width="2316" height="670" alt="image" src="https://github.com/user-attachments/assets/7e487141-43e3-40ff-8047-7349e1b4026f" />
 flowchart TD
    Usuario(["Usuário"])
    Conta(["Gerenciar Conta"])
    Transacao(["Realizar Transação"])
    Investimento(["Aplicar/Resgatar Investimento"])
    Credito(["Solicitar Crédito"])
    Relatorio(["Gerar Relatório Financeiro"])
    Poupanca(["Aplicar em Poupança"])
    FundoImobiliario(["Aplicar em Fundo Imobiliário"])

    Usuario -- "Acessa" --> Conta
    Usuario -- "Realiza" --> Transacao
    Usuario -- "Investe em" --> Investimento
    Usuario -- "Solicita" --> Credito
    Usuario -- "Consulta" --> Relatorio
    Investimento -- "Inclui" --> Poupanca
    Investimento -- "Inclui" --> FundoImobiliario
```
