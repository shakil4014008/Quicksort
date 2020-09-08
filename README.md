# Quicksort
```C#
using System;
using System.Collections.Concurrent;

namespace ConsoleApp9
{ 
    class Program
    {
        static void Main(string[] args)
        {
            int[] arr = { 23, 9, 18, 32, 61, 50, 4, 99, 3, 1, 555 , 0};
            QuickSort(arr, 0, arr.Length - 1);
            foreach(var item in arr)
            {
                Console.Write(item + " ");
            }
            
            Console.ReadLine();
        } 

        public static void QuickSort(int [] A, int p, int r)
        {
            int q;
            if(p < r)
            {
                q = Partition(A, p, r);
                QuickSort(A, p, q - 1);
                QuickSort(A, q + 1, r);
            }
        }

        public static int Partition(int [] A, int p, int r)
        {
            int x = A[r];
            int i = p - 1; 
            for(int j=p; j < r -1; j++)
            {
                if(A[j] < x)
                {
                    i++;
                    int temp = A[j];
                    A[j] = A[i];
                    A[i] = temp;
                }
            }

            int temp2 = A[i + 1];
            A[i + 1] = A[r];
            A[r] = temp2;

            return i + 1;
        }
    } 
}


````
