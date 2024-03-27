```c#
static void Main(string[] args)
{
	//dogaGyak();

	// mátrix kezelés
	int[,] matrix = new int[5, 5];
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			if (j % 5 == 0) Console.WriteLine();
			Console.Write($"{matrix[i, j],3}");
		}
	}
	// rajzoljuk ki csak bizonyos elemit a mátrixnak a megadott minták alapján
	Console.WriteLine("\n---------------");
	a(matrix);
	Console.WriteLine("\n---------------");
	b(matrix);
	Console.ReadKey();
}

private static void b(int[,] matrix)
{
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			if (j % 5 == 0) Console.WriteLine();
			if (i == 0 || j==0 || i==4 || j==4) Console.Write($"{'-',3}");
			else Console.Write($"{matrix[i, j],3}");
		}
	}
}

private static void a(int[,] matrix)
{
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			if (j % 5 == 0) Console.WriteLine();
			if(j==2) Console.Write($"{matrix[i,j],3}");
			else if (i == 2) Console.Write($"{matrix[i, j],3}");
			else Console.Write($"{'-',3}");
		}
	}
}

private static void dogaGyak()
{
	int[,] matrix = new int[12, 30];
	Random r = new Random();
	double osszAtlag = 0;
	for (int honap = 0; honap < matrix.GetLength(0); honap++)
	{
		int osszHomerseklet = 0;
		for (int nap = 0; nap < matrix.GetLength(1); nap++)
		{
			matrix[honap, nap] = r.Next(26) - 15; //[-15,10]
			osszHomerseklet += matrix[honap, nap];
		}
		double atlag = osszHomerseklet / 30.0;
		osszAtlag += atlag;
	}
	double evesAtlag = osszAtlag / 12;
	Console.WriteLine(osszAtlag);

	bool van = false;
	for (int honap = 0; van == false && honap < matrix.GetLength(0); honap++)
	{
		int osszHomerseklet = 0;
		for (int nap = 0; nap < matrix.GetLength(1); nap++)
		{
			osszHomerseklet += matrix[honap, nap];
		}
		double atlag = osszHomerseklet / 30.0;
		if (atlag < evesAtlag) van = true;
	}
	Console.WriteLine(van ? "van" : "nincs");

	van = false;
	for (int honap = 0; van == false && honap < matrix.GetLength(0); honap++)
	{

		for (int nap = 0; van == false && nap < matrix.GetLength(1); nap++)
		{
			if (matrix[honap, nap] == -2) van = true;
		}
	}
	Console.WriteLine(van ? "van" : "nincs");
}
```