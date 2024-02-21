```c#
static void Main(string[] args)
{
	matrixIsm();
	feladat1();
	feladat2();
	Console.ReadKey();
}

private static void feladat2()
{
	string[] gyumolcsok = new string[] 
	{ 
		"alma", 
		"korte", 
		"banan", 
		"narancs", 
		"szilva", 
		"Mandarin" 
	};

	// Mennyi legalább 5 karakteres szó van benne
	int szamlalo = 0;
	for (int i = 0; i < gyumolcsok.Length; i++) if (gyumolcsok[i].Length >= 5) szamlalo++;
	Console.WriteLine(szamlalo);

	// van-e benne páros karakterhosszú szó
	bool vanE = false;
	for (int i = 0; vanE==false && i < gyumolcsok.Length; i++) 
	{
		if (gyumolcsok[i].Length % 2 == 0) vanE = true;
	}
	Console.WriteLine((vanE?"van":"nincs")+ "benne páros karakterhosszú szó");

	// van-e olyan szó amely nagybetűvel kezdődik
	bool vanE2 = false;
	for (int i = 0; vanE2 == false && i < gyumolcsok.Length; i++)
	{
		if (gyumolcsok[i][0] >='A' && gyumolcsok[i][0]<='Z') vanE2 = true;
	}
	Console.WriteLine((vanE2 ? "van" : "nincs") + "benne olyan szó amely nagybetűvel kezdődik");

	// van-e olyan szó amely tartalmaz 'd'-t
	bool vanE3 = false;
	for (int i = 0; vanE3==false && i < gyumolcsok.Length; i++)
	{
		string gyumolcs = gyumolcsok[i];
		for (int j = 0; vanE3==false && j < gyumolcs.Length; j++)
		{
			if (gyumolcs[j] == 'd') vanE3 = true;
		}
	}
	Console.WriteLine((vanE3?"van":"nincs")+ " olyan szó amely tartalmaz 'd'-t");

	// melyik a legtöbb magánhangzót tartalmazó szó
	int maxIndex = 0;
	for (int i = 0; i < gyumolcsok.Length; i++)
	{
		if (mennyiMaganhangzo(gyumolcsok[i]) > mennyiMaganhangzo(gyumolcsok[maxIndex]))
		{
			maxIndex = i;
		}
	}
	Console.WriteLine(gyumolcsok[maxIndex]);
	// van-e szilva a tömbben.
	bool vanE4 = false;
	for (int i = 0; vanE4==false && i < gyumolcsok.Length; i++)
	{
		if (gyumolcsok[i] == "szilva") vanE4 = true;
	}
	Console.WriteLine((vanE4 ? "van" : "nincs") + " benne szilva");
}

private static int mennyiMaganhangzo(string gyumolcs)
{
	int szamlalo = 0;
	for (int j = 0; j < gyumolcs.Length; j++)
	{
		if (
			gyumolcs[j] == 'a' ||
			gyumolcs[j] == 'e' ||
			gyumolcs[j] == 'i' ||
			gyumolcs[j] == 'u' ||
			gyumolcs[j] == 'o'
		  ) szamlalo++;
	}
	return szamlalo;
}

private static void feladat1()
{
	string szoveg = "CASIC nevu kinai ceg megdonti a vasutipar rekordjait. " +
		"Keszul az 1000km/h-s vonat.";
	// mennyi db betű van benne (kisbetű/nagybetű)
	// mennyi db magánhangzó van benne
	// mennyi db mondatrészből áll
	// mennyi db szóból áll
	// hány %-a szám a teljes szövegnek, 2 tizedesre kerekítés
	// VAN-e benne kisbetű
	// VAN-e benne /-jel
	// írassa ki a szöveget kisbetűsen!
	// -------------------------------------------------------------------------
	// mennyi db betű van benne (kisbetű/nagybetű)
	int betuDarab = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if ((szoveg[i] >= 'A' && szoveg[i] <= 'Z') 
			|| (szoveg[i] >= 'a' && szoveg[i] <= 'z')) betuDarab++;
	}
	Console.WriteLine(betuDarab);
	// mennyi db magánhangzó van benne
	int maganhangzoDb = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if(
		   szoveg[i]=='a' || szoveg[i]=='e' || szoveg[i]=='i' || szoveg[i]=='o' || szoveg[i] == 'u'
			||
		   szoveg[i] == 'A' || szoveg[i] == 'E' || szoveg[i] == 'I' || szoveg[i] == 'O' || szoveg[i] == 'U'
		)
		{
			maganhangzoDb++;
		}
	}

	// mennyi db mondatrészből áll
	//for (int i = 0, darab = 0; i < szoveg.Length; i++) if (szoveg[i] == ' ') Console.WriteLine((i ==szoveg.Length-1?(++darab).ToString():(++darab).ToString())); 
	int pontszamlalo = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] == '.') pontszamlalo++;
	}
	Console.WriteLine(pontszamlalo);

	// mennyi db szóból áll
	int szokozSzamlalo = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] == ' ') szokozSzamlalo++;
	}
	Console.WriteLine(++szokozSzamlalo);

	// hány %-a szám a teljes szövegnek, 2 tizedesre kerekítés
	int szamSzamlalo = 0;
	int osszKarakter = szoveg.Length;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] >= '0' && szoveg[i] <= '9') szamSzamlalo++;
	}
	Console.WriteLine(Math.Round((double)szamSzamlalo/osszKarakter,2));

	// VAN-e benne kisbetű
	bool vanE = false;
	for (int i = 0; vanE ==false && i<szoveg.Length; i++) 
		if (szoveg[i] >= 'a' && szoveg[i] <= 'z') vanE = true;
	Console.WriteLine((vanE ? "van" : "nincs") + " benne kisbetű");

	// VAN - e benne / -jel
	bool vanE2 = false;
	for (int i = 0; vanE2 == false && i < szoveg.Length; i++) if (szoveg[i] == '/') vanE2 = true;
	Console.WriteLine((vanE2 ? "van" : "nincs") + " benne / jel");

	// írassa ki a szöveget kisbetűsen!
	for (int i = 0; i < szoveg.Length; i++)
	{
		Console.Write((szoveg[i] >= 'A' && szoveg[i] <= 'Z')? (char)(szoveg[i] + 32): szoveg[i]);
	}
}


private static void matrixIsm()
{
	int[,] matrix = new int[3, 4];
	// feltöltés random számokkal
	Random r = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++) //3
	{
		for (int j = 0; j < matrix.GetLength(1); j++) // 4
		{
			matrix[i, j] = r.Next(10); // [0,9]
		}
	}
	// kiíratás
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			Console.Write($"{matrix[i, j]} "); // i. sor j. elme
		}
		Console.WriteLine();
	}
}
```