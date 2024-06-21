## Introdução
Ao aprender uma nova linguagem de programação, é comum explorar algoritmos fundamentais como a busca linear e binária. Esses algoritmos não apenas ajudam a compreender melhor como as máquinas executam sequências de eventos, mas também fortalecem o raciocínio lógico e a capacidade de desenvolver algoritmos eficientes. É fundamental compreender os conceitos.

- Na busca linear, percorremos toda a lista verificando cada elemento sequencialmente. Em contraste, a busca binária é altamente eficiente, dividindo a lista pela metade a cada passo.

## Exemplos das buscas:

```javascript

Imagine que queremos encontrar o número 7 na lista [1, 2, 3, 4, 5, 6, 7, 8, 9, 10] //Isso em Busca Linear
````
- A busca começaria no início da lista.
- A máquina compararia cada número com o 7 até encontrá-lo no sétimo índice.
- Pior caso: Se o número 7 estivesse no final da lista, a máquina precisaria percorrer todos os 10 elementos.

**Complexidade**
- O(1) Melhor caso
- o(n) Pior caso

## Busca Binária

A busca binária é eficiente em listas ordenadas, reduzindo o intervalo de busca, dividindo pela metade a cada iteração.

**Complexidade**
- O(1) Melhor caso
- O(log n) Pior caso

## Exemplo de Busca Binária:

```javascript
Na lista [1, 2, 3, 4, 5, 6, 7, 8, 9, 10], procuramos o número 7:
```

- Começamos comparando com o elemento central (5).
- Como 7 é maior que 5, ignoramos a metade inferior da lista ([1, 2, 3, 4, 5]).
- Continuamos dividindo o intervalo até encontrar o número 7 no índice 6.


## Comparações
Para ilustrar as diferenças de desempenho: imagine que eu tenha um exemplar de "O Iluminado" de Stephen King, que possui 412 páginas, e eu queira encontrar a página 210.

### Exemplo em JavaScript
**Busca Linear:**
```javascript
function buscaLinear(array, elemento) {
    for (let i = 0; i < array.length; i++) {
        if (array[i] === elemento) {
            return i;
        }
    }
    return -1;
}

const paginas = [...Array(412)].map((_, index) => index + 1); // Simula as páginas de 1 a 412

const paginaDesejada = 210;
const indiceLinear = buscaLinear(paginas, paginaDesejada);

console.log(`Índice encontrado pela Busca Linear: ${indiceLinear}`);
````
-  A busca linear percorre cada página do livro até encontrar a página desejada.

**Busca Binária**
```javascript
function buscaBinaria(array, elemento, inicio = 0, fim = array.length - 1) {
    while (inicio <= fim) {
        const meio = Math.floor((inicio + fim) / 2);
        if (array[meio] === elemento) {
            return meio;
        } else if (array[meio] < elemento) {
            inicio = meio + 1;
        } else {
            fim = meio - 1;
        }
    }
    return -1;
}

const indiceBinaria = buscaBinaria(paginas, paginaDesejada);

console.log(`Índice encontrado pela Busca Binária: ${indiceBinaria}`);
````
- Na busca binária, sabemos que ela está aproximadamente na metade do livro. Assim, a máquina divide o percurso pela metade a cada passo, encontrando a página desejada em menos tempo e com menos etapas, mesmo em arrays grandes.

## Executando o código

```javascript
Busca Linear: A página 210 foi encontrada no índice 209.
Foram necessários 210 passos para encontrar a página na busca linear.
````
```javascript
Busca Binária: A página 210 foi encontrada no índice 209.
Foram necessários 8 passos para encontrar a página na busca binária.
````

## Conclusão

A diferença na quantidade de passos entre a busca linear e a busca binária é significativa, especialmente em arrays grandes como o número de páginas de um livro. Enquanto a busca linear exige que percorramos cada página sequencialmente até encontrar a desejada, a busca binária reduz drasticamente o número de passos, dividindo o intervalo pela metade a cada iteração. Isso ilustra a eficiência da busca binária em comparação com a busca linear para encontrar um elemento em um conjunto ordenado de dados.
