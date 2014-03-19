Coursera Discrete Optimization HW - Graph Coloring
==================================================

Coursera course: [Discrete Optimization](https://www.coursera.org/course/optimization) ([session 2](https://class.coursera.org/optimization-002), March 2014)

This is to visualize and get a sense of the assignment's data sets.

Usage
-----

1. Run RStudio
1. Load up `README.Rmd`
1. Modify `processData` function below to set the working directory to be the root of your assignment (where the `data/` directory can be found)
1. Click "Knit HTML" (or hit Ctrl-Shift-H)
1. All the figures below will be regenerated

---


```r
if (!require("igraph")) {
    install.packages("igraph", repos = "http://cran.rstudio.com/")
    library("igraph")
}
```

```
## Loading required package: igraph
```



Helpers
-------


```r

processData = function(dataFile, display = T) {
    setwd("~/cabinet/Personal/Education/2014 Coursera Discrete Optimization/hw/src/coloring")
    Table = read.table(dataFile, header = T)
    
    # (Note: if we had read in the data from file directly via `read.graph`, not
    # only would we not have been able to skip the header line but igraph would
    # have changed the node indexes to 1-based indexing by adding 1 to every
    # ID.)
    G = graph.data.frame(Table, directed = F)
    
    hist(degree(G), col = "lightgreen")
    
    if (display) {
        plot(G)
        plot(G, layout = layout.circle, vertex.size = 10 + 5 * log(degree(G)))
    }
    
}
```



gc_20_1
-------


```r
processData("data/gc_4_1")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-31.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-32.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-33.png) 

```r
processData("data/gc_20_1")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-34.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-35.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-36.png) 

```r
processData("data/gc_20_3")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-37.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-38.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-39.png) 

```r
processData("data/gc_20_5")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-310.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-311.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-312.png) 

```r
processData("data/gc_20_7")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-313.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-314.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-315.png) 

```r
processData("data/gc_20_9")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-316.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-317.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-318.png) 

```r
processData("data/gc_50_3")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-319.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-320.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-321.png) 

```r
processData("data/gc_70_7", F)
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-322.png) 

```r
processData("data/gc_100_5", F)
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-323.png) 

```r
processData("data/gc_250_9", F)
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-324.png) 

```r
processData("data/gc_500_1", F)
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-325.png) 

```r
processData("data/gc_1000_5", F)
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-326.png) 


