#locação de veículos
#include <stdio.h>
    #include <string.h>

typedef struct {
    long cpfCliente;
    char nomeCliente[100];
    char enderecoCliente[100];
    char telefoneCliente[20];
    char emailCliente[50];
} Cliente;

typedef struct {
    char placaAutomovel[10];
    long renavamAutomovel;
    char chassiAutomovel[20];
    char corAutomovel[20];
    int numeroPortasAutomovel;
    int tipoCombustivelAutomovel;
    long quilometragemAutomovel;
    double valorLocacaoAutomovel;
} Automovel;

typedef struct {
    char descricaoModelo[50];
} Modelo;

typedef struct {
    char descricaoMarca[50];
} Marca;

typedef struct {
    char dataLocacao[11];  
    char horaLocacao[6];  
    char dataDevolucao[11]; 
    char horaDevolucao[6];  
    long quilometragemLocacao;
    long quilometragemDevolucao;
    double valorCaucao;
    double valorLocacao;
    int locacaoDevolvida;   
} Locacao;

void registrarCliente(Cliente *cliente) {
    printf("Digite o CPF do cliente: ");
    scanf("%ld", &cliente->cpfCliente);
    printf("Digite o nome do cliente: ");
    scanf(" %[^\n]", cliente->nomeCliente);
    printf("Digite o endereço do cliente: ");
    scanf(" %[^\n]", cliente->enderecoCliente);
    printf("Digite o telefone do cliente: ");
    scanf(" %[^\n]", cliente->telefoneCliente);
    printf("Digite o email do cliente: ");
    scanf(" %[^\n]", cliente->emailCliente);
}

void registrarAutomovel(Automovel *automovel) {
    printf("Digite a placa do automóvel: ");
    scanf(" %[^\n]", automovel->placaAutomovel);
    printf("Digite o RENAVAM do automóvel: ");
    scanf("%ld", &automovel->renavamAutomovel);
    printf("Digite o chassi do automóvel: ");
    scanf(" %[^\n]", automovel->chassiAutomovel);
    printf("Digite a cor do automóvel: ");
    scanf(" %[^\n]", automovel->corAutomovel);
    printf("Digite o número de portas do automóvel: ");
    scanf("%d", &automovel->numeroPortasAutomovel);
    printf("Digite o tipo de combustível do automóvel (1 - Gasolina, 2 - Diesel, 3 - Elétrico): ");
    scanf("%d", &automovel->tipoCombustivelAutomovel);
    printf("Digite a quilometragem do automóvel: ");
    scanf("%ld", &automovel->quilometragemAutomovel);
    printf("Digite o valor da locação do automóvel: ");
    scanf("%lf", &automovel->valorLocacaoAutomovel);
}

void registrarLocacao(Locacao *locacao) {
    printf("Digite a data da locação (DD/MM/AAAA): ");
    scanf(" %[^\n]", locacao->dataLocacao);
    printf("Digite a hora da locação (HH:MM): ");
    scanf(" %[^\n]", locacao->horaLocacao);
    printf("Digite a data da devolução (DD/MM/AAAA): ");
    scanf(" %[^\n]", locacao->dataDevolucao);
    printf("Digite a hora da devolução (HH:MM): ");
    scanf(" %[^\n]", locacao->horaDevolucao);
    printf("Digite a quilometragem na locação: ");
    scanf("%ld", &locacao->quilometragemLocacao);
    printf("Digite a quilometragem na devolução: ");
    scanf("%ld", &locacao->quilometragemDevolucao);
    printf("Digite o valor do caução: ");
    scanf("%lf", &locacao->valorCaucao);
    printf("Digite o valor da locação: ");
    scanf("%lf", &locacao->valorLocacao);
    printf("A locação foi devolvida? (1 - Sim, 0 - Não): ");
    scanf("%d", &locacao->locacaoDevolvida);
}

// Função principal

int main() {
    Cliente cliente;
    Automovel automovel;
    Locacao locacao;
    Modelo modelo;
    Marca marca;

    printf("Cadastro de Cliente\n");
    registrarCliente(&cliente);

    printf("\nCadastro de Automóvel\n");
    registrarAutomovel(&automovel);

    printf("\nCadastro de Locação\n");
    registrarLocacao(&locacao);

    // Exibe os dados cadastrados
    printf("\nDados do Cliente\n");
    printf("CPF: %ld\n", cliente.cpfCliente);
    printf("Nome: %s\n", cliente.nomeCliente);
    printf("Endereço: %s\n", cliente.enderecoCliente);
    printf("Telefone: %s\n", cliente.telefoneCliente);
    printf("Email: %s\n", cliente.emailCliente);

    printf("\nDados do Automóvel\n");
    printf("Placa: %s\n", automovel.placaAutomovel);
    printf("RENAVAM: %ld\n", automovel.renavamAutomovel);
    printf("Chassi: %s\n", automovel.chassiAutomovel);
    printf("Cor: %s\n", automovel.corAutomovel);
    printf("Número de Portas: %d\n", automovel.numeroPortasAutomovel);
    printf("Tipo de Combustível: %d\n", automovel.tipoCombustivelAutomovel);
    printf("Quilometragem: %ld\n", automovel.quilometragemAutomovel);
    printf("Valor da Locação: %.2lf\n", automovel.valorLocacaoAutomovel);

    printf("\nDados da Locação\n");
    printf("Data da Locação: %s\n", locacao.dataLocacao);
    printf("Hora da Locação: %s\n", locacao.horaLocacao);
    printf("Data da Devolução: %s\n", locacao.dataDevolucao);
    printf("Hora da Devolução: %s\n", locacao.horaDevolucao);
    printf("Quilometragem na Locação: %ld\n", locacao.quilometragemLocacao);
    printf("Quilometragem na Devolução: %ld\n", locacao.quilometragemDevolucao);
    printf("Valor do Caução: %.2lf\n", locacao.valorCaucao);
    printf("Valor da Locação: %.2lf\n", locacao.valorLocacao);
    printf("Locação Devolvida: %s\n", locacao.locacaoDevolvida ? "Sim" : "Não");

    return 0;
}
