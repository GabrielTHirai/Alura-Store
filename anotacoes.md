<h1> CSS GRID </h1>

Para que o css grid funcione, o propriedade do display grid tem que entrar dentro do body, pois você vai estar informando que todo o body daquele site vai ser em css grid
```
    display:grid;
```

<h2>Grid-template</h2>

Precisamos dizer ao css grid quais são as partes do template (site todo) que vamos utilizar, e tambem nomear. 
No caso do grid-template-columns ou rows vai ser definido o tamanho das colunas e linhas, respectivamente.

```
    grid-template-areas: 
        "cabecalho"
        "conteudo"
        "rodape";
    grid-template-columns: auto;
    grid-template-rows: 50px auto auto;
```

Porém para que seja implementado o grid template areas, temos que definir no elemento que queremos, qual grid-area ele pertence.

```
    .cabecalho {
        grid-area: cabecalho;
    }
    
    .conteudo {
        grid-area: conteudo;
    }

    .rodape {
        grid-area: rodape;
    }
```

Para que fique mais claro como é feito o grid, temos o site em questão, na parte "destaques" vai ser definida com 4 colunas e 3 linhas, então se pega 100% da tela e divide pelas quantidades de colunas ou linhas:

```
    grid-template-columns: 25% 25% 25% 25%;
    grid-template-rows: 33.3% 33.3% 33.3%;
```

Depois precisamos definir a altura da seção "destaques", então, pegamos o 100vh (viewport height) e tiramos o tamanho do header (cabeçalho):

```
    height: calc(100vh -50px);
```

Para definir o tamanho de cada elemento, temos que definir onde a coluna começa e termina e a mesma coisa na linha também, então:
```
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 2;
```
Só que nesse caso vai dar erro, pois foi definido que vai terminar na coluna 3, então ele foi até a coluna 2 e parou, pois o ponto de parada dele foi até o 3. Mesma coisa acontece na linha, então temos que mudar isso, para isso:
```
    grid-column-start: 1;
    grid-column-end: 4;
    grid-row-start: 1;
    grid-row-end: 3;
```

Porém o código fica grande assim, então podemos diminuir isso:
```
    grid-column: 1 / 4;
    grid-row: 1 / 3;
```

Para fazer um espaçamento entre os grid's, se usa uma propriedade especifica do grid, e não mais o margin, o que vamos usar vai ser:
```
    grid-gap: .2rem;
```