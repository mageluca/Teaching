```R
#Import the experimental dataset (the file contains all experiments performed up to 4GPa)
exp_cpx<- read.delim("CPX_experiments.txt")
```


```R
#Number of experimental studies in which cpx was stable
length(unique(exp_cpx$Reference))
```


126



```R
#Plot the pressure and temperature at which the experiments were performed
plot(exp_cpx$T_K, exp_cpx$P_GPa, ylim=c(4,0), pch=19, col="red", 
     xlab="Experimental Temperature [K]", ylab="Experimental Pressure [GPa]")
```


    
![png](output_2_0.png)
    


Before attempting to model the data it is very important that you GET TO KNOW your data Prepare a seres of plot (using the commands at lines 43) to generate a series of diagrams and look for which elements give the strongest relationshiops between the chemistry of clinopyroxene and the intensive parameters at which the experiments were performed (i.e. Pressure and temperature).


```R
#Make some plots using all elements versus one of the intensive parameters of the experiments
plot(exp_cpx$CaO.cpx, exp_cpx$T_K, pch=19, col="grey", xlab="CaO cpx", ylab="Experimental temperature [K]")
plot(exp_cpx$MgO.cpx, exp_cpx$P_GPa, pch=19, col="grey", xlab="MgO cpx", ylab="Experimental pressure [GPa]")
```


    
![png](output_4_0.png)
    



    
![png](output_4_1.png)
    


Prepare diagrams that illustrate the relationships between the chemistry of the melt from which cpx grow and the cpx. What would you plot?


```R

```

What did you noticed looking at the relationships between cpx chemistry, pressure, temperature and the chemistry of the melt from which the cpx grow?

IT CAN BE USEFUL TO PLOT DATA USING COLOUR CONTOURING. IN THE FOLLOWING CASE WE PLOT THE EXPERIMENTAL PRESSURE VERSUS THE SILICA CONTENT OF CPX COLOUR CONTOURING FOR TEMPERATURE


```R
yvar <- exp_cpx$P_GPa
xvar <- exp_cpx$SiO2.cpx
ylab <- "Pressure (GPa)"
xlab <- "SiO2 (wt. %)"
symbol <- 19
symbol.size <- 2

colourvar <- exp_cpx$T_K
colourvarname <- "Temperature (K)"
n.colours <- 5
pal <- colorRampPalette(c("red", "yellow"))
legend.position <- "topleft"

col.points <- pal(n.colours)[cut(colourvar,breaks = n.colours)] #do not change
plot(xvar,yvar,pch=symbol,col=col.points,cex=symbol.size,xlab=xlab,ylab=ylab) #do not change
legend(legend.position,title = colourvarname,legend = round(c(min(exp_cpx$T_K),max(exp_cpx$T_K)),0),col = pal(2), pch = symbol) #do not change
```


    
![png](output_8_0.png)
    


Make a series of plot to see if you can see any interesting relationship between cpx chemistry pressure and temperature (using colour contouring)


```R

```
