```c#
static void Main(string[] args)
{
	binToDec();
	DecToBin1();
	DecToBin2();
	// ne ezzel oldjátok meg, de ilyen
	// egyszerűbb megoldások is vannak mint ez
	Console.WriteLine("11101", 10);
	Console.ReadKey();
}

private static void DecToBin2()
{
	int dec = 29;
	string bin = "";
	while (dec!=0)
	{
		bin += dec % 2;
		dec /= 2;
	}
	for (int i = bin.Length - 1; i >= 0; i--)
	{
		Console.Write(bin[i]);
	}
}

private static void DecToBin1()
{
	int dec = 33;
	string bin = "";
	int hatvany = 0;
	while (Math.Pow(2, hatvany)<=dec)hatvany++ ;
	hatvany--;
	int osszeg = 0;
	for (int i = hatvany; i >= 0; i--)
	{
		if (osszeg + Math.Pow(2, i) <= dec)
		{
			osszeg += (int)Math.Pow(2, i);
			bin += "1";
		}
		else
		{
			bin += '0';
		}
	}
	Console.WriteLine(bin);
}

private static void binToDec()
{
	string bin = "11101";
	int dec = 0;
	int hatvany = bin.Length - 1;
	for (int i = 0; i < bin.Length; i++, hatvany--)
	{
		if (bin[i] == '1') dec += (int)Math.Pow(2, hatvany); // 4-->3-->2-->1-->0
	}
	Console.WriteLine(dec);
}
```