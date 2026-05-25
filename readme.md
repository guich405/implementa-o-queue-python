# Fila (Queue) - Implementação Customizada em Python

Este projeto contém uma implementação customizada de uma estrutura de dados do tipo Fila (Queue) baseada no conceito de FIFO. O código foi construído  em Python utilizando o conceito de nós encadeados.

## Funcionalidades

A classe `Queue` oferece os principais métodos de uma fila, construídos com tipagem estática e suporte nativo aos "magic methods" do Python:

* **`push(node_value: int)`:** Adiciona um novo nó com um valor inteiro ao final da fila.
* **`pop() -> Node`:** Remove e retorna o primeiro nó da fila. Levanta uma exceção `EmptyQueueError` se a fila já estiver vazia.
* **`peek() -> Node`:** Retorna o primeiro nó da fila (para visualização) sem removê-lo.
* **Iteração Embutida:** A fila atua como seu próprio iterador. É possível usar a função `next(queue)` ou iterar com um loop `for item in queue`. **Aviso:** Como toda fila padrão, o ato de iterar sobre ela consome (faz *pop*) dos elementos.
* **Verificações Nativas:** Suporta a verificação de tamanho utilizando `len(queue)` e testes booleanos lógicos (`if queue:` para checar se não está vazia).

##  Estrutura do Código

O arquivo é estruturado com três componentes principais:

1. **`EmptyQueueError`:** Uma exceção customizada focada em prevenir erros críticos de remoção em filas vazias.
2. **`Node`:** A classe que representa o elemento da fila. Cada nó guarda um valor (`value`) e aponta para o próximo elemento da cadeia (`next`).
3. **`Queue`:** O gerenciador da fila. Ele rastreia o primeiro (`first`) e o último (`last`) nó, além de manter a contagem instantânea de elementos (`_count`).

## Como Usar

O uso é simples e direto. Você pode testar rodando o próprio script ou importando em outro arquivo:

```python
# Supondo que o arquivo se chame queue.py
from queue import Queue

# Inicializa a Fila
queue = Queue()

# Adiciona elementos à fila
queue.push(1)
queue.push(2)
queue.push(3)

# Retira o primeiro item da fila utilizando next()
print('Item retirado:', next(queue)) # Saída: 1

# Itera sobre os itens restantes
# (Isso fará o pop() automático de cada item até esvaziar a fila)
for item in queue:
    print('Item no loop:', item) # Saída: 2, e depois 3

# Como os itens foram consumidos na iteração, a fila agora está vazia
print(queue) # Saída: Queue()