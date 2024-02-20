```c#
static void Main(string[] args)
{
	int[] tomb = new int[] { 3, 2, 10, 4 };
	osszegzes(tomb);
	megszamlalas(tomb);
	eldontes(tomb);
	matrixIsmetles();
	// feladat
	feladat1();
	feladat2();
	Console.ReadKey();
}

private static void feladat2()
{
	string szoveg = "CASIC nevu kinai ceg megdonti a vasutipar rekordjait. Keszul az 1000km/h-s vonat.";
	// mennyi db betű van benne (kisbetű/nagybetű)
	// mennyi db magánhangzó van benne
	// mennyi db mondatrészből áll
	// mennyi db szóból áll
	// hány %-a szám a teljes szövegnek
	// VAN-e benne kisbetű
	// VAN-e benne /-jel
	// írassa ki a szöveget kisbetűsen!
	int betuDarab = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if ((szoveg[i] >= 'A' && szoveg[i] <= 'Z') || (szoveg[i] >= 'a' && szoveg[i] <= 'z')) betuDarab++;
	}
	Console.WriteLine(betuDarab);
}

/// <summary>
/// iskolai csoportverseny volt. 2 10 fős csoport van. 
/// töltse fel [1,10]-ban az elemeket. és válaszoljon az alábbi kérdésekre
/// ------------------------------------------
/// melyik csoport szerzett több pontot (összegzés tétele)
/// mennyi tanuló szerzett az 1. csoportból 1 pontot (megszámlálás)
/// volt-e a kettes csoportban olyan aki 10 pontot szerzett (eldöntés)
/// </summary>
private static void feladat1()
{
	int[,] csapatok = new int[2, 10];
	Random r = new Random();
	for (int i = 0; i < csapatok.GetLength(0); i++)
	{
		for (int j = 0; j < csapatok.GetLength(1); j++) csapatok[i, j] = r.Next(10) + 1;
	}
	// elso
	int elsoCsopOsszeg = 0;
	int masodikCsopOsszeg = 0;
	for (int i = 0; i < csapatok.GetLength(0); i++)
	{
		for (int j = 0; j < csapatok.GetLength(1); j++)
		{
			if (i == 0) elsoCsopOsszeg += csapatok[i, j];
			else masodikCsopOsszeg += csapatok[i, j];
		}
	}
	Console.WriteLine((masodikCsopOsszeg > elsoCsopOsszeg) ? "2. nyert" : (elsoCsopOsszeg > masodikCsopOsszeg) ? "1. nyert" : "döntetlen");

	// masodik
	int szamlalo = 0;
	for (int i = 0; i < csapatok.GetLength(1); i++) if (csapatok[0, i] == 1) szamlalo++;

	// harmadik
	bool vanE = false;
	for (int i = 0; vanE == false && i < csapatok.GetLength(1); i++) if (csapatok[1, i] == 10) vanE = true;
	Console.WriteLine(vanE ? "van" : "nincs");
}

private static void matrixIsmetles()
{
	int[,] matrix = new int[3, 5];
	Random r = new Random();
	// feltölteni
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			matrix[i, j] = r.Next(10); //[0,9]
		}
	}
	// kiíratás
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			Console.Write($"{matrix[i, j]} "); // egy sor elemeit egymás mellé helyezi
		}
		Console.WriteLine(); // amikor egy sort kiíratott, akkor sort tör
	}
}

private static void eldontes(int[] tomb)
{
	bool vanE = false;
	int i = 0;
	while (vanE==false && i<tomb.Length)
	{
		if (tomb[i] == 2)
		{
			vanE = true;
		}
		i++;
	}
	//  for (int i = 0; vanE==false && i<tomb.Length; i++) if (tomb[i] == 2) vanE = true;
	Console.WriteLine(vanE?"van":"nincs");
}

private static void megszamlalas(int[] tomb)
{
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 2 == 0)
		{
			szamlalo++;
		}
	}
	Console.WriteLine(szamlalo);
}

private static void osszegzes(int[] tomb)
{
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
	}
	Console.WriteLine(osszeg);
}
```