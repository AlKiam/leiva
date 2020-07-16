# Leiva, the definitive low-level programming language
## Download & Installation
There are not actual releases, since this language is a prototype. 

## How Leiva works:
Leiva is written primary in [C](https://es.wikipedia.org/wiki/C_(lenguaje_de_programaci%C3%B3n)) and its resultant code is compiled with [gcc](https://github.com/gcc-mirror/gcc). This gives Leiva a powerful typed and the speed and the low-level of C.

##### How it works?
**interpreter:**
```
leiva
  └─ parse
       └─ interpretation
            └─ output
```

**compiler:**
```
leiva
  └─ parse
       └─ translation to C
            └─ gcc compiles the C source code
                 └─ executable
```

## Compilation

#### If you want to interpret your code use:
```
leiva main.lei
```

#### If you want to compile and create an executable of your code use:
```
leiva build main.lei -o executable
```

## Examples
#### Hello World:
```julia
println("Hello World!!!")
```
```
Hello World!!!
```
#### Fibbonacci numbers:
```julia
fn fib(n: i32) -> i32 {
  if n <= 1 {
    return n
  }
  else {
    return fibb(n - 1) + fibb(n - 2)
  }
}
  

fn main() {
  for let i = 0; i < 10; i++ {
    print(fib(i), "")
  }
}

```
```
0 1 1 2 3 5 8 13 21 34
```

#### Double return:
```julia
fn swap(a: *GenericType, b: *GenericType) {
  *a, *b = *b, *a
}
  

fn pair() -> ([]i32, string) { 
  return [], "Here I return an array to you."
}

fn main() {
  a, b = 10, 6

  println(a, b) # Before
  swap(&a, &b)
  println(a, b, "\n") # After

  arr, str = pair()
  println(arr)
  println(str)
}
```
```
10 6
6 10

[]
Here I return an array to you.
```

#### Object Oriented:
```julia
struct OwnArray<T> {
  priv data: []T
  
  pub constr(data: []T) 
  {
    self.data = data
  }

  pub constr(data: ... T) {      # In order to put infinite arguments
    for value, index in data
      self.data[index] = value
  }
  
  pub fn size() -> size {
    return len(self.data)
  }
  
  
  pub operator self() -> []T {
    return self.data
  }
    
}
fn main():
  a = OwnArray<i32>([1, 2, 3]) # 1st constructor
  b = OwnArray<i32>(1, 2, 3)   # 2nd constructor
  
  println(a, b)
  
```
```
[1, 2, 3] [1, 2, 3]
```

## Leiva by examples:
| Nº            | Tutorial      | Complexity      |
| ------------- |:-------------:|:---------------:|
| 1             | [Hello World!!!](https://github.com/AlKiam/Leiva/tree/master/Examples/Hello%20World) | Easy |
| 2             | [Primitives](https://github.com/AlKiam/Leiva/tree/master/Examples/Primitives) | Easy |
| 3             | [Pointers](https://github.com/AlKiam/Leiva/tree/master/Examples/Pointers) | Medium |
| 4             | [Custom types](https://github.com/AlKiam/Leiva/tree/master/Examples/Custom%20Types) | Easy |

###### Note:
A hipotetical new programming language. Syntax and functions are prototypes.
