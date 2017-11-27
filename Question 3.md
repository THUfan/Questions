	Question 3
	/******************************************************************************/
	Question 3
	题目一：找出数组中重复的数字。
	在一个长度为n的数组中的所有数字都在0~n-1的范围内。数组中某些数字是重复的	，但不知道
	有哪几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。例如，
	如果输入长度为7的数组{2,3,1,0,2,5,3}，那么对应的重复的数字2或3.
	/******************************************************************************/
	解答：
	bool duplicate(int number[], int length, int* duplication)
	{
		if(numbers == nullptr || length <= 0)
		{
			return false;
		}
		
		for (int i = 0; i < length; i++)
		{
			if(numbers[i] < 0 || numbers[i] > length - 1 )
				return false;
		}
		
		for(int i = 0; i < length; i++)
		{
			while(numbers[i] != i)
			{
				if numbers[i] == numbers[numbers[i]]
				{
					*duplication = numbers[i];
					return true;
				}
			
			int temp = numbers[i];
			numbers[i] = numbers[temp];
			numbers[temp] = temp;
			}
		}
	return false;
	}
	/******************************************************************************/
	
	/******************************************************************************/
	Question 3
	题目二：不修改数组找出重复的数字。
	在一个长度为n+1的数组里的所有数字都在1~n的范围内，所以数组中至少有一个数字是重复的，
	请找出数组中任意一个重复的数字，但不能修改已输入的数组。例如，如果输入的长度为8的数组
	{2,3,5,4,3,2,6,7}，那么对应的输出是重复数字2或者3。
	/******************************************************************************/
	解答：
	int getDuplication(const int* numbers,int length)
	{
		if(numbers == nullpter || length <= 0)
			return -1;
		int start = 1;
		int end = length - 1;
		while(end >= start)
		{
			int middle = ((end - start) >> 1 ) + start;
			int count = countRange(numbers.length,start,middle);
			if(end == start)
			{
				if(cout > 1)
					return start;
				else
					break;
			}
			
			if(countr > middle - start + 1)
				end = middle;
			else
				start = middle + 1;
		}
		return -1;
	}

	int countRange(const int* numbers,int length,int start,int end)
	{
		if(numbers == nullptr)
			return 0;
		
		int count = 0;
		for(int i =0;i < length, i++ )
			if(numbers[i] >= start && numbers[i] <= end)
				++count;
		return count;
	}
	/******************************************************************************/
	
	
	
