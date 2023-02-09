## Implementation

### go
```go
type Node[T any] struct {
	Data T
	Next *Node[T]
}

type Queue[T any] struct {
	Length      int
	first, last *Node[T]
}

func (q *Queue[T]) Enqueue(item T) {
	node := &Node[T]{Data: item}

	q.Length++
	if q.last == nil {
		q.last = node
		q.last.Next = node
		q.first = q.last
		return
	}

	q.last.Next = node
	q.last = node
}

func (q *Queue[T]) Dequeue() (T, error) {
	if q.first == nil {
		var result T
		return result, errors.New("first node is nil")
	}

	result := q.first.Data
	q.first = q.first.Next
	q.Length--
	if q.Length == 0 {
		q.last = nil
	}

	return result, nil
}

func (q *Queue[T]) Peek() T {
	return q.first.Data
}
```

### Typescript
```
```
```ts
type node<T> = {
    value: T;
    next?: node<T>;
};

export default class Queue<T> {
    public length: number;

    private head?: node<T>;
    private tail?: node<T>;

    constructor() {
        this.head = this.tail = undefined;
        this.length = 0;
    }

    enqueue(item: T): void {
        const node: node<T> = { value: item };
        this.length++;
        if (!this.tail) {
            this.tail = node;
            this.tail.next = node;
            this.head = this.tail;
            return;
        }
        this.tail.next = node;
        this.tail = node;
    }

    deque(): T | undefined {
        if (!this.head) {
            return;
        }
        const result = this.head?.value;
        this.head = this.head.next;
        this.length--;
        if (this.length === 0) {
            this.tail = undefined;
        }
        return result;
    }

    peek(): T | undefined {
        return this.tail?.value;
    }
}
```