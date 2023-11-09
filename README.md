# gophercon-australia-2023

Code Reviews - Top 5 Misses

## Description

Code Reviews in Go: Top 5 Misses stems from our time working together and the many code reviews we've done over the years. It's Go specific with frequently missed things in code reviews, and some of the standards that we use in our code reviews for Go projects.

## Slides

Can be found in this repo in PDF format

## PR Review Checklist

### Error Handling

- [ ] Should this error be wrapped?
- [ ] How can we leverage `error.Is`, `error.As`, `error.Unwrap`?
- [ ] Should we define custom errors here?
- [ ] How do we want to handle this behavior?
- [ ] Is it better to return an error or log?
- [ ] Is the handling of this error here sufficient?
- [ ] Is `defer`, `panic`, `recover` applicable here?

### Concurrency

- [ ] Do we need a Goroutine here, or is it simpler to run this synchronously?
- [ ] What does this Goroutine do?
- [ ] Do we need to use `WaitGroups` here to see when the goroutines have finished?
- [ ] Do we do anything to cap how many Goroutines can be spun up at once?

### Nil

- [ ] Is the zero value for this type nil? For pointers, maps, slice, functions, channels, interfaces.
- [ ] When a field is accessed, will a nil pointer occur?
- [ ] Is this an interface?
- [ ] Check nil on Interface types with switch on various types.
- [ ] Does this need to be mutable?
- [ ] Is this naturally a value type?
- [ ] How are we referring to the variable throughout the function?
- [ ] Are we copying a pointer in a loop?
- [ ] Are we copying synchronization fields?
- [ ] Is this pointer necessary?

### Interface and Testing 

- [ ] Can we consolidate this into one interface that supports both methods?
- [ ] Do we need all these functions, or can we have a smaller interface to pass in here?
- [ ] Could we use an interface for this so it can be a unit test?
- [ ] Do we do anything to cap how many Goroutines can be spun up at once?

### Style items to watch for

- [ ] Are the input fields validated as needed?
- [ ] Are the comments helpful and necessary?
- [ ] Is a comment needed here?
- [ ] Does the comment have the correct format and grammar?
- [ ] Is it lowercase, single word?
- [ ] Does it avoid repetition?
- [ ] Are the variable names clear, succinct, and readable?
- [ ] Is the slice declared as a nil slice value?

## References

- [Effective Go](https://go.dev/doc/effective_go)
- [Learning Go: Common Mistakes to Avoid](https://earthly.dev/blog/learning-golang-common-mistakes-to-avoid)
- [Code Reviews in Go](https://microsoft.github.io/code-with-engineering-playbook/code-reviews/recipes/go/)
- [Code Review Comments on Receiver Type](https://github.com/golang/go/wiki/CodeReviewComments#receiver-type)
- [YouTube Video: zskPGr5dFU0](https://www.youtube.com/watch?v=zskPGr5dFU0)
- [Awesome Go](https://awesome-go.com/)
- [Stack Overflow Question: Implicit Memory Aliasing in For Loop](https://stackoverflow.com/questions/62446118/implicit-memory-aliasing-in-for-loop)
- [Code Review Comments on Receiver Type (again)](https://github.com/golang/go/wiki/CodeReviewComments#receiver-type)
- [Code Review in Golang: Error Handling](https://sorawis.dev/blog/code-review-golang-error-handling)
- [Go Error Handling with Panic, Recovery, and Defer](https://www.developer.com/languages/go-error-handling-with-panic-recovery-and-defer/)
- [Defer, Panic, and Recover](https://go.dev/blog/defer-panic-and-recover)
- [Understanding Nil in Go](https://go101.org/article/nil.html)
- [Checking Nil Interface in Golang](https://bluehive.medium.com/how-to-check-nil-interface-in-golang-5a78a441bde2)
- [Uber Go Style Guide: Copy Slices and Maps at Boundaries](https://github.com/uber-go/guide/blob/master/style.md#copy-slices-and-maps-at-boundaries)


## Contact

- Sadie Freeman [linkedin](https://www.linkedin.com/in/sadie-f-589a5358)
- Quinn Hou [linkedin](https://www.linkedin.com/in/quinnhou)
