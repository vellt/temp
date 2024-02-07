```c#
static void Main(string[] args)
{
	ismetles();
	// PROGRAMOZÁSI TÉTELEK
	// gyakran használt algoritmusok a programozásban

	osszegzesTetele();
	osszegzesTeteleFeladat();

	megszamlalasTetele();
	megszamlalasTeteleFeladat();

	eldontesTetele();
	eldontesTeteleFeladat1();

	// komplex, amely érinti az előző tételeket
	komplex();

	Console.ReadKey();
}

/// <summary>
/// iskolai verseny. 2 10 főscsoport van. minden tanuló [0,10] közötti
/// pontot szerzett. Írassa ki külön-külön sorba a csoportok eredményeit
/// - mennyi tanuló szerzett az első csoportból 0 pontot [megszámlálás tétele]
/// - volt-e a második csoportban 10 pontot szerző tanuló [eldöntés tétele]
/// - melyik csoport mennyi pontot szerzett összesen [összegzés tétele]
/// </summary>
private static void komplex()
{
	// órai feladat volt, következő órán ezzel kezdünk
}

/// <summary>
/// kérjünk be a konzolról egy string-et majd döntsük el
/// hogy van-e benne s-betű
/// </summary>
private static void eldontesTeteleFeladat1()
{
	string szov = Console.ReadLine();
	bool vanBenne = false;
	int i = 0;
	while (vanBenne==false && i<szov.Length)
	{
		if (szov[i] == 's') vanBenne = true;
		i++;
	}

	// eldöntés tétele 1 sorosan for ciklussa
	vanBenne = false;
	for (int index=0; vanBenne == false && index < szov.Length; index++) if (szov[index] == 's') vanBenne = true;
	Console.WriteLine((vanBenne == true) ? "van" : "nincs" + " benne");
}

private static void eldontesTetele()
{
	// eldönti hogy van-e benneegy adott tulajdonságú elem. Amint talál kilép
	// a ciklusból
	char[] tomb = new char[3];
	tomb[0] = 'e';
	tomb[1] = 'k';
	tomb[2] = 'e';

	// van-e benne k betű
	bool vanBenne = false;
	int ciklusValtozo = 0;
	while (vanBenne==false && ciklusValtozo<tomb.Length)
	{
		if (tomb[ciklusValtozo] == 'k') vanBenne = true;
		ciklusValtozo++;
	}
	if (vanBenne == true) Console.WriteLine("van benne k betű");
	else Console.WriteLine("nincs benne k betű");

}

/// <summary>
/// feladat: 12 elemű tömb feltöltése [-50,50], majd kiíratása egy sorban.
/// Majd megszámoljuk mennyi a pozitív és mennyi ebből a negatív
/// </summary>
private static void megszamlalasTeteleFeladat()
{
	int[] tomb = new int[12];
	Random random = new Random();
	int pozitivDarab = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = random.Next(101)-50;
		if (tomb[i] >= 0) pozitivDarab++;
		Console.Write($"{tomb[i],5}");
	}
	Console.WriteLine();
	Console.WriteLine($"pozitv: {pozitivDarab}");
	Console.WriteLine($"negatív: {tomb.Length - pozitivDarab}");
}

/// <summary>
/// dokumentációs komment, ha az egeret ráviszed erre a metódusra, látni fogod
/// ezt a szöveget
/// </summary>
private static void megszamlalasTetele()
{
	// mennyi olyan elem van a tömbben ami egy bizonyos feltételnek megfelel
	// összeg=összeg+1
	// összeg+=1
	// összeg++
	char[] karakterTomb = new char[3];
	karakterTomb[0] = 'e';
	karakterTomb[1] = 'k';
	karakterTomb[2] = 'e';

	int osszeg = 0;
	for (int i = 0; i < karakterTomb.Length; i++)
	{
		if (karakterTomb[i] == 'e') osszeg++;
	}
	Console.WriteLine($"ennyi db 'e' betű van: {osszeg} db.");

	// hány 0-tól nagyobb szám van a tömbben
	int[] tomb = new int[5];
	tomb[0] = 3;
	tomb[1] = -2;
	tomb[2] = 10;
	tomb[3] = -3;
	tomb[4] = -7;
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] > 0) szamlalo++;
	}
	Console.WriteLine($"ennyi 0tól nagyobb van: {szamlalo}");
}

private static void osszegzesTeteleFeladat()
{
	/*
	 8 elemű egész számokból álló tömböt hozz létre
	töltsd fel [0,100]-os random számokkal
	a tömb elemeit íratsd ki egymás mellé
	számolja ki külön a tömb elemeinek az átlagát 
	2 tizedesre kerekítve
	 */

	Random r = new Random();
	int[] tomb = new int[8];
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(101); //[0,100]
		osszeg += tomb[i];
		Console.Write($"{tomb[i],5}");
	}
	Console.WriteLine();
	double avg = (double)osszeg / tomb.Length;
	Console.WriteLine($"átlg: {Math.Round(avg, 2)}");
}

private static void osszegzesTetele()
{
	// tömb elemeinek az összege
	// összeg=összeg+aktuális elem
	// összeg+=aktuális elem

	// 3 elemű egész szám tömb, aminek meg kell számolni az elemeit
	int[] tomb = new int[3];
	tomb[0] = 10;
	tomb[1] = 10;
	tomb[2] = 10;

	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
		// osszeg = osszeg + tomb[i];
	}
	Console.WriteLine($"számok összege: {osszeg}");

	// megszámolja a karakterek ASCII kóbeli értékének az összegét
	string sz = "ALMA";
	int stringOsszeg = 0;
	for (int i = 0; i < sz.Length; i++)
	{
		stringOsszeg += sz[i];
	}
	Console.WriteLine($"karakterek összege: {stringOsszeg}"); //283

	// nem mindegy hogy milyen típusba adunk folyamatosan elemeket
	// példáúl, ha string-be: +=, akkor az konkatenáció/összefűzés
	// ha int-be +=, mint az előző feladatrész, akkor az matematikai művelet
	string sz1 = "ALMA";
	string stringOsszeg2 = "";
	for (int i = 0; i < sz.Length; i++)
	{
		stringOsszeg2 += sz[i];
	}
	Console.WriteLine($"karakterek összege: {stringOsszeg2}"); //ALMA

	char[] karakterTomb = new char[4];
	karakterTomb[0] = 'A';
	karakterTomb[1] = 'L';
	karakterTomb[2] = 'M';
	karakterTomb[3] = 'A';

	int szamlalo = 0;
	for (int i = 0; i < karakterTomb.Length; i++)
	{
		szamlalo += sz[i];
	}
	Console.WriteLine($"karakterek összege: {szamlalo}"); //ALMA
}

private static void ismetles()
{
	// a tömböknek egyik nagy előnye hogy nem kell ezer meg egy 
	// változót létrehozni a különböző értékeknek
	// a tömbben egyszerre rengeteg értéket el tudok menteni
	int a = 6;
	int b = 7;
	// három elemű int tömb, kezőértékei 3 nulla
	int[] tomb = new int[3];
}
```
