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
