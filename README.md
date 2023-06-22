# oops
### EXP 01:
```
using System;

namespace ConsoleApp16
{
    class Program
    {
        static void Main(string[] args)
        {
            int phy, math, chem, total1, total2;
            string name;
            Console.WriteLine("Enter the student name : ");
            name = Console.ReadLine();
            Console.WriteLine("Enter the physics marks : ");
            phy = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Enter the chemistry mark : ");
            chem = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Enter the Math marks : ");
            math = Convert.ToInt32(Console.ReadLine());
            total1 = math + phy + chem;
            total2 = math + phy;
            if(math>=65 && phy>=55 && chem >= 50)
            {
                if(total1>=180 && total2 >= 140)
                {
                    Console.WriteLine(name + "is eligible for engineering admission");
                }
            }
            else
            {
                Console.WriteLine(name + "is not eligible for engineering admission");
            }
        }
    }
}
```

### EXP 02 :
```
using System;
class HelloWorld
{
    static void Main()
    {
        string num1, rem, rev = "";
        Console.Write("Enter a string : ");
        num1 = Console.ReadLine();
        rem = num1;
        for (int s = num1.Length - 1; s >= 0; s--)
        {
            rev += num1[s];
        }
        Console.WriteLine(rev);
        if (rev == rem)
            Console.WriteLine(rem + " is a palindrome");
        else
            Console.WriteLine(rem + " is not a palindrome");

    }
}
```

### EXP 03 :
```
using System;

namespace condition
{
    public class pascal
    {
        public static void Main(string[] args)
        {
            Console.WriteLine("Pascal's Triangle : ");
            int rows = 5, num = 1;
            for (int i = 0; i < rows; i++)
            {
                for (int k = 1; k < rows - i; k++)
                {
                    Console.Write(" ");
                }
                for (int j = 0; j <= i; j++)
                {
                    if (i == 0 || j == 0)
                    {
                        num = 1;
                    }
                    else
                    {
                        num = num * (i - j + 1) / j;
                    }
                    Console.Write(num + " ");


                }
                Console.WriteLine();
            }
        }
    }
}

```

### EXP 04 :
```
using System;
public class Employee
{
    public String designation;
    public String employee_name;
    public int exp;
    public int bs;
    public int insurance;
    double hra, ta, salary;

    public Employee(String employee_name, String designation, int exp, int bs, int i)
    {
        this.employee_name = employee_name;
        this.designation = designation;
        this.exp = exp;
        this.bs = bs;
        this.insurance = i;
    }
    public void sal()
    {
        hra = this.bs * 0.2;
        ta = this.bs * 0.1;
        salary = this.bs + hra + ta - this.insurance;

    }
    public void display()
    {

        Console.WriteLine("Name of the employee is {0} having {1} of experience,working as {2}", this.employee_name, this.exp, this.designation);
        Console.WriteLine("Receives {0} of salary.", salary);

    }

}
class TestEmployee
{
    public static void Main(string[] args)
    {
        Employee e1 = new Employee("Shobika", "Developer", 10, 30000, 1000);
        e1.sal();
        Employee e2 = new Employee("Sharmila", "HR", 5, 50000, 1000);
        e2.sal();
        e1.display();
        e2.display();

    }
}
```

### EXP 05 :
```
using System;
class CPUactivity
{
    public static void Main(String[] args)
    {
        int[][] cpu = new int[4][];
        cpu[0] = new int[3];
        cpu[1] = new int[5];
        cpu[2] = new int[6];
        cpu[3] = new int[4];
        for (int i = 0; i < 4; i++)
        {
            for (int j = 0; j < cpu[i].Length; j++)
            {
                cpu[i][j] = i * j + 70;
            }
        }
        for (int i = 0; i < cpu.Length; i++)
        {
            for (int j = 0; j < cpu[i].Length; j++)
            {
                Console.WriteLine("CPU usage at node" + i + " is " + cpu[i][j] + "%");
            }
            Console.WriteLine();
        }
    }
}
```

### EXP 06:
```
using System;
   class program
   {
       public program(int p1, int p2)
       {
           Console.WriteLine(p1 * p2);
       }
       public program(int p1)
       {
       Console.WriteLine(p1 * 1);
       }
       public static bool operator == (program p1, program p2)
       {
           return p1.Equals(p2);
       }
       public static bool operator != (program p1, program p2)
       {
           return !p1.Equals(p2);
       }

   }
   class Example
   {
       public static void Main()
       {
           program p1 = new program(10,20);
           program p2 = new program(10);
           p1 = p2;
           if(p1==p2)
           {
               Console.WriteLine("Objects are equal");
           }
           else
           {
               Console.WriteLine("Objects are not equal");
           }
       }
   }


```

### EXP 07:
```
using System;

public class reverse
{
    static int RevNum(int n, int rev = 0)
    {
        if (n == 0)
        {
            return rev;
        }
        int digit = n % 10;
        rev = rev * 10 + digit;
        return RevNum(n / 10, rev);
    }

    static void Main(string[] args)
    {
        Console.Write("Enter a number: ");
        int number = Convert.ToInt32(Console.ReadLine());
        Console.WriteLine("Reversed number: " + RevNum(number));
    }
}
```

### EXP 08:
```
using System;

namespace ex_8
{
    class tyre
    {
        public tyre()
        {
            Console.WriteLine("Tyre Constructor");
        }
        public virtual void display()
        {
            Console.WriteLine("Methods in Tyre class");
        }
    }
    class scooter : tyre
    {


        public scooter()
        {
            Console.WriteLine("scooter Constructor");
        }
        public override void display()
        {
            base.display();
        }
    }
    class car : tyre
    {

        public car()
        {
            Console.WriteLine("Car Constructor");
        }
        public override void display()
        {
            base.display();
        }
    }
    class program
    {
         static void Main(string[]args)
        {
            scooter s= new scooter();
            s.display();
            car c = new car();
            c.display();

        }
    }
}
```

### EXP 09:
```
using System;
using System.Reflection.Metadata.Ecma335;

namespace abhi
{

    public interface bank
    {
        public int deposit(int amount);
        public int withd(int amount);


    }
    public class Program : bank
    {
        public int amount, amt = 30000;
        public int deposit(int amount)
        {
            this.amount = amount;
            return amt + amount;

        }
        public int withd(int amount)
        {
            this.amount = amount;
            return amt - amount;

        }
        public static void Main(string[] args)
        {


            Program b = new Program();
            Console.WriteLine("Enter the option \n 1. WITHDRAWL \n 2. DEPOSIT");
            int a = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("\nAccount Balance : " + b.amt);
            if (a == 1)
            {
                Console.WriteLine("Enter the amount to be withdrawled:");
                b.amount = Convert.ToInt32(Console.ReadLine());
                int c = b.withd(b.amount);
                Console.WriteLine("Bank Balance : " + c);

            }
            if (a == 2)
            {
                Console.WriteLine("Enter the amount to be deposited:");
                b.amount = Convert.ToInt32(Console.ReadLine());
                int d = b.deposit(b.amount);
                Console.WriteLine("Bank Balance : " + d);

            }

        }
    }
}
```

### EXP 10:
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.IO;
struct student
{
    public string name;
    public int age;
    public string dept;
    public float sem_percent;
};
public class program
{
    static void write(string name, int age, string dept, float percent, int i)
    {
        FileStream fs = new FileStream("file.txt", FileMode.Append, FileAccess.Write);
        StreamWriter sw = new StreamWriter(fs);
        sw.WriteLine("name of the student-{0}:{1}", i + 1, name);
        sw.WriteLine("age of the student-{0}:{1}", i + 1, age);
        sw.WriteLine("dept of the student-{0}:{1}", i + 1, dept);
        sw.WriteLine("semester percentage of the student-{0}:{1}", i + 1, percent);
        sw.WriteLine();
        sw.Close();
        fs.Close();
    }
    public static void Main(string[] args)
    {
        FileStream fs = new FileStream("file.txt", FileMode.Create, FileAccess.Write);
        fs.Close();
        Console.Write("Enter num of students:");
        int n = Convert.ToInt32(Console.ReadLine());
        student[] s = new student[n];
        for (int i = 0; i < n; i++)
        {
            Console.Write("Enter the name of the student {0}:", i + 1);
            s[i].name = Console.ReadLine();
            Console.Write("Enter the age of the student {0}:", i + 1);
            s[i].age = Convert.ToInt32(Console.ReadLine());
            Console.Write("Enter the dept of the student {0}:", i + 1);
            s[i].dept = Console.ReadLine();
            Console.Write("Enter the semester percentage of the student {0}:", i + 1);
            s[i].sem_percent = float.Parse(Console.ReadLine());
            write(s[i].name, s[i].age, s[i].dept, s[i].sem_percent, i);
            Console.WriteLine();
        }
        Console.ReadKey();
    }
}
```
