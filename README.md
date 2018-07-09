using System;
using System.IO;
namespace Week4
{
    class SoftwareDeveloper
    {
        private string Name; // decleration of names
        private string Address;// decleration of address
        private string EmployeeType;// decleration of Employee types
        public double MonthlyPay;// decleration of monthly pay amount
       public double MonthlyTax;// decleration of monthly tax amount
        



        public SoftwareDeveloper(string n, string add, string type, double pay) // Software dev data info conversion for each employee
        {
            Name = n;
            Address = add;
            EmployeeType = type;
            MonthlyPay = pay;
        }
        public double getMonthlyTax() // returns monthly tax information Baised off of if the employee is W2 or 1099
        {
            if (EmployeeType.Equals("W2")) 
            {
                MonthlyTax = MonthlyPay * 0.07;
            }
            else if (EmployeeType.Equals("1099"))
            {
                MonthlyTax = MonthlyPay * 0;
            }
            else
            {
                MonthlyTax = 0;
            }
            return MonthlyTax; //where data returns and is used for annual taxes
        }
                
        public double getAnnualTax()// returns annual tax
        {
            return 12 * MonthlyTax;
        }
        public double getAnnualGrossPay()// returns annual gross pay
        {
            return 12 * MonthlyPay;
        }
        public void displayEmployee()// display Employee Details
        {
            Console.WriteLine("\nSoftware Developer Name: " + Name);
            Console.WriteLine("Address: " + Address);
            Console.WriteLine("Gross Monthly Pay: " + MonthlyPay);
            Console.WriteLine("Annual Gross Pay: " + getAnnualGrossPay());
            Console.WriteLine("Employee Type: " + EmployeeType);
            Console.WriteLine("Monthly Tax: " + getMonthlyTax());
            Console.WriteLine("Annual Tax: " + getAnnualTax());
        }
    }
    class Program // Data is read in this portion to display data at one time
    {
        static void Main(string[] args)
        {
            


            string name, address, employeeType;
            double pay;
            Console.WriteLine("Weclome");
            Console.WriteLine("Enter The first Employee's Details:");// Collects data of first employee 
            Console.Write("Name: ");
            bool check = false;
            name = Console.ReadLine();// collects name
            for (int i = 0; i < name.Length; i++)// checks for numbers and outputs error messige if name contains numbers
            {
                if (name[i] >= 'a' && name[i] <= 'z' || name[i] == ' ')
                {
                    check = true;
                }
                else
                {
                    check = false;
                }
            }
            if (check == false)
            {
                Console.WriteLine("Names do not contain numbers please try again");
                Console.WriteLine("");
                name = Console.ReadLine();
            }// checks for numbers and outputs error messige if name contains numbers
            Console.Write("Address: ");
            address = Console.ReadLine();//collects dev 1 Address
            Console.Write("Employee Type: ");
            employeeType = Console.ReadLine();
            employeeType = validateEmployeeType(employeeType);//collects dev 1 1099 or w2
            Console.Write("Gross Monthly Pay: ");
            try// collects pay data and verifys its a number
            {
                pay = double.Parse(Console.ReadLine());
            }
            catch
            {
                Console.WriteLine("Gross Monthly Pay must be a number. Please try again!");
                pay = double.Parse(Console.ReadLine());
            }// collects pay data and verifys its a number
            SoftwareDeveloper emp1 = new SoftwareDeveloper(name, address, employeeType, pay);//stores developer 1

          
            using (StreamWriter writer = new StreamWriter("E:\\Users\\jason\\source\\repos\\Week4redo.csv", true))
            {

                // Use string interpolation syntax to make code clearer.
                writer.WriteLine($" { name}{","}  {address}{","} {employeeType}{","} {pay} .");

            }


            Console.WriteLine("\nEnter The Second Employee's Details:");//Collects data of second employee
            Console.Write("Name: ");
            name = Console.ReadLine(); //collects name
            for (int i = 0; i < name.Length; i++)// checks for numbers and outputs error messige if name contains numbers
            {
                if (name[i] >= 'a' && name[i] <= 'z' || name[i] == ' ')
                {
                    check = true;
                }
                else
                {
                    check = false;
                }
            }
            if (check == false)
            {
                Console.WriteLine("Names do not contain numbers please try again");
                Console.WriteLine("");
                name = Console.ReadLine();
            }// checks for numbers and outputs error messige if name contains numbers
            Console.Write("Address: ");
            address = Console.ReadLine();//collects dev 2 address
            Console.Write("Employee Type: ");
            employeeType = Console.ReadLine();//collects dev 2 1099 or w2
            employeeType = validateEmployeeType(employeeType);
            Console.Write("Gross Monthly Pay: ");
            try// collects pay data and verifys its a number
            {
                pay = double.Parse(Console.ReadLine());
            }
            catch
            {
                Console.WriteLine("Gross Monthly Pay must be a number. Please try again!");
                pay = double.Parse(Console.ReadLine());
            }// collects pay data and verifys its a number
            SoftwareDeveloper emp2 = new SoftwareDeveloper(name, address, employeeType, pay);//stores developer 2

            
            using (StreamWriter writer = new StreamWriter("E:\\Users\\jason\\source\\repos\\Week4redo.csv", true))
            {

                // Use string interpolation syntax to make code clearer.
                writer.WriteLine($" { name}{","}  {address}{","} {employeeType}{","} {pay}.");

            }


            Console.WriteLine("\nEnter The Third Employee's Details:");  // Collects data of third employee 
            Console.Write("Name: ");            
            name = Console.ReadLine();//collects name
            for (int i = 0; i < name.Length; i++)// checks for numbers and outputs error messige if name contains numbers
            {
                if (name[i] >= 'a' && name[i] <= 'z' || name[i] == ' ')
                {
                    check = true;
                }
                else
                {
                    check = false;
                }
            }
            if (check == false)
            {
                Console.WriteLine("Names do not contain numbers please try again");
                Console.WriteLine("");
                name = Console.ReadLine();
            }// checks for numbers and outputs error messige if name contains numbers
            Console.Write("Address: ");
            address = Console.ReadLine();//collects dev 3 address
            Console.Write("Employee Type: ");
            employeeType = Console.ReadLine();//collects dev 3 1099 or w2
            employeeType = validateEmployeeType(employeeType);
            Console.Write("Gross Monthly Pay: ");
            try// collects pay data and verifys its a number
            {
                pay = double.Parse(Console.ReadLine());
            }
            catch
            {
                Console.WriteLine("Gross Monthly Pay must be a number. Please try again!");
                pay = double.Parse(Console.ReadLine());
            }// collects pay data and verifys its a number
            SoftwareDeveloper emp3 = new SoftwareDeveloper(name, address, employeeType, pay);//stores developer 3

            using (StreamWriter writer = new StreamWriter ("E:\\Users\\jason\\source\\repos\\Week4redo.csv", true))
            {
               
                // Use string interpolation syntax to make code clearer.
                writer.WriteLine($" { name} {","} {address} {","} {employeeType} {","} {pay}{","} .");
               
            }
           
            string text = System.IO.File.ReadAllText("E:\\Users\\jason\\source\\repos\\Week4redo.csv");

            System.Console.WriteLine("Contents of WriteText.csv");
            System.Console.WriteLine("Name,  Address, Employee type,  Gross pay");
            System.Console.WriteLine("");
            System.Console.WriteLine("{0}", text);


            string[] lines = System.IO.File.ReadAllLines("E:\\Users\\jason\\source\\repos\\Week4redo.csv");
            






            Console.WriteLine(" ");// provides space between collected data and displayed data
            Console.WriteLine(" ");// provides space between collected data and displayed data
            Console.WriteLine("Press enter to close this program");// 
            Console.ReadLine();// Requires user to press enter to close console
        }
        
        private static string validateEmployeeType(string employeeType) // Checks for errors in 1099 and W2 information
        {
            while (!(employeeType.Equals("W2") || employeeType.Equals("1099"))) // makes sure the answer is one of these to types
            {
                Console.WriteLine("Valid types are 1099 and W2, Please Try Again!");// props the user of the error
                employeeType = Console.ReadLine();
            }
            return employeeType;
        }
           

    }
}
