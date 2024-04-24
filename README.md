```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace csop2
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(Koszones()); // Szia, Otto!
            Console.WriteLine(Koszones("Béla")); // Szia, Béla!

            Console.WriteLine(Legnagyobb(1,2,3)); // 3
            Console.WriteLine(Legnagyobb(new int[] { 1, 20, 10 })); // 20
            Console.WriteLine(Legnagyobb(new List<int>() { 1, 2, 10 })); // 10
            Console.WriteLine((char)Legnagyobb("alma")); // m

            Console.ReadKey();
        }

        static int Legnagyobb(List<int> lista)
        {
            int max = lista[0];
            for (int i = 1; i < lista.Count(); i++)
            {
                if (max < lista[i]) max = lista[i];
            }
            return max;
        }

        static int Legnagyobb(int[] tomb)
        {
            int max = tomb[0];
            for (int i = 1; i < tomb.Length; i++)
            {
                if (max < tomb[i]) max = tomb[i];
            }
            return max;
        }

        static int Legnagyobb(string szoveg)
        {
            int max = szoveg[0];
            for (int i = 1; i < szoveg.Length; i++)
            {
                if (szoveg[i] > max) max = szoveg[i];
            }
            return max;
        }

        static int Legnagyobb(int sz1, int sz2, int sz3)
        {
            int max = sz1;
            if (sz2 > max) max = sz2;
            if (sz3 > max) max = sz3;
            return max;
        }

        static string Koszones()
        {
            return "Szia, Otto!";
        }

        static string Koszones(string nev)
        {
            return $"Szia, {nev}!";
        }

        
    }
}

```