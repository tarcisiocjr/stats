# Stats [![Build Status](https://img.shields.io/wercker/ci/548fca786b3ba8733d7f219d.svg)](https://app.wercker.com/project/bykey/2eafc5c6f7c702b53d967aef3b2bb65e) [![Coverage Status](https://img.shields.io/coveralls/montanaflynn/stats.svg)](https://coveralls.io/r/montanaflynn/stats?branch=master) [![GoDoc](https://godoc.org/github.com/montanaflynn/stats?status.svg)](https://godoc.org/github.com/montanaflynn/stats)

A simple stats package for Go that includes many common functions that are missing from the standard library. Pull requests are always welcome.

__The package is still in the early stages so expect the API to change.__ 

### Install

```go
go get github.com/montanaflynn/stats
```

### Usage

```go
package main

import (
    "fmt"
    "github.com/montanaflynn/stats"
)

func main() {
    m := stats.Min([]float64{1.1, 2, 3, 4, 5})
    fmt.Println(m) // 1.1

    m = stats.Max([]float64{1.1, 2, 3, 4, 5})
    fmt.Println(m) // 5

    m = stats.Sum([]float64{1.1, 2.2, 3.3})
    fmt.Println(m) // 6.6

    m = stats.Mean([]float64{1, 2, 3, 4, 5})
    fmt.Println(m) // 3

    m = stats.Median([]float64{1, 2, 3, 4, 5, 6, 7})
    fmt.Println(m) // 4

    s := stats.Mode([]float64{5, 5, 3, 3, 4, 2, 1})
    fmt.Println(s) // [5 3]

    m = stats.VarP([]float64{1,2,3,4,5})
    fmt.Println(m) // 2

    m = stats.VarS([]float64{1,2,3,4,5})
    fmt.Println(m) // 2.5

    m = stats.StdDevP([]float64{1, 2, 3})
    fmt.Println(m) // 0.816496580927726

    m = stats.StdDevS([]float64{1, 2, 3})
    fmt.Println(m) // 1

    m = stats.Percentile([]float64{1, 2, 3, 4, 5}, 75)
    fmt.Println(m) // 4

    m = stats.Round(5.3253543, 3)
    fmt.Println(m) // 5.325
}
```

### API

The [entire API documentation](http://godoc.org/github.com/montanaflynn/stats) is available on GoDoc.

### Todos

- Error checking in idiomatic Go style
- Add linear and exponential regression 

### MIT license

Copyright (c) 2014, Montana Flynn (http://anonfunction.com/)