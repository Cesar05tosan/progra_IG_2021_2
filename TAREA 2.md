# progra_IG_2021_2---
title: "TAREA 2"
author: "Alvarez Manuel, Sanchez Cesar, Torres Jesus"
date: "25/11/2021"
output: github_document
---
# 01
```{r}
10000%%3
```

# 02
```{r}
0 == (4560%%3)
```

# 03
```{r}
numeros_enteros <- c(2:87)
divisibles_7 <- (0 == numeros_enteros%%7)
which(divisibles_7 == TRUE)
numeros_enteros[c(6,13,20,27,34,41,48,55,62,69,76,83)]
```

# 04
```{r}
primer_vector <- c(seq(7,3,-1))
segundo_vector <- c(head(seq(0,100,5),5))
```

# 4.1
```{r}
A <- (0 == primer_vector%%2)
which(A == TRUE)
primer_vector [c(2,4)]
```

# 4.2
```{r}
B <- which(segundo_vector >10)
segundo_vector [c(4,5)]
```

# 4.3
```{r}
z<-rep(x=1,times=25) 
((2^z)/z+(3^z)/(z^2))
sum(((2^z)/z+(3^z)/(z^2)))
```

# 06
```{r}
jaa<-c(1,-4,5,9,-4)
min(jaa)
which(jaa ==-4)
```


# 07
```{r}
factorial(5)
```

# 08
```{r}
sum(sumatoria<-exp(3:7))
```

# 09
```{r}
a<-1:10
b<-log(sqrt(a))
c<-prod(b)
```

# 10
```{r}
a<-function(x,y){((x^2)*(y-sin(y))/2)}
a(4,pi/2)
```

# 11
```{r}
vector<-c(8,9,10,11,12)
vector
u.u<-which(vector ==c(8,9,10,11,12))
u.u[order(-u.u)]
RAA<-sort(u.u,TRUE)
vector[RAA]
#Comparando con rev()
rev(vector)
```

# 12
```{r}
a<-(10:100)**3
b<-4*(10:100)**2
c<-sum(a)+sum(b)
```

# 13
```{r}
a<-2**(1:25)/(1:25)
b<-3**(1:25)/(1:25)**2
sum(a)+sum(b)
```

# 14
```{r}
#url<- "https://raw.githubusercontent.com/fhernanb/datos/master/Paises.txt"
#download.file(url,"mi_archivo.txt")

#GO<-read.delim("C:/Users/Nitro 5}/OneDrive/Documentos/ProgramaciÃ³n/Nueva carpeta/mi_archivo.txt",TRUE)
##NÃºmero de variables: 5
##NÃºmero de paÃ­ses: 107
##PaÃ­s con mayor poblaciÃ³n: China_
#GO
#apply(GO[c("poblacion")],2,max)
#MAX<-max(GO$poblacion)
#y<-c(GO$poblacion)
#GO$Pais[which.max(y)]
##PaÃ­s con alfabetizaciÃ³n mÃ¡s baja: Busrkina_Faso
#j<-min(GO$alfabetizacion)
#GO$Pais[which(GO$alfabetizacion==j)]
```

# 15
```{r}
mtcars[mtcars$mpg<18,]   ##a
mtcars[mtcars$cyl==4,]   ##b
mtcars[mtcars$wt>2.500 & mtcars$am==1,]   ##c
```

# 16
```{r}
#library(ggplot2)
#library(extrafont)

#x<-(0:365)
#y<- 2*pi*(x-81)/365
#y
#Minutos<-iy[c(1,31,61,91,121,151,181,211,241,271,301,331,361)]
#jaaa<-factor(je,labels=c("Enero","Febrero","Marzo","Abril","Mayo","Junio","Julio","Agosto","Setiembre","Octubre","Noviembre","Diciembre","Enero"))
#iy<- (9.87*sin(2*y)-7.53*cos(y)-1.5*sin(y))
#iy
#plot(jaaa,Minutos,main="EcuaciÃ³n del tiempo",sub="Mathematical Astronomy Morsels, Jean Meeus. 1997",xlab="Meses",ylab="Minutos", col="red",type="l")
#grid(26,12,lty=2,col="gray",lwd=1)


#df<-data.frame(jaaa,Minutos)
#  Grafico=ggplot(df,aes(x=jaaa, y=Minutos))+geom_line(color=4,linetype="dashed")
#  Grafico
  
#  ggplot(df,aes(x=jaaa, y=Minutos, fill=jaaa))+geom_line(color=4,linetype="dashed")
```
