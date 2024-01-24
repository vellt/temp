```c#
static void Main(string[] args)
{
	// string gyakorlás
	feladat1();
	// üzenet tikosítás és visszafejtés
	feladat2();
	// mátrixok
	feladat3();
	// vektorok
	feladat4();
	// közös elemek
	feladat5();
	// kisebb vektor gyak fel
	feladat6();
	Console.ReadKey();
}

private static void feladat6()
{
	// tölsön fel egy int típusú tömböt/vektort random számokkal,
	// annyi elemmelű legyen a tömb, amennyit a konzolban megadok
	Random r = new Random();
	int[] elemek = new int[Convert.ToInt32(Console.ReadLine())];
	for (int i = 0; i < elemek.Length; i++)
	{
		elemek[i] = r.Next(100) + 1;
	}
}

private static void feladat5()
{
	string sz1 = "kerítés";
	string sz2 = "egér";
	// írassuk ki a közös elemeket (karaktereket)
	// és hogy hány db közös elem volt?

	// A közös elemeket egy különálló tömbben tárolja le,
	// a kérdésekre a választ ebből a dedikált tömbböl nyerje ki

	// ebbe gyűjtjük a közös elemeket ami a e,é,r lesz nagy valószínűséggel
	char[] egyezoElemek = new char[sz2.Length]; // 4 karakter

	// körbejárjuk a 'kerítés' minden elemét (karaktert)
	for (int i = 0; i < sz1.Length; i++)
	{
		// körbe járjuk az 'egér' elemét
		for (int j = 0; j < sz2.Length; j++)
		{
			// mindig összevetjük a kerítés adott karakterét az összes sz2 változó karakterével,
			// pl a 'k'-t, ha van találat akkor pl a 'k'-t bele helyezzük
			// a gyűjtő tömbbe, ahol a közös elemek lesznek
			if (sz1[i] == sz2[j])
			{
				// egyezőElemekhez hozzáadni, mert van találat
				//egyezoElemek;

				// megkeressük, hogy milyen indexre helyezhetünk
				// értéket a gyűjtő tömbben, hogy hol nincs még érték
				int nullakSzama = 0;
				for (int k = 0; k < egyezoElemek.Length; k++)
				{
					if (egyezoElemek[k] == 0)
					{
						nullakSzama++;
					}
				}
				int index = egyezoElemek.Length - nullakSzama;

				// bele helyezzük a közös elemet
				if (index != egyezoElemek.Length)
				{
					egyezoElemek[index] = sz1[i];
				}
			}
		}
	}
	// kilistázom a közös elemeket
	for (int i = 0; i < egyezoElemek.Length; i++)
	{
		Console.WriteLine($"{egyezoElemek[i]} ---> {(int)egyezoElemek[i]}");
	}
	// megnézem hány db közös elem van, ahol 0 érték van ott nincs karakter(közös elem)
	int nemNulla = 0;
	for (int k = 0; k < egyezoElemek.Length; k++)
	{
		if (egyezoElemek[k] != 0)
		{
			nemNulla++;
		}
	}
	Console.WriteLine($"{nemNulla} db közös karakter van a {sz1} és az {sz2}-ben");
}

private static void feladat2()
{
	string eredetiUzenet = "ALMA LEESETT A FÁROL DE NEM TÖRT EL";
	string titkositottUzenet = titkositas(eredetiUzenet, 25);
	string visszafejtettUznet = visszafejtes(titkositottUzenet, 25);
	Console.WriteLine(eredetiUzenet);
	Console.WriteLine(titkositottUzenet);
	Console.WriteLine(visszafejtettUznet);
}

private static void feladat4()
{
	// 1 dimenziós tömbök, vektorok 
	
	// töltsünk fel egy szekrény string típusú 5 elemű tömböt/vektort
	// az adatokat konzolról kérjük be
	string[] szekreny = new string[5];
	for (int i = 0; i < szekreny.Length; i++)
	{
		Console.Write("Add meg mit helyezzek a szekrenybe: ");
		szekreny[i] = Console.ReadLine();
	}

	// listázzuk a szekrény tartalmát
	Console.WriteLine("A szekreny tartalma:");
	for (int i = 0; i < szekreny.Length; i++)
	{
		Console.WriteLine(szekreny[i]);
	}

	//---------------------------------------------

	// töltsünk fel egy 20 elemű int tömböt/veltort
	// [1,100]-béli random számokkal
	Random random = new Random();
	int[] vektor = new int[20];
	for (int i = 0; i < vektor.Length; i++)
	{
		vektor[i] = random.Next(100) + 1; //[1,100]
	}
	
	// írassuk ki az értékeket
	for (int i = 0; i < vektor.Length; i++)
	{
		Console.WriteLine(vektor[i]);
	}
}

private static void feladat3()
{
	// matrix--> 2 dim tömb
	// - van szélessége, magassága
	// - táblázatként lehet értelmezni

	// kezdeti értékkel létrehozott mátrix, ilyenkor nem kell megadni
	// kötelezően, hogy mennyi a szélessége és magassága
	int[,] matrix = new int[,]
	{
		{ 421, 45, 54, 6},
		{ 23, 55, 40, 8},
		{ 66, 88, 21, 9}
	};

	// 66-ot azonosítása:
	Console.WriteLine(matrix[2, 0]);
	// 54-es érték azonosítása
	Console.WriteLine(matrix[0, 2]);

	// ahhoz, hogy a mátrix elemeit körbejárjuk, kettő forciklust kell egymásba ágyazni
	// a külsp a sorokat kezeli a belső az adott sor elemeit hivatkozza le
	// GetLength(0)-->a sorokat hivatkozzuk le
	// GetLength(1)-->az oszlopokat hivatkozzuk le
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			Console.WriteLine(matrix[i, j]); // sor, oszlop
		}
	}
	
	// mátrix feltöltése
	Random random = new Random();
	// nincs kezdeti értékek kapcsos zárójel által megadva, ergó-->
	// nekünk kell megadni egyből a sorok számát (3), és az oszlopok számát(5)
	int[,] matrix2 = new int[3, 5];
	for (int i = 0; i < matrix2.GetLength(0); i++)
	{
		for (int j = 0; j < matrix2.GetLength(1); j++)
		{
			matrix2[i, j] = random.Next(100) + 1; //[1,100] random
		}
	}

	// mátrix elemeinek kiíratása
	for (int i = 0; i < matrix2.GetLength(0); i++)
	{
		for (int j = 0; j < matrix2.GetLength(1); j++)
		{
			Console.WriteLine(matrix2[i, j]);
		}
	}
}

private static string visszafejtes(string titkositottUzenet, int eltolas)
{
	string visszafejtettUzenet = "";
	for (int i = 0; i < titkositottUzenet.Length; i++)
	{
		visszafejtettUzenet += (char)(titkositottUzenet[i] + eltolas);
	}
	return visszafejtettUzenet;
}

private static string titkositas(string eredetiUzenet, int eltolas)
{
	string titkositottUzenet = "";

	for (int i = 0; i < eredetiUzenet.Length; i++)
	{
		titkositottUzenet+= (char)(eredetiUzenet[i] - eltolas);
	}

	return titkositottUzenet;
}

private static void feladat1()
{
	// írassuk ki a második szót
	string mondat = "Géza kék az ég";
	int szokozSzamlalo = 0;
	for (int i = 0; i < mondat.Length; i++)
	{
		if (mondat[i] == ' ')
		{
			szokozSzamlalo++;
		}
		if (szokozSzamlalo > 0 && szokozSzamlalo < 2 && mondat[i] != ' ')
		{
			Console.Write(mondat[i]);
		}
	}
	Console.WriteLine();
}
```
