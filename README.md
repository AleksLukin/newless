using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace HomeWork211
{
    public static class Program
    {
        public class TestCase
        {
            public int NUMBER { get; set; }
            public int Excpected { get; set; }
            public Exception ExcpectedException { get; set; }
        }

        static void TestNumber(TestCase testCase)
        {
            try
            {
                var actual = CheckNumber(testCase.NUMBER);

                if (actual == testCase.Excpected)
                {
                    Console.WriteLine("действительный тест");
                }
                else
                {
                    Console.WriteLine("недействительный тест");
                }
            }

            catch (Exception ex)
            {
                if (testCase.ExcpectedException != null)
                {
                    Console.WriteLine("действительный тест");
                }
                else
                {
                    Console.WriteLine("недействительный тест");
                }
            }

        }

        static void Main(string[] args)
        {
            var testCase1 = new TestCase()
            {
                NUMBER = 5,
                Excpected = 5,
                
            };

            TestNumber(testCase1);

        }

        static int CheckNumber(int number)
        {
            number = int.Parse(Console.ReadLine());
            int d = 0;
            int i = 2;

            while (i < number)
            {
                if (number % i == 0)
                {
                    d++;
                }
                else
                {
                    i++;
                }
                if (d == 0)
                {
                    Console.WriteLine("d-простое число");
                }
                else
                {
                    Console.WriteLine("d-непростое число");
                }
                break;
            }
            return number;
        }
    }
}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace HW2_1_2
{
    class Program
    {
        static void Main(string[] args) //Вычислите асимптотическую сложность функции из примера
        {
        }
        public​ ​ static​ ​ int​ ​ StrangeSum​(​ int​[] inputArray)
        {
        int​ sum = ​ 0​ ;                                               
            ​ for​(​ int​ i = ​ 0​ ; i < inputArray.Length; i++)            ​ // O(N*N*N)
                {
                for( int j =  0 ; j < inputArray.Length; j++)          ​ // O(N*N)
                    { 
                     for( int​ k = ​ 0​ ; k < inputArray.Length; k++)      ​ // O(N)
                    {
                    int y = 0;

                    if (j != 0) 
                    {
                        y = k/ j;
                    }

                    sum += inputArray[i] + i + k + j + y; //O(1)
                    }
                }

            }
        return sum;                                  //O(1)               

        }//N*N*N 
    }
}
