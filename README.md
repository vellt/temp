```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp53
{
    enum Muvelet { Osszeadas, Szorzas, Osztas, Kivonas}
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(ZsebSzamologep(5,10,'/'));
            Console.WriteLine(ZsebSzamologep(5,10,Muvelet.Osszeadas));
            Console.ReadKey();
        }

        static double ZsebSzamologep(int a, int b, Muvelet muvelet)
        {
            double osszeg = 0;
            switch (muvelet)
            {
                case Muvelet.Osszeadas: osszeg = a + b; break;
                case Muvelet.Kivonas: osszeg = a - b; break;
                case Muvelet.Szorzas: osszeg = a * b; break;
                case Muvelet.Osztas: osszeg = a / (double)b; break;
            }
            return osszeg;
        }

        static double ZsebSzamologep(int a, int b, char muvelet)
        {
            double osszeg = 0;
            switch (muvelet)
            {
                case '+': osszeg = a + b; break;
                case '-': osszeg = a - b; break;
                case '*': osszeg = a * b; break;
                case '/': osszeg = a / (double)b; break;
            }
            return osszeg;
        }
    }
}
```