```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace doga_gyakorlas
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.Write("Add meg mennyiszer menjen a busz: ");
            int N = Convert.ToInt32(Console.ReadLine());
            if (N < 2)
            {
                Console.WriteLine("minimum 2x indulnia kell a busznak");
            }
            else
            {
                int[] buszjarat = new int[N];
                Random r = new Random();
                for (int i = 0; i < buszjarat.Length; i++)
                {
                    buszjarat[i] = r.Next(61) + 10;
                }

                // a)
                int elso = buszjarat[0];
                int utolso = buszjarat[buszjarat.Length - 1];
                //int utolso = buszjarat[N-1];
                if (elso == utolso) Console.WriteLine("ugyanannyi");
                else Console.WriteLine("eltérő");
                // vagy
                Console.WriteLine((elso == utolso) ? "ugyanannyi" : "eltérő");


                // b)
                int sum = 0;
                for (int i = 0; i < buszjarat.Length; i++)
                {
                    sum += buszjarat[i];
                    //sum =sum+ buszjarat[i];
                }
                double atlag = sum / (double)buszjarat.Length;
                Console.WriteLine(Math.Round(atlag));

                // c)
                bool tendencia = true;
                for (int i = 1; tendencia==true && i < buszjarat.Length; i++)
                {
                    if(buszjarat[i]  > buszjarat[i - 1])
                    {
                        tendencia = false;
                    }
                }
                Console.WriteLine("folyamatosan"+(tendencia ? " csökken":" nő"));

                // d)
                bool van = false;
                for (int i = 0;van==false &&  i < buszjarat.Length; i++)
                {
                    if (buszjarat[i] < atlag)
                    {
                        van = true;
                    }
                }
                Console.WriteLine(van ? "van" : "nincs");

                // e)
                int db = 0;
                for (int i = 0; i < buszjarat.Length; i++)
                {
                    if (buszjarat[i] == 10) db++;
                }
                Console.WriteLine(db);
            }
        }
    }
}

```