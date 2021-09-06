#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#define j 3
typedef struct{
    int conta;
    char nome[100];
    float saldo;
    }cliente;
void cadastrar(cliente cliente[],int posicao){
    fflush(stdin);
    printf("\n\nINFORME O NOME DO CLIENTE: ");
    gets(cliente[posicao].nome);
    fflush(stdin);
    printf("\nINFORME O NÚMERO DA CONTA CORRENTE: ");
    scanf("%d",&cliente[posicao].conta);
    printf("\nINFORME O SALDO ATUAL: ");
    scanf("%f",&cliente[posicao].saldo);
    system("pause");
    system("cls");
}
void consulta(cliente cliente[]){
 int posicao,indice=-1;
    char nome[100];
    fflush(stdin);
    printf("\nINFORME O NOME PARA A CONSULTA: ");
    gets(nome);
    system("pause");
    system("cls");
    for(posicao=0;posicao<j;posicao++){
     if(strcmp(nome,cliente[posicao].nome)==0){
        indice=posicao;
        break;
      }
  }
  if(indice != -1){
    printf("------------------INFORMAÇÕES ENCONTRADAS------------------\n\nNOME: %s",cliente[posicao].nome);
    printf("\nINFORME O NÚMERO DA CONTA CORRENTE: %d\n\n",cliente[posicao].conta);
    printf("\nINFORME O SALDO ATUAL: %.2f\n\n",cliente[posicao].saldo);
    system("pause");
    system("cls");
}
  else{
    printf("\nCliente não encontrado\n\n");
     system("pause");
   system("cls");
   }
}
/*float menor(float nt1,float nt2, float nt3)
{
float resmenor;
  if ((nt1<nt2)&&(nt1<nt3))
{
resmenor=nt1;
}
  else if((nt2<nt1)&&(nt2<nt3))
{
resmenor=nt2;
}
  else
{
resmenor=nt3;
}
printf("\n\n O MENOR VALOR É: %.2f",menorvalor);
return resmenor;
}*/
int main()
{
    cliente cli[j];
 int loop=1,opc,aux=0;
 //float menorvalor,n1,n2,n3;

setlocale(LC_ALL,"");
system("color 0b");
    while(loop){
        system("cls");
        printf("\n\----------------------------BEM VINDO AO BANCO CEFET----------------------------");
        printf("\n\n\t\t\t\tMENU DE CADASTRO");
        printf("\nDIGITE 1 PARA CADASTRAR UM NOVO CLIENTE");
        printf("\nDIGITE 2 PARA CONSULTAR UM CLIENTE");
        printf("\nDIGITE 3 MOSTRAR DADOS DO CLIENTE COM MENOR SALDO");
        printf("\nDIGITE 4 PARA SAIR DO PROGRAMA\n");
        printf("OPÇÃO SELECIONADA: ");
        scanf("%d",&opc);
        switch(opc){
         case 1: cadastrar(cli,aux);
            aux++;
            break;
         case 2: consulta(cli);
            break;
         //case 3: menor(n1,n2,n3);
            //break;
         case 4: loop=0;
            break;
         default:
            printf("\nOPÇÃO INVÁLIDA");
        }

    }

 printf("\n-----------------------OBRIGADO POR USAR O PROGRAMA-----------------------\n\n");

    return 0;
}






