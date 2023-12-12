```c#
 // OKTATÓPROGRAM
// összeadást kivonást szorzást osztást gyakoroltatja véletlenszerűen
// 5 feladatot adjuk a felh-nak
// egész számokat álklítsunk elő véletlenszerűen [1,9]
// minden egyes helyes megoldás 1 pontot ért, összesen 10 pont
// szerezhető
// 0-2 elégtelen
// 3-4 elégséges
// 5-6 közepes
// 7-8 jó
// 9-10 jeles
Random random = new Random();
int pontszam = 0;
int feladatokSzama = Convert.ToInt32(Console.ReadLine());
for (int i = 1; i <= feladatokSzama; i++)
{
	int szam1 = random.Next(9) + 1;
	int szam2 = random.Next(9) + 1;
	int op = random.Next(4);
	double valasz = 0;
	switch (op)
	{
		case 0:
			Console.Write($"{szam1} + {szam2} = ");
			valasz = Convert.ToDouble(Console.ReadLine());
			if (valasz == szam1 + szam2) pontszam++;
			break;
		case 1:
			Console.Write($"{szam1} - {szam2} = ");
			valasz = Convert.ToDouble(Console.ReadLine());
			if (valasz == szam1 - szam2) pontszam++;
			break;
		case 2:
			Console.Write($"{szam1} * {szam2} = ");
			valasz = Convert.ToDouble(Console.ReadLine());
			if (valasz == szam1 * szam2) pontszam++;
			break;
		case 3:
			Console.Write($"{szam1} / {szam2} = ");
			valasz = Convert.ToDouble(Console.ReadLine());
			if (valasz == (double)szam1 / szam2) pontszam++;
			break;
		default:
			Console.WriteLine("ez sose fut le");
			break;
	}
}
Console.WriteLine($"pontok: {pontszam}/{feladatokSzama}");
if (pontszam <= 2)
{
	Console.WriteLine("Elégtelen");
}
else if (pontszam <= 4)
{
	Console.WriteLine("Elégséges");
}
else if (pontszam <= 6)
{
	Console.WriteLine("Közepes");
}
else if (pontszam <= 8)
{
	Console.WriteLine("jó");
}
else
{
	Console.WriteLine("jeles");
}

// tizes szorzótábla

for (int i = 1; i <= 10; i++)
{
	Console.WriteLine($"{i}x10={i * 10}");
}

Console.ReadKey();
```
