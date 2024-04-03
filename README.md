```c#
class Caesar 
{
	public static string Titkositas(string uzenet)
	{
		string titkositott = "";
		char[] abc = abcFeltolt();
		for (int i = 0; i < uzenet.Length; titkositott += abc[karakterTitkositas(karakterIndex(uzenet[i++], abc))]);
		return titkositott;
	}

	public static string Visszafejtes(string uzenet)
	{
		string visszafejtett = "";
		char[] abc = abcFeltolt();
		for (int i = 0; i < uzenet.Length; visszafejtett += abc[karakterVisszafejtes(karakterIndex(uzenet[i++], abc))]);
		return visszafejtett;
	}

	private static int karakterVisszafejtes(int x)
	{
		int maradek = (x - 3) % 26;
		return maradek < 0 ? maradek + 26 : maradek;
	}

	private static int karakterTitkositas(int x)
	{
		return (x + 3) % 26;
	}

	private static int karakterIndex(char karakter, char[] abc)
	{
		int index = -1;
		for (int i = 0; index == -1 && i < abc.Length; i++) if (karakter == abc[i]) index = i;
		return index;
	}

	private static char[] abcFeltolt()
	{
		char[] temp = new char[26];
		for (int i = 0; i < temp.Length; i++) temp[i] = (char)(65 + i);
		return temp;
	}
}

class Program
{
	static void Main(string[] args)
	{
		Console.WriteLine(Caesar.Titkositas("PLAY"));
		Console.WriteLine(Caesar.Visszafejtes(Caesar.Titkositas("PLAY")));
		Console.ReadKey();
	}
}
```