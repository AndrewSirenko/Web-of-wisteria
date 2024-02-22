
## Key Moves

From [Learn Go with Tests: Refactoring and your tooling](https://quii.gitbook.io/learn-go-with-tests/go-fundamentals/install-go#refactoring-and-your-tooling)

Know how to:
- **Extract/Inline variable**. Being able to take magic values and give them a name lets you simplify your code quickly.
- **Extract method/function**. It is vital to be able to take a section of code and extract functions/methods
- **Rename**. You should be able to confidently rename symbols across files.
- **go fmt**. Go has an opinioned formatter called `go fmt`. Your editor should be running this on every file save.
- **Run tests**. You should be able to do any of the above and then quickly re-run your tests to ensure your refactoring hasn't broken anything.

You should also be able to:
- **View function signature**. You should never be unsure how to call a function in Go. Your IDE should describe a function in terms of its documentation, its parameters and what it returns.
- **View function definition**. If it's still not clear what a function does, you should be able to jump to the source code and try and figure it out yourself.
- **Find usages of a symbol**. Being able to see the context of a function being called can help your decision process when refactoring.


### Goland Shortcuts 
- opt-cmd
	- r: rename
	- v: extract var
	- m: extract method
- cmd-b: go to declaration
- right click: 
	- Find Usages
