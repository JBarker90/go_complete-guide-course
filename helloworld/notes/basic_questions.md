# Five Basic Questions

### 1. How do we run the code in our project?

- You can `cd` to the directory where your file is located and use `go` command to run the program.

```
go run <file_name>
```

Example: This is running our file using `go run main.go`

```
jonathan@dockerhost-01:~/go_complete-guide-course/helloworld$ go run main.go
Hi there!
```

- Now what exactly is `go` doing and how does us run code?
	
	- Here is a breakdown of Go CLI and what it does:
		- `go build` - Compiles a bunch of go source code files
		- `go run` - Compiles and executes one or two files
		- `go fmt` - Formats all the code in each file in the current directory
		- `go install` - Compiles and "installs" a package
		- `go get` - Downloads the raw source code of someone else's package
		- `go test` - Runs any tests associated with the current project. 

### 2. What does `'package main'` mean?

- When you see "package" you can think of it as a equivalent to project or workspace. 

- Now every file should end with the file extension `.go`. But the main requirement is that every file needs to have the first line declare which "package" it belongs to.

Example:

"main.go":

```
package main

import "fmt"

func main() {
	fmt.Println("Hi there!")
}
```

"support.go":

```
package main

func support(){
	fmt.Println("I help!")
}
```

"helper.go":

```
package main

func help(){
	fmt.Println("I help too!")
}
```

- Why use the name `main` in declaring the package?
	- There are two types of packages:
		- Executable: Generates a file that we can run. (Like "main" package when we run "go build"). The name 'main' is special.
		- Reusable: Code used as 'helpers'. Good place to put reuseable logic.

### 3. What does `'import fmt'` mean?

- The import statement using 'fmt' is specifically importing a standard library included with the Go programming language.

- So when we use an import statement, it is telling the file to import a library into the package (in this case main). This allows the code to utilize the library. 

- Here is a link to the standard packages from Golang:
	- https://pkg.go.dev/std

### 4. What's that `'func'` thing?

- Similar to many other programming languages, `'func'` is used to declare a function. 

- From our Hello World program, the function that was declare is called `main`

```
func main() {
	fmt.Println("Hi there!")
}
```

### 5. How is the `main.go` file organized?

- It will always be organized the same way.

- Default Pattern:
	- `package main` : Package declaration
	- `import "fmt"` : Import other packages that we need
	- `func main(){}` : Declare functions, tell Go to do things