## VI.1
The following code computes the product of a and b. What is its runtime?

```
  def product(a, b)
    sum = 0
    i = 0
    while i < b
      sum += a
      i += 1
    end
  end
```

### Answer
The runtime of the above should be O(b) or Linear Time

## VI.2
The following code computes a**b. What is the runtime?

```
  def power(a, b)
    if b < 0
      0
    elsif b == 0
      1
    else
      a * power(a , b - 1)
    end 
  end

```

### Answer 
Finishes in linear time O(b).

## VI.3
The following code computes a % b. What is the runtime?
```
  def mod(a, b)
    if b <= 0
      -1
    end
    div = a / b
    a - (div * b)
  end
```

### Answer
Constant time O(1)

## VI.4
The following code performs integer division. Assume a and b are both positive.

```
  def div(a, b)
    count = 0
    sum = b
    while sum <= a
      sum += b
      count += 1
    end

    count
  end
```

### Answer 
Linear Time O(a/b)

## VI.5
The following code computes the [integer] square root of a number. If the number is not a perfect square (there is no integer square root), then it returns -1. It does this by successive guessing. If n is 100, it first guesses 50. Too high? Try something lower - halfway between 1 and 50. What is its runtime?

```
  def sqrt(n)
    sqrt_helper(n, 1, n)
  end

  def sqrt_helper(n, min, max)
    return -1 if max < min
    guess = (min + max) / 2

    if guess * guess == n
      guess
    elsif guess * guess < n
      sqrt_helper(n, guess + 1, max)
    else
      sqrt_helper(n, min, guess - 1)
    end
  end


```

### Answer
Logarithmic Time O(logN)

## VI.6
The following code computes the [integer] square root of a number. If the number is not a perfect square (there is no integer square root), then it returns -1. It does this by trying increasingly large numbers until it finds the right value (or is too high). What is its runtime?

```
  def sqrt(n)
    guess = 1
    while (guess * guess <= n)
      if (guess * guess) == n
        return guess
      else
        guess += 1
      end
    end
    -1
  end
```

### Answer 
O(n) or linear time

## VI.7
If a binary search tree is not balanced, how long might it take (worst case) to find an element?

### Answer


