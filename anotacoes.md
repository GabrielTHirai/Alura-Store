#CSS GRID

Para que o css grid funcione, o propriedade do display grid tem que entrar dentro do body, pois você vai estar informando que todo o body daquele site vai ser em css grid
```
    display:grid;
```

##Grid-template

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

