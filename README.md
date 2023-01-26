Задача: Написать программу, которая из имеющегося массива строк формирует новый массив из строк, длина которых меньше, либо равна 3 символам. Первоначальный массив можно ввести с клавиатуры, либо задать на старте выполнения алгоритма. При решении не рекомендуется пользоваться коллекциями, лучше обойтись исключительно массивами.

1. Программа стартует и создаем массив из 3 символов с помощью команд: 
        string[] arr1 = {"Hello", "2", "world", ":-)"};
		string[] arr2 = {"1234", "1567", "-2", "computer science"};
		string[] arr3 = {"Russia", "Denmark", "Kazan"};

2. Содание переменной и с помощью цикла проходим по переменным:
        int MAX_WORD_LENGTH = 3;
		
		string[] GetShortWordsArray(string[] array)
		{
			int length = array.Length;			
			string[] result = new string[length];
			int count = 0;
			
			for (int i = 0; i < length; i++)
			{
				if(array[i].Length <= MAX_WORD_LENGTH)
				{
					result[count] = array[i];
					count++;
				}
			}
			Array.Resize(ref result, count);
			
			return result;

3. Путем сравнения проверка исполнения цикла и как только доходим до 0 конец цикла. Печать данных на экран.
        void PrintArray(string[] array)
		{
			if(array.Length == 0)
			{
				Console.WriteLine("Array is empty");
			}
			else
			{
				Array.ForEach(array, (str) => Console.Write($"{str} "));
				Console.WriteLine();
			}
		}
		
		void PrintTask(string[] array)
		{
			Console.WriteLine("Source array:");
			PrintArray(array);
			string[] shortArray = GetShortWordsArray(array);
			Console.WriteLine($"Result array (words are less or equal than {MAX_WORD_LENGTH} symbols)");
			PrintArray(shortArray);
			Console.WriteLine();
		}
		
		PrintTask(arr1);
		PrintTask(arr2);
		PrintTask(arr3);    