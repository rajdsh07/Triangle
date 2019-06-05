# Triangle

Program -->

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace SENG8040_Assignment2
{
    class Program
    {
        public static int SelectAnyfromMenu()
        {
            string custInput = "";
            bool validSelection = false;

            while (validSelection == false)
            {
                Console.WriteLine("1. Enter triangle dimensions: ");
                Console.WriteLine("2. Exit");

                Console.WriteLine("\nHey Hi! Please select any one from the above Menu: \n");
                custInput = Console.ReadLine();

                if (custInput != "1" && custInput != "2")
                {
                    Console.WriteLine("Invalid Option, Select from [1-2]\n");
                }
                else
                {
                    validSelection = true;
                }
            }
            Console.WriteLine();
            return int.Parse(custInput);
        }
        static void Main(string[] args)
        {
            SelectAnyfromMenu();
            TriangleSolver.Analyze();
        }
    }
}
