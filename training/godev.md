# go.dev getting started guide

## enable dependency tracking for your code

when importing packages contained in other modules, you manage those dependencies through your code's own module. That module is defined by a go.mod file that tracks the modules that provide those packages. That *go.mod* file stays with your code, including in your source code repo.

To enable dependency tracking for your code by creating a *go.mod* file, run:

> go mod init

giving it the name of the module your code will be in. The name is the module's module path. In development, the module path will typically be the repo location where your source code will be kept.

For this example, I'm using the following:

> go mod init training/godev

We'll start with the following code:

### Code and Notes

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

* declar a *main* package (a package is a way to group functions, and it's made up of all the files in the same dir)
* import **fmt** package, which contains functions for formatting text, including printing to the console
    + [standard library functions](https://pkg.go.dev/std)
* implement a **main** function to print a message to the console. A main function executes by default when you run the **main** package.

### Run your code

> go run .

## Call code in an external package

When you need your code to do something that might have been implemented by someone else, you can look for a package that has functions you can use in your code.

We'll spice up the code with [this package](https://pkg.go.dev/rsc.io/quote/v4).

Use the following template to import the *quote* package.

```go
package main

import "fmt"

import "rsc.io/quote"

func main() {
    fmt.Println(quote.Go())
}
```

Don't forget to install the package!

![Using the quote package](../img/Screenshot-2024-04-18-195941.png)

---
