# Functions

A function must return a value. The return type is not specified in the signature of a function.

A function must be declared above the place of its usage.

A function can be [annotated](/ride/functions/annotations.md).

There are multiple [built-in functions](/ride/functions/built-in-functions.md) in RIDE.

When declaring a function to the right of the "=" sign must be an [expression](/ride/base-concepts/expression.md). The value of the function is the [expression result](/ride/base-concepts/expression.md#expression-result).

## Examples

Definition of the function with no parameters that returns an integer:

``` ride
func main() = {
   3
}
```

Definition of a function with two parameters:

``` ride
func main(amount: Int, name: String) = {
   throw()
}
```
