//Задайте прямоугольный двумерный массив. Напишите программу, которая будет находить строку с наименьшей суммой элементов.

//Например, задан массив:

//1 4 7 2

//5 9 2 3

//8 4 2 4

//5 2 6 7

//Программа считает сумму элементов в каждой строке и выдаёт номер строки с наименьшей суммой элементов: 1 строка

Console.WriteLine("Введите количество строк: ");

int m = Convert.ToInt32(Console.ReadLine());

Console.WriteLine("Введите количество столбцов: ");

int n = Convert.ToInt32(Console.ReadLine());

int[,] a = new int[m,n];

for (int i = 0; i < m;i++)

{

    for (int j =0; j<n; j++)
    
    {
    
        a[i,j] = new Random().Next(0,100);
        
        Console.Write(string.Format("{0} ", a[i, j]));
        
    }
    
    Console.Write(Environment.NewLine + Environment.NewLine);
    
}

int min = 0;

for (int j =0;j<n;j++)

{
    min = min + a[0,j];
}

int l =0;

for (int i = 0; i < m;i++)


{
    int k =0;
    
    for (int j =0; j<n; j++)
    
    {
        k = k + a[i,j]; 
    }
    
    if (k<min)
    
    {
    
        min = k;
        
        l = i;
        
    }
    
}

Console.WriteLine($"Строка с наименьшей суммой элементов - {l}");
