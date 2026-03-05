#include <stdio.h>
#include <stdlib.h>
#include <limits.h>

// ---------- Questão 1 ----------
void questao1() {
    printf("Questao 1:\n");
    printf("HeapSort possui complexidade O(n log n) garantida, pois cada extracao da raiz custa log n e sao feitas n vezes.\n");
    printf("ShellSort depende da sequencia de gaps escolhida, podendo variar entre O(n log^2 n) e O(n^2).\n\n");
}


void imprimirVetor(int vet[], int n) {
    for (int i = 0; i < n; i++) printf("%d ", vet[i]);
    printf("\n");
}

void organizarSubarvore(int vet[], int tamanho, int indiceRaiz) {
    int maior = indiceRaiz;
    int esquerda = 2 * indiceRaiz + 1;
    int direita = 2 * indiceRaiz + 2;

    if (esquerda < tamanho && vet[esquerda] > vet[maior])
        maior = esquerda;
    if (direita < tamanho && vet[direita] > vet[maior])
        maior = direita;

    if (maior != indiceRaiz) {
        int aux = vet[indiceRaiz];
        vet[indiceRaiz] = vet[maior];
        vet[maior] = aux;
        organizarSubarvore(vet, tamanho, maior);
    }
}

void construirHeap(int vet[], int n) {
    for (int i = n/2 - 1; i >= 0; i--)
        organizarSubarvore(vet, n, i);
}

// ---------- Questão 2 ----------
void questao2() {
    printf("Questao 2:\n");
    int vet[] = {30, 12, 45, 6, 18, 3};
    int n = sizeof(vet)/sizeof(vet[0]);

    printf("Vetor inicial: ");
    imprimirVetor(vet, n);

    construirHeap(vet, n);
    printf("Max-Heap construido: ");
    imprimirVetor(vet, n);

    // Extração da raiz
    int aux = vet[0];
    vet[0] = vet[n-1];
    vet[n-1] = aux;
    organizarSubarvore(vet, n-1, 0);

    printf("Vetor apos primeira extracao da raiz: ");
    imprimirVetor(vet, n);
    printf("\n");
}

// ---------- Questão 3 ----------
void questao3() {
    printf("Questao 3:\n");
    printf("Afirmativas corretas: II e IV.\n");
    printf("Resposta: A) Apenas II e IV\n\n");
}

// ---------- Questão 4 ----------
void questao4() {
    printf("Questao 4:\n");
    printf("Para sistemas com milhoes de registros, HeapSort e mais indicado.\n");
    printf("Complexidade O(n log n) garantida e previsivel, diferente do ShellSort.\n\n");
}

// ---------- Questão 5 ----------
#define V 5
int minDistancia(int dist[], int visitado[]) {
    int min = INT_MAX, indice = -1;
    for (int v = 0; v < V; v++) {
        if (!visitado[v] && dist[v] <= min) {
            min = dist[v];
            indice = v;
        }
    }
    return indice;
}

void dijkstra(int grafo[V][V], int src) {
    int dist[V];
    int visitado[V];

    for (int i = 0; i < V; i++) {
        dist[i] = INT_MAX;
        visitado[i] = 0;
    }
    dist[src] = 0;

    for (int count = 0; count < V-1; count++) {
        int u = minDistancia(dist, visitado);
        visitado[u] = 1;

        for (int v = 0; v < V; v++) {
            if (!visitado[v] && grafo[u][v] && dist[u] != INT_MAX && dist[u] + grafo[u][v] < dist[v]) {
                dist[v] = dist[u] + grafo[u][v];
            }
        }
    }

    printf("Distancias minimas a partir do vertice %d:\n", src);
    for (int i = 0; i < V; i++) {
        printf("Vertice %d: %d\n", i, dist[i]);
    }
}

void questao5() {
    printf("Questao 5:\n");
    printf("Heap e usado como fila de prioridade em algoritmos de grafos.\n");
    printf("Exemplo: Algoritmo de Dijkstra.\n");

    int grafo[V][V] = {
        {0, 10, 0, 30, 100},
        {10, 0, 50, 0, 0},
        {0, 50, 0, 20, 10},
        {30, 0, 20, 0, 60},
        {100, 0, 10, 60, 0}
    };

    dijkstra(grafo, 0);
    printf("\n");
}

// ---------- MAIN ----------
int main() {
    questao1();
    questao2();
    questao3();
    questao4();
    questao5();
    return 0;
}
