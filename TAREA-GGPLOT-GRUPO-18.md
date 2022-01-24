TAREA GGPLOT GRUPO 18
================
ALVAREZ, SANCHEZ, TORRES
22/1/2022

# Ejercicios

### Instalamos el paquete “tidyverse”, “ggplot2” y “datos”

``` r
library(tidyverse)
```

    ## Warning: package 'tidyverse' was built under R version 4.1.2

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.1 --

    ## v ggplot2 3.3.5     v purrr   0.3.4
    ## v tibble  3.1.6     v dplyr   1.0.7
    ## v tidyr   1.1.4     v stringr 1.4.0
    ## v readr   2.1.1     v forcats 0.5.1

    ## Warning: package 'ggplot2' was built under R version 4.1.2

    ## Warning: package 'tidyr' was built under R version 4.1.2

    ## Warning: package 'readr' was built under R version 4.1.2

    ## Warning: package 'purrr' was built under R version 4.1.2

    ## Warning: package 'dplyr' was built under R version 4.1.2

    ## Warning: package 'forcats' was built under R version 4.1.2

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(ggplot2)
library(datos)
```

    ## Warning: package 'datos' was built under R version 4.1.2

``` r
millas=(datos::millas)
head(millas)
```

    ## # A tibble: 6 x 11
    ##   fabricante modelo cilindrada  anio cilindros transmision traccion ciudad
    ##   <chr>      <chr>       <dbl> <int>     <int> <chr>       <chr>     <int>
    ## 1 audi       a4            1.8  1999         4 auto(l5)    d            18
    ## 2 audi       a4            1.8  1999         4 manual(m5)  d            21
    ## 3 audi       a4            2    2008         4 manual(m6)  d            20
    ## 4 audi       a4            2    2008         4 auto(av)    d            21
    ## 5 audi       a4            2.8  1999         6 auto(l5)    d            16
    ## 6 audi       a4            2.8  1999         6 manual(m5)  d            18
    ## # ... with 3 more variables: autopista <int>, combustible <chr>, clase <chr>

## Pregunta N°2

### ¿Qué no va bien en este código? ¿Por qué hay puntos que no son azules?

``` r
 ggplot(data = millas) +
   geom_point(mapping = aes(x = cilindrada, y = autopista, color = "blue"))
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

### Corrección

``` r
ggplot(data = millas) +
    geom_point(mapping = aes(x = cilindrada, y = autopista), color = "blue")
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

###¿Qué variables en millas son categóricas? ¿Qué variables son
continuas? (Pista: escribe ?millas para leer la documentación de ayuda
para este conjunto de datos). ¿Cómo puedes ver esta información cuando
ejecutas millas? ###Asigna una variable continua a color, size, y shape.
¿Cómo se comportan estas estéticas de manera diferente para variables
categóricas y variables continuas? ###¿Qué ocurre si asignas o mapeas la
misma variable a múltiples estéticas?

``` r
ggplot(millas, aes(x = cilindrada, y = autopista, colour = autopista, size = autopista)) +
    geom_point()
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

### ¿Qué hace la estética stroke? ¿Con qué formas trabaja? (Pista: consulta ?geom_point)

``` r
ggplot(mtautos, aes(peso, millas)) +
    geom_point(shape = 21, colour = "black", fill = "white", size = 5, stroke = 5)
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

### ¿Qué ocurre si se asigna o mapea una estética a algo diferente del nombre de una variable, como aes(color = cilindrada \< 5)?

``` r
ggplot(millas, aes(x = cilindrada, y = autopista, colour = cilindrada < 5)) +
    geom_point()
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

## Pregunta N°6

### ¿Cuál es el problema con este gráfico? ¿Cómo podrías mejorarlo?

``` r
ggplot(data = millas, mapping = aes(x = ciudad, y = autopista)) +
  geom_point()
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

### Corrección

``` r
ggplot(data = millas, mapping = aes(x = ciudad, y = autopista)) +
    geom_point()
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

### ¿Qué parámetros de geom_jitter() controlan la cantidad de ruido?

``` r
ggplot(data = millas, mapping = aes(x = ciudad, y = autopista)) +
    geom_jitter()
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

``` r
ggplot(data = millas, mapping = aes(x = ciudad, y = autopista)) +
    geom_jitter(height = 0.5)
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-9-2.png)<!-- -->

### Compara y contrasta geom_jitter() con geom_count()

``` r
ggplot(data = millas, mapping = aes(x = ciudad, y = autopista)) +
    geom_jitter()
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-10-1.png)<!-- -->

``` r
ggplot(data = millas, mapping = aes(x = ciudad, y = autopista)) +
    geom_count()
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-10-2.png)<!-- -->

### ¿Cuál es el ajuste de posición predeterminado de geom_boxplot()? Crea una visualización del conjunto de datos de millas que lo demuestre.

``` r
ggplot(data = millas, mapping = aes(x = ciudad, y = autopista,notch=T,color=clase)) +
    geom_boxplot()+
    coord_flip()
```

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

``` r
ggplot(data = millas, mapping = aes(x = ciudad, y = autopista,shape=clase)) +
    geom_jitter()
```

    ## Warning: The shape palette can deal with a maximum of 6 discrete values because
    ## more than 6 becomes difficult to discriminate; you have 7. Consider
    ## specifying shapes manually if you must have them.

    ## Warning: Removed 62 rows containing missing values (geom_point).

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-12-1.png)<!-- -->

``` r
ggplot(data = millas, mapping = aes(x = ciudad, y = autopista,color=clase, shape=clase)) +
    geom_jitter()
```

    ## Warning: The shape palette can deal with a maximum of 6 discrete values because
    ## more than 6 becomes difficult to discriminate; you have 7. Consider
    ## specifying shapes manually if you must have them.

    ## Warning: Removed 62 rows containing missing values (geom_point).

![](TAREA-GGPLOT-GRUPO-18_files/figure-gfm/unnamed-chunk-12-2.png)<!-- -->
