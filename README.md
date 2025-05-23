# Symboa

A Python library for symbolic algebra manipulation that provides a clean and intuitive interface for mathematical expressions.

## Features

- Expression manipulation with support for basic arithmetic operations (+, -, *, /)
- Variable handling with symbolic computation
- Expression simplification
- Derivative computation
- Expression evaluation with variable substitution
- Parenthesized expression parsing
- Support for both numeric and symbolic computations

## Classes

### Core Classes

- `Expr`: Base class for all symbolic expressions
- `Var`: Represents variables in expressions (e.g., x, y, z)
- `Num`: Represents numerical values
- `BinOp`: Base class for binary operations

### Operations

- `Add`: Addition operation
- `Sub`: Subtraction operation
- `Mul`: Multiplication operation
- `Div`: Division operation

## Usage

### Creating Expressions

You can create expressions in two ways:

1. Using the object-oriented interface:

   ```python
   from symboa import Var, Num

   x = Var('x')
   y = Var('y')
   expr = (x * x) + (y * y)  # Creates x²+ y²
   ```

2. Using the string parser:

   ```python
   from symboa import make_expression

   expr = make_expression("((x*x) + (y*y))")  # Creates x²+ y²
   ```

### Expression Manipulation

```python
# Create variables
x = Var('x')
y = Var('y')

# Basic arithmetic
expr1 = x + y      # Addition
expr2 = x - y      # Subtraction
expr3 = x * y      # Multiplication
expr4 = x / y      # Division

# Complex expressions
expr5 = (x * x) + (y * y)  # x² + y²
```

### Evaluation

```python
expr = make_expression("((x*x) + (y*y))")
result = expr.evaluate({'x': 2, 'y': 3})  # Evaluates to 13
```

### Derivatives

```python
x = Var('x')
y = Var('y')
expr = (x * x) + y  # x² + y
dx = expr.deriv('x')  # Takes derivative with respect to x (result: 2x)
dy = expr.deriv('y')  # Takes derivative with respect to y (result: 1)
```

### Simplification

The library includes basic simplification rules:
- Adding/multiplying by 0
- Multiplying by 1
- Division by 1
- Basic numeric operations

```python
expr = make_expression("(0 + x)")
simplified = expr.simplify()  # Simplifies to x
```

## Error Handling

The library includes a custom `SymbolicEvaluationError` exception for handling evaluation errors, such as missing variable values during evaluation.

## Requirements

- Python 3.x

## License

See the [LICENSE](LICENSE) file for details.

