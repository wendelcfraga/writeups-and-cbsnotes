## Exemplo de uso do operador -> em C


```c
#include <stdio.h>

typedef struct {
  int x;
  int y;
} point;

int main(void) {
  point p1 = {1, 2};
  point *p2 = &p1;

  // Imprime o valor de x na estrutura p1
  printf("p1.x = %d\n", p1.x);

  // Imprime o valor de y na estrutura p1 através do ponteiro p2
  printf("p2->y = %d\n", p2->y);

  return 0;
}
```
Neste exemplo, criamos uma estrutura chamada "point" que tem dois campos inteiros: "x" e "y". Em seguida, criamos uma variável da estrutura chamada "p1" e atribuímos valores aos seus campos.

Depois, criamos um ponteiro para a estrutura "point" chamado "p2" e atribuímos a ele o endereço da variável "p1".

Para acessar os campos da estrutura "p1" através do ponteiro "p2", usamos o operador "->". Por exemplo, para acessar o campo "y" da estrutura "p1", escrevemos "p2->y". Isso é equivalente a escrever "(*p2).y".

O programa imprime os valores de "x" e "y" da estrutura "p1" usando duas maneiras diferentes: diretamente na variável "p1" e através do ponteiro "p2". A saída do programa seria:

```c
p1.x = 1
p2->y = 2
```
