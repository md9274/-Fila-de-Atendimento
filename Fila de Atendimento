#include <stdio.h>
#include <string.h>
#define TAM 5
char fila[TAM][50];
int inicio = -1;
int fim = -1;
int cheia() {
 return (inicio == 0 && fim == TAM - 1) || (inicio == fim + 1);
}
int vazia() {
 return inicio == -1;
}
void enqueue(char nome[]) {
 if (cheia()) {
 printf("Fila cheia! Nao foi possivel adicionar %s.\n", nome);
 return;
 }
 if (inicio == -1) {
 inicio = 0;
 }
 fim = (fim + 1) % TAM;
 strncpy(fila[fim], nome, 49);
 fila[fim][49] = '\0';
 printf("%s entrou na fila.\n", fila[fim]);
}
void dequeue() {
 if (vazia()) {
 printf("Fila vazia! Ninguem para atender.\n");
 return;
 }
 printf("%s foi atendido.\n", fila[inicio]);
 if (inicio == fim) {
 inicio = -1;
 fim = -1;
 } else {
 inicio = (inicio + 1) % TAM;
 }
}
void mostrar() {
 if (vazia()) {
 printf("Fila vazia!\n");
 return;
 }
 printf("\n--- Fila de atendimento ---\n");
 int i = inicio;
 int pos = 1;
 while (1) {
 printf("%d. %s\n", pos++, fila[i]);
 if (i == fim)
 break;
 i = (i + 1) % TAM;
 }
}
int main() {
 int opcao;
 char nome[50];
 do {
 printf("\n===== SISTEMA DE FILA DE ATENDIMENTO =====\n");
 printf("1. Adicionar pessoa a fila\n");
 printf("2. Atender pessoa\n");
 printf("3. Mostrar fila\n");
 printf("0. Sair\n");
 scanf("%d", &opcao);
 getchar();
 switch(opcao) {
 case 1:
 printf("Nome da pessoa: ");
 fgets(nome,50,stdin);
 nome[strcspn(nome,"\n")] = '\0';
 enqueue(nome);
 break;
 case 2:
 dequeue();
 break;
 case 3:
 mostrar();
 break;
 }
 } while(opcao != 0);
 return 0;
}
