# Gráficos
 Gráficos com Matplotlib e Numpy. Gráficos com R e ggplot2. Agradecimento a Data Science Academy
***
# Gráfico com R e ggplot2

## Gráfico de Barras
```
barplot(vetor_total_resultados)
barplot(vetor_total_resultados, col=c(1,2,3,4,5)) # Cores
```
![image](https://user-images.githubusercontent.com/90532605/193432046-e037577c-3df5-41f5-a4de-5bfa701d3b8c.png)
***

## Gráfico de Barras Colorido
```
ggplot(mtcars, aes(x= as.factor(cyl), fill = as.factor(cyl) )) +
  geom_bar() + 
  scale_fill_manual(values = c("red", "green", "blue"))
```
![image](https://user-images.githubusercontent.com/90532605/193432113-53df08be-dd0e-4270-9dbe-33f6ef99db3b.png)

```
# Dados dummy
dados <- data.frame(group = c("A", "B", "C", "D"), value = c(33,62,56,67))

# Barplot
ggplot(dados, aes(x= group, y= value, fill= group )) +
  geom_bar(width=0.85, stat= "identity")
```
![image](https://user-images.githubusercontent.com/90532605/193432143-85b5d79b-78fd-46af-a0ba-aec5590309f9.png)
***

## Gráfico de Pizza
```
fatias <- c(1,2,3,4,5,12,15,18)
paises <- c("BR", "EUA", "AR", "CH", "RU", "ALE", "ING", "UCR")
pie(fatias, labels=paises, main="Leitura de livors por País")
```
![image](https://user-images.githubusercontent.com/90532605/193432162-d3a51b38-d2f2-42c4-90fa-330e63fd4d98.png)

```
#install.packages("plotrix")
library(plotrix)
pie3D(fatias, labels = paises, explode = 0.1, main="Leitura por País")
```
![image](https://user-images.githubusercontent.com/90532605/193432208-ebc9a7a2-7ac2-4945-a30d-a2a8fdb1b5b2.png)
***

## Gráfico de Linhas
```
# Dados
carros <- c(1,3,5,6,7)
caminhoes <- c(1,5,4,5,12)

# Plot
plot(carros, type="o", col= "blue", ylim= c(0,12))
lines(caminhoes, type="o", pch=22, lty=2, cl="red")
title(main="Produção de Veículos", col.main="red", font.main=4)
```
![image](https://user-images.githubusercontent.com/90532605/193432229-2875b433-5862-4fdf-8237-2184408015aa.png)
***

## Gráfico BoxPlot
```
# ----- BoxPlot: Ajuda a detectar outliers (Valores extremos)
ggplot(mpg, aes(x= reorder(class, hwy), y= hwy, fill= class)) +
  geom_boxplot() + 
  xlab("class") +
  theme(legend.position = "none")
```
![image](https://user-images.githubusercontent.com/90532605/193432246-80248458-4de6-4e6d-9e7e-ec84c16dadda.png)
***

## Gráfico de Dispersão
```
data <- data.frame(cond= rep(c("condition_1", "condition_2"), each=10),
                   my_x=1:100 + rnorm(100, sd=9), my_y=1:100 + rnorm(100, sd=16))

ggplot(data, aes(x=my_x, y=my_y)) + 
  geom_point(shape=1)
```
![image](https://user-images.githubusercontent.com/90532605/193432267-66b67a9d-f6ac-4a60-851e-efa3a98b7cd1.png)

```
# Adicionando linha de regressão
ggplot(data, aes(x=my_x, y=my_y)) +
  geom_point(shape=1) + 
  geom_smooth(method = lm, color="red", se=FALSE)
```
![image](https://user-images.githubusercontent.com/90532605/193432290-d414fc29-5498-47e8-b8ea-a4a7efd6f078.png)

```
# Adicionando SMOOTH
ggplot(data, aes(x=my_x, y=my_y)) +
  geom_point(shape=1) + 
  geom_smooth(method = lm, color="red", se=TRUE) #se= margem de erro
```
![image](https://user-images.githubusercontent.com/90532605/193432304-9468da05-dd0c-4787-9bd4-e32a47cec544.png)
