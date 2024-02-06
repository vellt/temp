```c#
static void Main(string[] args)
{
	// ismetles();
	// tombok();
	// tombok1();
	// tombok2();
	// tombok3();
	tombok4();
	Console.ReadKey();
}

private static void tombok4()
{
	// MIN MAX vizsgálat
	// 10 elemű tömb [-10,20]-ban
	int[] tomb = new int[10];
	Random r = new Random();
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(31)-10;
	}
	int min = tomb[0];
	int max = tomb[0];
	for (int i = 1; i < tomb.Length; i++)
	{
		if (min > tomb[i]) min = tomb[i];
		if (max < tomb[i]) max = tomb[i];
	}
	Console.WriteLine($"max: {max}");
	Console.WriteLine($"max: {min}");
}

private static void tombok3()
{
	// 5 elemű tömb, [5,10] intervallum
	// másoljuk ki a PÁROS értéket egy külön tömbbe
	int[] tomb = new int[5];
	Random r = new Random();
	int paros = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(6)+5;
		if (tomb[i] % 2 == 0) paros++;
	}
	int[] parosTomb = new int[paros];
	int parosTombIndex = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 2 == 0) 
		{
			parosTomb[parosTombIndex] = tomb[i];
			parosTombIndex++;
		}
	}
	for (int i = 0; i < parosTomb.Length; i++)
	{
		Console.WriteLine(parosTomb[i]);
	}
}

private static void tombok2()
{
	// mennyi pozitív és mennyi negatív
	// 5 elemű tömb
	// [-50,50] intervallumban
	Random r = new Random();
	int[] tomb = new int[5];
	int negativSzamlalo = 0;
	int pozitivSzamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(101) - 50; // [-50,50]
		if (tomb[i] < 0) negativSzamlalo++;
		else pozitivSzamlalo++;
	}
	Console.WriteLine($"pozitív: {pozitivSzamlalo}db");
	Console.WriteLine($"negatív: {negativSzamlalo}db");

}

private static void tombok1()
{
	// 3 elemű szöveges tömb, töltsük fel konzolból
	// és írassuk ki az elemeit
	string[] tomb = new string[3];
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = Console.ReadLine();
	}
	for (int i = 0; i < tomb.Length; i++)
	{
		Console.WriteLine(tomb[i]);
	}
}

private static void tombok()
{
	// bizonyítsuk be, hogy ha primitív típusból hozunk létre egy tömböt
	// akkor alapértelmezetten nullákkal tölti fel
	int num1 = 1;
	int num2 = 2;

	char[] tomb = new char[5];
	for (int i = 0; i < tomb.Length; i++)
	{
		Console.WriteLine((int)tomb[i]);
	}
}

private static void ismetles()
{
	// stringes dolgok

	string sz = "Az eg kek";
	for (int i = 0; i < sz.Length; i++)
	{
		if (sz[i] != ' ')
		{
			Console.Write(sz[i]);
		}
	}

	string sz1 = "9x10=90";
	int szamlalo = 0;
	for (int i = 0; i < sz1.Length; i++)
	{
		if (sz1[i] >= 48 && sz1[i] <= 57) szamlalo++;
	}
	Console.WriteLine(szamlalo);

	string sz2 = "AaAa";
	int szamlalo2 = 0;
	for (int i = 0; i < sz2.Length; i++)
	{
		if (sz2[i] >= 65 && sz2[i] <= 90) szamlalo2++;
	}
	Console.WriteLine(szamlalo2);

	char karakter = Console.ReadLine()[0];
	if (karakter >= 48 && karakter <= 57)
		Console.WriteLine("szám");
	else Console.WriteLine("nem szám");

	string sz3 = "alma";
	for (int i = 0; i < sz3.Length; i++)
	{
		Console.Write(sz3[i]);
	}
	Console.WriteLine();

	for (int i = sz3.Length - 1; i >= 0; i--)
	{
		Console.Write(sz3[i]);
	}
}
```
