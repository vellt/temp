```c#
static void Main(string[] args)
{
	// vektorok
	// 12 napig megmértük a napi csapadék mennyiséget.
	// határozza meg mennyi eső esett összesen
	Random r = new Random();
	int[] csapadekok = new int[12];
	int osszeg = 0;
	for (int i = 0; i < csapadekok.Length; i++)
	{
		csapadekok[i] = r.Next(21)+10;
		osszeg += csapadekok[i];
	}
	Console.WriteLine(osszeg);

	// ismerjük 9 autó fogyasztását. Döntsük el, hogy minden autó
	// 10 liter alatt fogyasztott-e
	// + folyamatábra

	int[] fogyasztasok = new int[9];
	int szamlalo = 0;
	for (int i = 0; i < fogyasztasok.Length; i++)
	{
		fogyasztasok[i] = r.Next(12) + 4;
		if (fogyasztasok[i] < 10)
		{
			szamlalo++;
		}
	}
	if (szamlalo != fogyasztasok.Length)
	{
		Console.WriteLine("Nem minden autónak 10 liter a fogyasztása");
	}
	else
	{
		Console.WriteLine("Minden 10 liter alatti");
	}

	string[] tomb = new string[3];
	for (int i = 0; i < tomb.Length ; i++)
	{
		tomb[i] = Console.ReadLine(); // sapka, kalap, sál
	}
	// mennyi az átlagos szöveghossz
	int osszesHossz = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		string szoveg = tomb[i];
		int hossz = szoveg.Length;
		osszesHossz += hossz;
	}
	double atlag = osszesHossz / (double)tomb.Length;
	Console.WriteLine($"Átlagos szöveghossz: {atlag}");

	// tartalmaz-e a tömb 7db karakterből álló szöveget?
	bool van = false;
	for (int i = 0; van==false&& i < tomb.Length; i++)
	{
		if (tomb[i].Length == 7) van = true;
	}
	Console.WriteLine(van ? "van" : "nincs");

	// van-e olyan aminek a keződbetűje 'a' az utolsó betűje "k"
	van = false;
	for (int i = 0; van==false && i < tomb.Length; i++)
	{
		string szoveg = tomb[i];
		char kezdoKarakter = szoveg[0];
		char vegKarakter = szoveg[szoveg.Length-1];
		if (kezdoKarakter == 'a' && vegKarakter == 'k') van = true;
	}
	Console.WriteLine(van ? "van" : "nincs");

	// a hónap minden napján megmértük a hőméréskletet egy éven keresztül
	// 1 hó-->30 nap. A napok [-10,10]-ban töltsük fel.
	// a-> mennyi az átlaghőmérséklet
	// b-> mennyi olyan hónap volt, ahol -3 fok alatti az átlaghőmérséklete
	// c-> mennyi az éves átlaghőmérséklet
	int[,] homersekletek = new int[12, 30];
	int szamalalo = 0;
	double atlagHomersekletek = 0;
	for (int i = 0; i < homersekletek.GetLength(0); i++)
	{
		int egyHonapOsszHomerseklete = 0;
		for (int j = 0; j < homersekletek.GetLength(1); j++)
		{
			homersekletek[i, j] = r.Next(21) - 10;
			egyHonapOsszHomerseklete += homersekletek[i, j];
			
		}
		double egyHonapAtlagHomerseklete = egyHonapOsszHomerseklete / 30.0;
		Console.WriteLine($"{i+1}. hónap átlag hőm.: {egyHonapAtlagHomerseklete:0.00}");
		if (egyHonapAtlagHomerseklete < -3) szamalalo++;
		atlagHomersekletek += egyHonapAtlagHomerseklete;
	}
	Console.WriteLine($"Ennyi hónap van -3 fok alatti átlaghőmérséklettel: {szamalalo} db");
	double atlaghomerseklet = atlagHomersekletek / 12;
	Console.WriteLine($"Az éves átlaghőmérséklet: {atlaghomerseklet:0.00}");
```