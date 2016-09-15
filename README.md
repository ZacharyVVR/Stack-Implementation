# Stack-Implementation

#include "stdafx.h"
#include <iostream>
#include <cassert>


using namespace std;

class Stack
{
	int array[10];
	int stackLength = 0;

public:
	void reset()
	{
		stackLength = 0;
		for (int x = 0; x < 10; x++)
			array[x] = 0;
	}
	bool push(int x)
	{
		while (stackLength < 10)
		{
			array[stackLength] = x;
			stackLength++;
			return true;
		}
		cout << "Stack is full\n";
		return false;
	}
	int pop()
	{
		assert(stackLength > 0);
		int length = stackLength;
		stackLength--;
		return array[length];
		
	}
	void print()
	{
		cout << "( ";
		for (int x = 0; x < stackLength; x++)
			cout << array[x] << ' ';
		cout << ")\n";
	}
};


int main()
{
	Stack stack;
	stack.reset();
	stack.print();
	stack.push(2);
	stack.push(9);
	stack.push(5);
	stack.print();
	stack.pop();
	stack.push(4);
	stack.push(7);
	stack.print();
	stack.pop();
	stack.pop();
	stack.print();
	return 0;
}
