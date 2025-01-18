# Implement Stack using Array
### Initialize an Array to represent the Stack
### Use the end of the array to represent the top of stack
### Implement *push*, *pop* and *peek*
```cpp
typedef struct stack_t
{
  int top;
  unsighed capacity;
  int* array;
}stack_t;
stack_t * createStack(unsigned capacity)
{
  stack_t *stack=(stack_t*)malloc(sizeof(stack_t));
  stack->capacity=capacity;
  stack->top = -1;
  stack->array=(int*)malloc(stack->capacity*sizeof(int));
  return stack;
}
int isFull(stack_t* stack)
{
  return stack->top==stack->capacity-1;
}
int isEmpty(stack_t* stack)
{
  return stack->top==-1;
}
void push(stack_t *stack,int item)
{
  if(isFull(stack))
  {
    printf("\nStack is Full!!!\n");
    return;
  }
  stack->array[stack->++top]=item;
  printf("\n%d is pushed to stack\n",item);
}
int pop(stack_t* stack)
{
  if(isEmpty(stack))
  {
    printf("\nStack is Empty!!!\n");
    return INT_MIN;
  }
  return stack->array[stack->--top];
}
int seek(stack_t * stack)
{
  if(isEmpty(stack))
  {
    printf("\nStack is Empty!!!\n");
    return INT_MIN;
  }
  return stack->array[stack->top];
}
void main()
{
    stack_t *stack = createStack(10);
    push(stack,1);
}


