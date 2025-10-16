# Algoritmo de Bellman-Ford para Grafos

Este projeto implementa o algoritmo de Bellman-Ford para encontrar os caminhos mais curtos de um vértice origem para todos os outros vértices em um grafo direcionado ponderado, incluindo a detecção e tratamento de ciclos negativos.

## Descrição

O algoritmo de Bellman-Ford é capaz de lidar com arestas de peso negativo, ao contrário do algoritmo de Dijkstra. Esta implementação inclui funcionalidades especiais para:

- Calcular distâncias mínimas de um vértice origem para todos os outros vértices
- Detectar a presença de ciclos negativos no grafo
- Reconstruir e exibir os caminhos encontrados
- Tratar grafos com ciclos negativos ignorando as arestas problemáticas

## Estrutura do Projeto

```
trabalho07-grafos/
├── script.py          # Implementação principal do algoritmo
├── grafo01.txt        # Arquivo de exemplo com dados do grafo 1
├── grafo02.txt        # Arquivo de exemplo com dados do grafo 2
└── README.md          # Documentação do projeto
```

## Formato dos Arquivos de Entrada

Os arquivos de grafo devem seguir o formato:
```
vertice_origem vertice_destino peso
```

Exemplo:
```
s t 6
s y 7
t x 5
t z -4
```

Onde cada linha representa uma aresta direcionada do vértice origem para o vértice destino com o peso especificado.

## Como Usar

1. **Preparação dos dados**: Certifique-se de que o arquivo do grafo está no formato correto
2. **Execução**: Execute o script Python
3. **Entrada**: Digite o vértice inicial quando solicitado

```bash
python script.py
```

O programa solicitará o vértice inicial:
```
Digite o vértice inicial: s
```

## Funcionalidades Implementadas

### Classe Grafo

- **`load_data(arquivo)`**: Carrega os dados do grafo a partir de um arquivo
- **`add_edge(a, b, peso)`**: Adiciona uma aresta ao grafo
- **`bellman_ford(start_vertex)`**: Implementa o algoritmo principal
- **`reconstruct_path(start, end, predecessors)`**: Reconstrói o caminho entre dois vértices
- **`print_results(start, distances, predecessors, negative_edges)`**: Exibe os resultados
- **`bellman_ford_ignore_cycles(start, negative_edges)`**: Versão que ignora ciclos negativos

### Saída do Programa

Para cada vértice de destino, o programa exibe:
- A distância mínima do vértice origem
- O caminho completo (sequência de vértices)
- Indicação de distância infinita quando não há caminho viável

## Detecção de Ciclos Negativos

O algoritmo detecta automaticamente a presença de ciclos negativos no grafo. Quando encontrados:
- As arestas que formam ciclos negativos são identificadas
- O algoritmo é executado novamente ignorando essas arestas
- Os resultados são calculados para o grafo sem os ciclos problemáticos

## Exemplos de Uso

### Grafo sem Ciclos Negativos
Para um grafo simples, o algoritmo calcula normalmente as distâncias mínimas e exibe os caminhos.

### Grafo com Ciclos Negativos
Quando ciclos negativos são detectados, o programa:
1. Identifica as arestas problemáticas
2. Recalcula as distâncias ignorando essas arestas
3. Apresenta os resultados para o grafo modificado

## Complexidade

- **Tempo**: O(V × E) onde V é o número de vértices e E é o número de arestas
- **Espaço**: O(V) para armazenar as distâncias e predecessores

## Requisitos

- Python 3.x
- Arquivo de entrada no formato especificado

