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


TriangleSolver -->

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace SENG8040_Assignment2
{
    public class TriangleSolver
    {
        private int opt1;
        private int opt2;
        private int opt3;

        public TriangleSolver()
        {
            opt1 = 1;
            opt2 = 1;
            opt3 = 1;
        }

        public TriangleSolver(int opt1, int opt2, int opt3)
        {
            this.opt1 = opt1;
            this.opt2 = opt2;
            this.opt3 = opt3;
        }

        public static void Analyze()
        {
            try
            {
                int opt1;
                int opt2;
                int opt3;

                Console.Write("Enter Number 1: ");
                opt1 = Convert.ToInt32(Console.ReadLine());

                Console.Write("Enter Number 2: ");
                opt2 = Convert.ToInt32(Console.ReadLine());

                Console.Write("Enter Number 3: ");
                opt3 = Convert.ToInt32(Console.ReadLine());

                if (opt1 + opt2 > opt3 || opt2 + opt3 > opt1 || opt1 + opt3 > opt2)
                {
                    if (opt1 == 0 || opt2 == 0 || opt3 == 0)
                    {
                        Console.WriteLine("Zero is not allowed!");
                    }
                    if (opt1 < 0 || opt2 < 0 || opt3 < 0)
                    {
                        Console.WriteLine("Negatives not allowed!");
                    }
                    else
                    {
                        Console.WriteLine("A. It is a Triangle ");

                        if (opt1 == opt2 && opt2 == opt3)
                        {
                            Console.Write("This is an equilateral triangle.\n");
                        }
                        else if (opt1 == opt2 || opt1 == opt3 || opt2 == opt3)
                        {
                            Console.Write("This is an isosceles triangle.\n");
                        }
                        else
                        {
                            Console.Write("This is a scalene triangle.\n");
                        }
                    }
                }
                else
                {
                    Console.WriteLine("B. Not a Triangle");
                }
                Console.ReadLine();
            }
            catch (Exception)
            {
                Console.WriteLine("Invalid Character(s)!!!");
                Console.ReadLine();
            }
        }
    }
}
