```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace gyakorlas_2023_10_04
{
    class Program
    {
        static void Main(string[] args)
        {

            /*
             * Kérjen be egy telefonszámot
                pl 30XXXXXXX
                és csak akkor fogadja el, ha valóban mobilszám!
                Írja ki hogy melyik szolgáltatóhoz tartozik
                "if else"-el, majd switch-el

                pl: Add meg a telefonszámod (06 utánit):
             */

            Console.WriteLine("Add meg a telefonszámod (06 utánit):");
            string telefonszam = Console.ReadLine();
            // valid-e a telefonszám
            if (telefonszam.Length != 9) Console.WriteLine("Nem valid a megadott telefonszám");
            else
            {
                // megvizsgáljuk hogy milyen szolgáltatóhoz tartozik a telefonszám
                if (telefonszam[0].ToString() == "3") Console.WriteLine("Telekomos");
                else if (Convert.ToInt32(telefonszam[0].ToString()) == 2) Console.WriteLine("Yettel");
                else if (telefonszam[0] == '7') Console.WriteLine("Vodafon");
                else Console.WriteLine("Nem ismerek ilyen szolgáltatót!");

                switch (telefonszam[0].ToString())
                {
                    case "3": Console.WriteLine("Telekomos"); break;
                    case "7": Console.WriteLine("Yetteles"); break;
                    case "5": Console.WriteLine("Digis"); break;
                    case "2": Console.WriteLine("Vodafonos"); break;
                    default: Console.WriteLine("Nem ismerem ezt a szolgáltatót"); break;
                }
            }

            // kérjen be egy számot a kozolról (1 vagy 0)
            // fej=1 vagy írást=0
            Console.WriteLine("Add meg az x értékét");
            int x = Convert.ToInt32(Console.ReadLine());

            if (x<1 && x>-1)// x==0
            {
                Console.WriteLine("írás");
            }
            else if(x<2 && x>0) // x==1
            {
                Console.WriteLine("fej");
            }
            
            //RANDOM------------------------------------------------

            Random rand1 = new Random();
            // [0,5]
            int random = rand1.Next(6);
            // [0,100]
            int random99 = rand1.Next(101);
            // [0,99]
            int random3 = rand1.Next(100);
            // [1,6]
            int random4 = rand1.Next(6)+1;
            // [-50,50]
            int random5 = rand1.Next(101)-50;
            // [-100, 100]
            int random6 = rand1.Next(201) - 100;
            // [-15,-5]
            int random7 = rand1.Next(11) - 15;

            // next nem csak 1 paraméteres változata van
            // hanem 2 paraméteres is
            //  [-100, 100]
            int random8 = rand1.Next(-100, 101);
            // [0,5]
            int random9 = rand1.Next(0, 6);
            // [-50,50]
            int random10 = rand1.Next(-50, 51);
            // [-15, -5]
            int random11 = rand1.Next(-15, -4);

            /*
             Készítsen számkitalálós programot! A gép vélezlenszerűen generáljon ki egy számot
             1 és 6 között! A felhasználótól kérjen be egy tippet, és mondja meg ha sikerült
             eltalálnia, ha nem mondja meg mire gondolt a gép
             */

            Random rand2 = new Random();
            int generaltSzam = rand2.Next(6) + 1; // r.Next(1,7);
            Console.WriteLine("Add meg a tippedet: ");
            int tipp = Convert.ToInt32(Console.ReadLine());

            if (generaltSzam == tipp) Console.WriteLine("Eltaláltad");
            else Console.WriteLine($"Nem találtad el. Amire én gondoltam az a {generaltSzam}");


            /*
             Állítsuk elő véletlenszerűen egy egész számot az [1,10]-ból, és írjuk ki, hogy 
                a szám páros-e vagy páratlan
            */ 

            Random rand3 = new Random();
            int r1 = rand3.Next(2,51);
            int r2 = rand3.Next(2,51);
            int r3 = rand3.Next(2,51);
            int r4= rand3.Next(2,51);
            int r5 = rand3.Next(2,51);

            Console.WriteLine($"Számok: {r1}, {r2}, {r3}, {r4}, {r5}");
            Console.WriteLine($"összegük: {r1+r2+r3+r4+r5}");
            Console.WriteLine($"Szorzat: {r1*r2*r3*r4*r5}");
            Console.WriteLine($"átlag: {(r1+r2+r3+r4+r5)/5.0}");

            /*
                2 random számot [-20,-2] készítsünk és 
                számoljuk ki az összegüket, kivonásukat, 
                szorzatukat, hányadosukat
             */

            Random rand4 = new Random();
            int random1 = rand4.Next(-20, -1);
            int random2 = rand4.Next(-20, -1);
            Console.WriteLine($"{random1} {random2}");
            Console.WriteLine($"összegük: {random1+random2}");
            Console.WriteLine($"kivonásuk: {random1-random2}");
            Console.WriteLine($"szorzatuk: {random1*random2}");
            Console.WriteLine($"szorzatuk: {random1 / Convert.ToDouble(random2)}");

            /*
             2 véletlen számot generáljunk [0,10] intervallumos tartományból, 
            és írjuk ki a számokat a képernyőre, majd azt, hogy melyik szám a nagyobb!
            Ha egyenlő, írjuk ki a  "A két szám egyenlő"
             */

            Random rand5 = new Random();
            int r_1 = rand5.Next(11);
            int r_2 = rand5.Next(11);
            Console.WriteLine($"r_1= {r_1}, r_2= {r_2}");
            // hármas operátorral is meglehet oldani
            Console.WriteLine((r_1==r_2)?"A két szám egyenlő":(r_1>r_2)?$"{r_1} a nagyobb":$"{r_2} a nagyobb");

            Console.ReadKey();
        }
    }
}

```
