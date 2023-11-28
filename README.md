```c#
/*
a gép generáljon random számot [1,100]
majd kérjen be a felhasználótól egy számot (tipp)
és mondja meg, hogy a gép által gondolt szám a tipptől nagyobb vagy 
kisebb! A tippelés addig megy, amíg a felh. el nem találja
a gép számát
 */

// plusz feladat: számoljuk meg hány
// lépéssel tudta kitalálni a gép átla generált számot

Random random = new Random();
int gep = random.Next(100)+1;
int felh = 0;
int szamlalo = 0;
while (gep!=felh)
{
	felh = Convert.ToInt32(Console.ReadLine());
	szamlalo++;
	if (felh < gep)
	{
		Console.WriteLine("nagyobb számra gondoltam");
	}else if(felh > gep)
	{
		Console.WriteLine("kisebb számra gondoltam");
	}
}
Console.WriteLine($"eltaláltad, ennyi lépés számmal sikerült: {szamlalo}");

// for ciklus-->előírt lépésszámú ciklus
/*
for (int i = 0; i < length; i++)
{

}*/

// 5 random számot generáljunk-->[0,50] for cikussal
for (int i = 1; i <= 5; i++)
{
	int szam = random.Next(51);
	Console.Write($"{szam} ");
}

// 40 random szám [-100,100]
// írjuk ki egymás mellé szóközökkel elválasztva a számokat
// minden 8.-nál törjön sort
for (int i = 1; i <= 40; i++)
{
	int szam = random.Next(201)-100;
	Console.Write($"{szam} ");
	if (i % 8 == 0) Console.WriteLine();
}

// OKTATÓPROGRAM
// összeadást kivonást gyakoroltatja
// 10 feladatot adjuk a felh-nak
// egész számokat álklítsunk elő véletlenszerűen [-5,15]
// minden páros ciklusváltozó az összeadást gyakoroltatja
// minden páratlan ciklusváltozó a kivonást gyakoroltatja
// minden egyes helyes megoldás 1 pontot ért, összesen 10 pont
// szerezhető
// 0-2 elégtelen
// 3-4 elégséges
// 5-6 közepes
// 7-8 jó
// 9-10 jeles
```
