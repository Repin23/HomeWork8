 Задайте двумерный массив. Напишите программу, которая упорядочит 
// по убыванию элементы каждой строки двумерного массива.
// // Например, задан массив:
// // 1 4 7 2
// // 5 9 2 3
// // 8 4 2 4
// // В итоге получается вот такой массив:
// // 7 4 2 1
// // 9 5 3 2
// // 8 4 4 2

// int[,] table = new int[3, 4];
// FillArrayRandom(table);
// PrintArray(table);
// SortToLower(table);
// Console.WriteLine();
// PrintArray(table);


// // Функция заполнения массива рандомно числами от 1 до 9
// void FillArrayRandom(int[,] array)
// {
//     for (int i = 0; i < array.GetLength(0); i++)
//     {
//         for (int j = 0; j < array.GetLength(1); j++)
//         {
//             array[i, j] = new Random().Next(1, 10);
//         }
//     }
// }

// // Функция сортировки элементов в строке двумерного массива, по убыванию
// void SortToLower(int[,] array)
// {
//     for (int i = 0; i < array.GetLength(0); i++)
//     {
//         for (int j = 0; j < array.GetLength(1); j++)
//         {
//             for (int k = 0; k < array.GetLength(1) - 1; k++)
//             {
//                 if (array[i, k] < array[i, k + 1])
//                 {
//                     int temp = array[i, k + 1];
//                     array[i, k + 1] = array[i, k];
//                     array[i, k] = temp;
//                 }
//             }
//         }
//     }
// }

// // Функция вывода двумерного массива
// void PrintArray(int[,] array)
// {
//     for (int i = 0; i < array.GetLength(0); i++)
//     {
//         for (int j = 0; j < array.GetLength(1); j++)
//         {
//             Console.Write($"{array[i, j]} ");
//         }
//         Console.WriteLine();
//     }
// }


// 2. Задайте прямоугольный двумерный массив. 
// Напишите программу, которая будет находить строку с наименьшей суммой элементов.

// int[,] arr = {
//     {1, 4, 7, 2},
//     {5, 9, 2, 3},
//     {8, 4, 2, 4},
//     {5, 2, 6, 7}
//   };

//   printArray(arr);

//   int row = arr.GetUpperBound(0) + 1;
//   int cal = arr.Length / row;

//   int[] counts = new int[row];

//   for (int i = 0; i < row; i++)
//     for (int j = 0; j < cal; j++)
//       counts[i] += arr[i, j];

//   int min = int.MaxValue;
//   int idx = 0;
//   for (int i = 0; i < counts.Length; i++)
//   {
//     if (counts[i] < min)
//     {
//       min = counts[i];
//       idx = i;
//     }
//   }

//   Console.WriteLine(idx);


//   3. Задайте две матрицы. 
//   Напишите программу, которая будет 
//   находить произведение двух матриц
//   using System;

// class Program
// {
//   public static void Main(string[] args)
//   {
//     int[,] A = {
//       {1,2},
//       {3,4}
//     };

//     int[,] B = {
//       {5,6,7},
//       {8,9,10}
//     };

//     int rowA = A.GetUpperBound(0) + 1;
//     int colA = A.Length / rowA;

//     int rowB = B.GetUpperBound(0) + 1;
//     int colB = B.Length / rowB;

//     int[,] C = new int[rowB, colB];

//     if (colA == rowB)
//     {
//       for (int i = 0; i < rowB; i++)
//         for (int l = 0; l < colA; l++)
//           for (int j = 0; j < colB; j++)
//             C[l, j] += A[l, i] * B[i, j];
//     }
//     else
//     {
//       Console.WriteLine($"Такую матрицу перемножать нельзя");
//     }

//     printArray(A);
//     printArray(B);
//     printArray(C);
//   }

//   private static void printArray(int[,] arr)
//   {
//     Console.WriteLine();

//     int row = arr.GetUpperBound(0) + 1;
//     int col = arr.Length / row;

//     for (int i = 0; i < row; i++)
//     {
//       for (int j = 0; j < col; j++)
//         Console.Write($"{arr[i, j]} ");
//       Console.WriteLine();
//     }
//   }
// } 

// 4. Сформируйте трёхмерный массив из неповторяющихся двузначных чисел. 
// Напишите программу, которая будет построчно 
// выводить массив, добавляя индексы каждого элемента.

// Random r = new Random();

//   int M = 2, N = 2, K = 2;

//   int[,,] arr = new int[M, N, K];

//   for (int i = 0; i < M; i++)
//   {
//     for (int j = 0; j < N; j++)
//     {
//       for (int l = 0; l < K; l++)
//       {
//         arr[i, j, l] = r.Next(10, 99);
//         Console.Write($"{arr[i, j, l]}({i},{j},{l}) ");
//       }
//       Console.WriteLine();
//     }
//   } 

// // 5. Напишите программу, которая заполнит спирально массив 4 на 4.

// int M = 5, N = 10;
//   int[,] arr = new int[M, N];

//   int i = 0;
//   int j = -1;

//   int row = 0;
//   int col = 1; // начинаем движение в право

//   int t = 1;
//   while (t <= M * N)
//   {
//     if (
//           (i + row >= 0 & i + row < M) &&
//           (j + col >= 0 & j + col < N) &&
//           arr[i + row, j + col] == 0
//         )
//     {
//       i += row;
//       j += col;
//       arr[i, j] = t++;
//     }
//     else if (col == 1)
//     {
//       row = 1;
//       col = 0;
//     }
//     else if (row == 1)
//     {
//       col = -1;
//       row = 0;
//     }
//     else if (col == -1)
//     {
//       col = 0;
//       row = -1;
//     }
//     else if (row == -1)
//     {
//       row = 0;
//       col = 1;
//     }
//   }

//   for (i = 0; i < M; i++)
//   {
//     for (j = 0; j < N; j++)
//       Console.Write("{0,4}", arr[i, j]);
//     Console.WriteLine();
//   } 
