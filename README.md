```c#
// irjunk egy programot ami kikalkulálja hogy mennyi a százalék alapján az érdemjegy
while (true)
{
	Console.WriteLine("Add meg a százalékot és megmondom az érdemjegyet");
	int szazalek = Convert.ToInt32(Console.ReadLine());
	int erdemjegy = 1;
	if (szazalek >= 86) erdemjegy = 5;
	else if (szazalek >= 71) erdemjegy = 4;
	else if (szazalek >= 56) erdemjegy = 3;
	else if (szazalek >= 40) erdemjegy = 2;
	else erdemjegy = 1;

	switch (erdemjegy)
	{
		case 5: Console.WriteLine("jeles (5)"); break;
		case 4: Console.WriteLine("jó (4)"); break;
		case 3: Console.WriteLine("közepes (3)"); break;
		case 2: Console.WriteLine("elégséges (2)"); break;
		case 1: Console.WriteLine("elégtelen (1)"); break;
	}
}

//-Dolgozat feladatok átnézése---------------------------------------------------------------------------

// 1 feladat
Console.WriteLine("Add meg az z értékét");
int z = Convert.ToInt32(Console.ReadLine());
Console.WriteLine((z >= 0) ? "pozitív" : "negatív");

// 2. feladat
Console.WriteLine("Add meg az első számot");
int szam1 = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("Add meg a második számot");
int szam2 = Convert.ToInt32(Console.ReadLine());

double osztas = (szam1 < szam2) ? szam1 / (double)szam2 : szam2 / (double)szam1;
Console.WriteLine($"kissebbet a nagyobbal: {Math.Round(osztas, 3)}");

// 3. feladat
Console.WriteLine("add meg egy számot, és megmondom a 9. gyökét");
int szam = Convert.ToInt32(Console.ReadLine());
Console.WriteLine($"A(z) {szam} szám 9. gyöke: {Math.Pow(szam, 1.0 / 9.0):0.0000}");

// 4. feladat
Console.WriteLine("Add meg a trapéz \"a\" oldalának a hosszát");
double a = Convert.ToDouble(Console.ReadLine());

Console.WriteLine("Add meg a trapéz \"b\" oldalának a hosszát");
double b = Convert.ToDouble(Console.ReadLine());

Console.WriteLine("Add meg a trapéz \"c\" oldalának a hosszát");
double c = Convert.ToDouble(Console.ReadLine());

Console.WriteLine("Add meg a trapéz \"d\" oldalának a hosszát");
double d = Convert.ToDouble(Console.ReadLine());

Console.WriteLine("Add meg a trapéz \"a\" oldalához tartozó magasságot");
double m = Convert.ToDouble(Console.ReadLine());

double t = ((a + c) * m) / 2;
double k = a + b + c + d;

Console.WriteLine($"A trapéz területe: {t:0.00}");
Console.WriteLine($"A trapéz kerülete: {k:0.00}");

//--ismétlés------------------------------------------------------------

/*
 *Kérjen be egy telefonszámot
   pl 30XXXXXXX
   és csak akkor fogadja el, ha valóban mobilszám!
   Írja ki hogy melyik szolgáltatóhoz tartozik
	"if else" - el, majd switch-el

	pl: Add meg a telefonszámod(06 utánit):
 */

Console.WriteLine("Add meg a telefonszámod a 06 utáni részt ");
string teloszam = Console.ReadLine();
if (teloszam.Length==9)
{
	// valid
	if (teloszam[0] == '7') Console.WriteLine("Ez a szám vodafonos");
	else if (teloszam[0] == '3') Console.WriteLine("Ez a szám telekomos");
	else if (teloszam[0] == '2') Console.WriteLine("Ez a szám yetteles");
	else if (teloszam[0] == '5') Console.WriteLine("Ez a szám digis");
	
}
else  Console.WriteLine("kamu -_-");

switch (teloszam.Length) {
	case 9:
		// valid
		switch (teloszam[0])
		{
			case '2': Console.WriteLine("yettel"); break;
			case '3': Console.WriteLine("telekom"); break;
			case '7': Console.WriteLine("vodafon"); break;
			case '5': Console.WriteLine("digi"); break;
		}
		break;
	default: Console.WriteLine("kamu -_-"); break;
}
```
