## Projeto de Busca Linear e Binária
Este projeto implementa algoritmos de busca linear e binária em JavaScript, mas pode ser feita com qualquer outra linguagem, desde que você saiba os conceitos e logicas basicas de programação. As buscas são realizadas em um array que simula páginas numeradas, onde buscamos encontrar a posição de uma página desejada.

## Algoritmos Implementados

### Busca Linear

A busca linear percorre cada elemento do array sequencialmente até encontrar o elemento desejado ou determinar que ele não está presente. É uma abordagem simples, mas pode ser ineficiente para arrays grandes.

**Complexidade:**
- Melhor caso: O(1) - O elemento está no início do array.
- Pior caso: O(n) - O elemento está no final do array ou não está presente.

**Estrutura Básica:**
```javascript
function buscaLinear(array, elemento) {
    for (let i = 0; i < array.length; i++) {
        if (array[i] === elemento) {
            return i;
        }
    }
    return -1;
}

````

## Busca Binária

A busca binária é uma abordagem eficiente para encontrar um elemento em um array ordenado. Ela divide repetidamente o intervalo de busca ao meio até que o elemento desejado seja encontrado ou determinado que não existe no array.

**Complexidade**
- Melhor caso: O(1) - O elemento está no meio do array.
- Pior caso: O(log n) - O elemento está no início ou no final do array.

**Estrutura Básica:**
```javascript
function buscaBinaria(array, elemento, inicio = 0, fim = array.length - 1) {
    if (inicio > fim) {
        return -1;
    }

    const meio = Math.floor((inicio + fim) / 2);

    if (array[meio] === elemento) {
        return meio;
    } else if (array[meio] > elemento) {
        return buscaBinaria(array, elemento, inicio, meio - 1);
    } else {
        return buscaBinaria(array, elemento, meio + 1, fim);
    }
}
````

## Comparação de Desempenho
Para comparar o desempenho dos dois algoritmos, você pode medir o tempo de execução de cada um ao buscar um elemento em um array.
<br><br>
**Exemplo de uso:**
```javascript
const paginas = [...Array(400)].map((_, index) => index + 1);

const elemento = 250; // Exemplo de elemento a ser buscado

console.time('Busca Linear');
const indiceLinear = buscaLinear(paginas, elemento);
console.timeEnd('Busca Linear');

console.time('Busca Binária');
const indiceBinaria = buscaBinaria(paginas, elemento);
console.timeEnd('Busca Binária');

console.log(`Índice encontrado pela Busca Linear: ${indiceLinear}`);
console.log(`Índice encontrado pela Busca Binária: ${indiceBinaria}`);
````

## Considerações Finais
- Busca Linear: Útil para arrays pequenos ou não ordenados. É fácil de implementar e não requer ordenação prévia.

- Busca Binária: Ideal para arrays grandes e ordenados. Embora seja mais eficiente em termos de tempo de execução, requer que os dados estejam ordenados.
