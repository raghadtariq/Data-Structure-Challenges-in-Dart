# Stacks:

## Challenge 1: Reverse a List
**Create a function that prints the contents of a list in reverse order.**

Sol:
```dart
class Stack<T> {
  List<T> _items = [];

  void push(T item) {
    _items.add(item);
  }

  T pop() {
    if (_items.isEmpty) {
      throw StateError('Cannot pop from an empty stack.');
    }
    return _items.removeLast();
  }

  bool get isEmpty => _items.isEmpty;
}

void reverseList(List<dynamic> inputList) {
  Stack<dynamic> stack = Stack();

  for (var item in inputList) {
    stack.push(item);
  }

  print('Reversed List:');
  while (!stack.isEmpty) {
    print(stack.pop());
  }
}

void main() {
  List<int> originalList = [1, 2, 3, 4, 5];
  print('Original List:');
  originalList.forEach(print);

  reverseList(originalList);
}
```
-------------------------------------------------------------------------------------------------------
## Challenge 2: Balance the Parentheses
**Check for balanced parentheses. Given a string, check if there are ( and ) characters, and return true if the parentheses in the string are balanced.**

Sol:
```dart
class Stack<T> {
  List<T> _items = [];

  void push(T item) {
    _items.add(item);
  }

  T pop() {
    if (_items.isEmpty) {
      throw StateError('Cannot pop from an empty stack.');
    }
    return _items.removeLast();
  }

  bool get isEmpty => _items.isEmpty;
}

bool areParenthesesBalanced(String input) {
  Stack<String> stack = Stack();

  for (var char in input.runes) {
    if (String.fromCharCode(char) == '(') {
      stack.push('(');
    } else if (String.fromCharCode(char) == ')') {
      if (stack.isEmpty) {
        return false; // Unbalanced parentheses
      } else {
        stack.pop();
      }
    }
  }

  return stack.isEmpty;
}

void main() {
  String balancedString = 'h((e))llo(world)()';
  print('$balancedString - Balanced: ${areParenthesesBalanced(balancedString)}');

  String unbalancedString = '(hello world';
  print('$unbalancedString - Balanced: ${areParenthesesBalanced(unbalancedString)}');
}

```
