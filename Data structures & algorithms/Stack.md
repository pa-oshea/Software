A stack is a linear data structure that follows the principle of **Last In First Out (LIFO)**. This means the last element inserted inside the stack is removed first.

You can think of the stack data structure as the pile of plates on top of another.

![[stack_plates.png]]

Here, you can:
- Put a new plate on top
- Remove the top plate

And, if you want the plate at the bottom, you must first remove all the plates on top. This is exactly how the stack data structure works.

![[stack_operations.png]]

#### Basic operations of stack

There are some basic operations that allow us to perform different actions on a stack.

- **Push**: Add an element to the top of a stack
- **Pop**: Remove an element from the top of a stack
- **Peek**: Get the value of the top element without removing it

##### Array implementation:
- **IsEmpty**: Check if the stack is empty
- **IsFull**: Check if the stack is full

## Implementation

#### Go
```go
type Node[T any] struct {
	Data T
	Next *Node[T]
}

type stack[T any] struct {
	length int
	top   *Node[T]
}

func (s *stack[T]) push(item T) {
	s.length++
	node := &Node[T]{Data: item}
	if s.top == nil {
		s.top = node
		return
	}
	node.Next = s.top
	s.top = node
}

func (s *stack[T]) pop() ( T, error ) {
	if s.length != 0 {
		s.length--
		result := s.top.Data
		s.top = s.top.Next
		return result, nil
	}
	var result T
	return result, errors.New("no item found")
}

func (s *stack[T]) peek() T {
	return s.top.Data
}
```

#### Javascript / Typescript
```ts
type node<T> = {
    value: T;
    next?: node<T>;
};

export default class Stack<T> {
    public length: number;
    public head?: node<T>;

    constructor() {
        this.head = undefined;
        this.length = 0;
    }

    push(item: T): void {
        const node: node<T> = { value: item };
        this.length++;
        if (!this.head) {
            this.head = node;
            return;
        }
        node.next = this.head;
        this.head = node;
    }

    pop(): T | undefined {
        const result = this.head?.value;

        if (this.head) {
            this.length--;
            this.head = this.head.next;
        }
        return result;
    }

    peek(): T | undefined {
        return this.head?.value;
    }
}
```
