# Call Stack

A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in script that calls multiple functions - what function is currently being run and what functions are called from within that fucntion, etc.

* When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
* Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
* When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
* If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.

```javascript
class Stack {
  constructor(...items) {
    this.reverse = false
    this.stack = [...items]
  }

  push(...items) {
    return this.reverse
      ? this.stack.unshift(...items)
      : this.stack.push(...items)
  }

  pop() {
    return this.reverse ? this.stack.shift() : this.stack.pop()
  }
}
```

## References
* https://developer.mozilla.org/en-US/docs/Glossary/Call_stack