#include<stdio.h>
#include<locale.h>
#include<string.h>

int opcao = 0;


void TelaLogin(){

    char login[15] = "1";
    char senha[15] = "2";
    char valid[15],tmp[15];
            
    int senhavalida = 0; //0 - Falso e  1 - Verdadeiro

    while(!senhavalida){
        printf("Digite o Login: ");
        scanf("%s", valid);

        printf("Digite a Senha: ");
        scanf("%s", tmp);

        if (strcmp(login, valid) == 0 && strcmp(senha, tmp) == 0){
            printf("\n\n      SEJA BEM VINDO\n\n");
            senhavalida = 1;
        }
        else
            printf("\n\nDADOS INVALIDOS!\n\n");    
    }

}

void MostrarMenu(){

    printf(">>>>>>>ARE YOU OKEY ?<<<<<<<\n\n");
    printf("****************************\n\n");

    printf("1) - ESTOU PASSANDO MAL PRECISO DE AJUDA\n");
    printf("2) - HOSPITAIS EM SUA REGIAO\n");
    printf("3) - SAIR DO SISTEMA\n\n");    
    printf("ESCOLHA A OPCAO ACIMA: ");
    scanf("%d", &opcao);

    getchar();    

}

void Ajuda(){

    printf("\n\nDisque Denúncia	181\n");
    printf("\n\nPolícia Militar	190\n");
    printf("\n\nRemoção de Doentes (Ambulâncias - SAMU)	192\n");
    printf("\n\nPolícia Federal	194\n");

}

void Hospitais(){

    printf("\n\nem sua cidade possui o HU\n");
    printf("numero do HU 3010-1440\n");
    printf("\n\nem sua cidade possui o Santa Rita\n");
    printf("numero do Santa Rita 2420-6460\n");
    printf("\n\nem sua cidade possui o Bom Samaritano\n");
    printf("numero do Bom Samaritano 5959-4948\n");
}


int main(){

    setlocale(LC_ALL, "");

    TelaLogin();

    MostrarMenu();

        switch (opcao)

        {

            case 1 : 

                Ajuda();

            break;

            case 2 : 

                Hospitais();

            break;

            default :

                printf("SAIR DO SISTEMA!");

            break;    
        }

        getchar();



    return 0;
}
