```c#
static void Main(string[] args)
{
	matrix();
	matrixKomplexGyak();
	Console.ReadKey();
}

private static void matrixKomplexGyak()
{
	/*
	 * 14 fős csoportban a tanulók minden hónapban írtak egy dogát
	 * eltelt 4 hónap. Minden tanuló kapott [1,5]-ban egy-egy jegyet.
	 * 
	 * - mennyi a tanulók átlaga
	 * - mennyi az osztályátlag
	 * - mennyi tanuló áll bukásra (1.6 alatt)
	 * - mennyi tanulónak van CSAK 1-es jegye
	 * - mennyi tanuló van az osztályátlag alatt
	 * 
	 * - van-e olyan tanuló aki ötösre áll (4.6 vagy felette)
	 * - van-e olyan tanuló aki csak 3-ast szerzett
	 * - van-e olyan tanuló akinek az első és az utolsó jegye megegyezik
	 */
	int[,] tanulok = new int[14, 4];
	Random r = new Random();
	for (int i = 0; i < tanulok.GetLength(0); i++)
	{
		for (int j = 0; j < tanulok.GetLength(1); j++)
		{
			tanulok[i, j] = r.Next(5) + 1; // [1,5]
		}
	}
	// mennyi a tanulók átlaga
	for (int i = 0; i < tanulok.GetLength(0); i++) //14
	{
		int osszJegy = 0;
		for (int j = 0; j < tanulok.GetLength(1); j++)
		{
			osszJegy += tanulok[i, j];
		}
		double atlag = osszJegy / (double)tanulok.GetLength(1);
		Console.WriteLine($"{i + 1}. tanuló: {atlag:0.00}");
	}
}

private static void matrix()
{
	int[,] matrix = new int[2, 4];
	Random r = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			matrix[i, j] = r.Next(10); //[0,9]
			Console.Write($"{matrix[i,j]} ");
		}
		Console.WriteLine();
	}
}
```