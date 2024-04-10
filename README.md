```c#
static void Main(string[] args)
{
	egyDimGyak1();
	egyDimGyak2();
	Console.ReadKey();
}

private static void egyDimGyak1()
{
	// N hosszúságú tömböt hozzon létre, [-10,50]-ban töltse fel elemeit
	// N értékét konzolból kérjük be
	Console.WriteLine("Add meg a tömb hosszát");
	int N = Convert.ToInt32(Console.ReadLine()); //6
	int[] tomb = new int[N];
	Random r = new Random();
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(61) - 10; // [-10,50]
	}

	// - Mennyi a pozitív számok összege
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] > 0) osszeg += tomb[i];
	}
	Console.WriteLine(osszeg);

	// - mennyi a 2-vel és 7-el osztható szám van benne
	int darab = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 7 == 0 && tomb[i] % 2 == 0) darab++;
	}
	Console.WriteLine(darab);

	// - van-e legalább 2 negatív szám benne
	int negativ = 0;
	for (int i = 0; negativ != 2 && i < tomb.Length; i++)
	{
		if (tomb[i] < 0) negativ++;
	}
	Console.WriteLine(negativ == 2 ? "van" : "nincs");

	// - mennyi a számok átlaga
	int sum = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		sum += tomb[i];
	}
	double atlag = (double)sum / tomb.Length;
	Console.WriteLine(atlag);
}

private static void egyDimGyak2()
{
	// készítsen egy N hosszúságú string tárolására alkalmas 1 dim tömböt
	// Járja körbe és töltse fel konzolból az elemeit

	Console.WriteLine("add meg a tömb hosszát/ N értékét");
	int N = Convert.ToInt32(Console.ReadLine());

	string[] tomb = new string[N];
	for (int i = 0; i < tomb.Length; i++)
	{
		Console.Write($"Add meg a tömb {i+1}. elemét: ");
		tomb[i] = Console.ReadLine();
	}

	// mennyi olyan szó van amiben van 'a' betű
	int megfeleloElemekSzama = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		string szoveg = tomb[i];
		int aBetukSzama = 0;
		for (int karakter = 0; aBetukSzama==0 && karakter < szoveg.Length; karakter++)
		{
			if (szoveg[karakter] == 'a') aBetukSzama++;
		}
		if (aBetukSzama != 0) megfeleloElemekSzama++;
	}
	Console.WriteLine(megfeleloElemekSzama) ;

	// nagybetűseket alaktsa kisbetűssé
	for (int i = 0; i < tomb.Length; i++)
	{
		string szoveg = tomb[i];
		for (int j = 0; j < szoveg.Length; j++)
		{
			if(szoveg[j]>='A' && szoveg[j]<='Z')
			{
				Console.Write((char)(szoveg[j]+32));
			}
			else
			{
				Console.Write(szoveg[j]);
			}
		}
	}
	int darab = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		Console.Write(tomb[i].ToLower());
		if (tomb[i].Contains('a')) darab++;
	}
}
```