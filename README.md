```c#
// dolgozat témája: [karakterek/ASCII, string, mint tömb]

// karakter típusból hogy nyerem ki az ASCII kódot? 
// (int)
char karakter = 'b';
Console.WriteLine((int)karakter); // 98
Console.WriteLine(karakter); // b

// "ASCII" kódból, hogy nyerem ki a karaktert?
// (char)
int asciiAzonosito = 97;
Console.WriteLine(asciiAzonosito); // 97
Console.WriteLine((char)asciiAzonosito); // a

// string, mint tömb-------------------------------------------
// a string pár fontosabb fulajdonsága
string alma = "alma";
Console.WriteLine(alma[0]); // első karakter
Console.WriteLine(alma[alma.Length-1]); // utolsó kar.

// járjuk körbe az alma változó karaktereit, és írassuk ki
// karakterenkét a konzolra
for (int i = 0; i < alma.Length; i++)
{
	Console.Write(alma[i]);
}
Console.WriteLine();

// járjuk ugyan ezt a változót körbe
// viszont hátulról előre haladva
for (int i = alma.Length - 1; i >= 0; i--)
{
	Console.Write(alma[i]);
}
Console.WriteLine();

// melyik indexen található az 'l'
// ha -1en marad az azt jelenti, hogy nem volt találat
int lIndex = -1; 
// mennyi db 'l' betű van benne?
// azt már számlálóval tudjuk megállapítani:
int lDb = 0;
for (int i = 0; i < alma.Length; i++)
{
	if (alma[i] == 'l') 
	{
		// ha van találat ezek történnek
		lIndex = i;
		lDb++;
	}
}
Console.WriteLine(lDb); // kiírjuk mennyi db 'l' volt benne
// (eldöntés tétele)
if (lIndex == -1)
{
	Console.WriteLine("nincs benne l");
}
else
{
	Console.WriteLine($"Van benne, méghozzá: {lIndex}. indexen");
}

// készítsünk monogrammot: kiss pista-->K.P.
string nev = "kiss pista";
Console.Write($"{(char)(nev[0] - 32)}.");
for (int i = 0; i < nev.Length; i++)
{
	if(nev[i]==' ')
	{
		Console.Write($"{(char)(nev[i+1] - 32)}.");
	}
}
Console.WriteLine();

// minden második karakter nagybetűs legyen
string sz1 = "abrakadabra";
for (int i = 0; i < sz1.Length; i++)
{
	if (i % 2 == 0)
	{
		Console.Write(sz1[i]);
	}
	else
	{
		Console.Write((char)(sz1[i]-32));
	}
}
Console.WriteLine();

// minden karakterének az ASCII értékét jelenítsük meg,
// kiíratva egymás mellé szóközzel elválasztva
string sz2 = "bela";
for (int i = 0; i < sz2.Length; i++)
{
	Console.Write($"{(int)sz2[i]} ");
}
Console.WriteLine();

// minden - (kötőjel) --> : (kettőspont)-ra
// cseréljünk ki kiíratáskor
// 6C-A6-77-44-C8-EA
// 6C:A6:77:44:C8:EA
string mac = "6C-A6-77-44-C8-EA";
for (int i = 0; i < mac.Length; i++)
{
	if (mac[i] == '-')
	{
		Console.Write(':');
	}
	else
	{
		Console.Write(mac[i]);
	}
}
Console.WriteLine();

// maximum értéket (karaktert) találjuk meg
// (ami az abc kezdőbetűjétől a legtávolabb van,
// mert annak a legnagyobb az ASCII kódbéli értéke is egyben)
string sz4 = "holnaputan";
int max = sz4[0];
for (int i = 1; i < sz4.Length; i++)
{
	if (sz4[i] > max)
	{
		max = sz4[i];
	}
}
Console.WriteLine($"max: {(char)max}");

// indexekkel határozzuk meg a legnagyobb karaktert
// ez kicsit jobb megoldás mert nem csak, hogy a maximum értékét
// tudjuk lehivatkozni, de a konkrét helyét a szövegben is megmutatja
int maxIndex = 0;
for (int i = 0; i < sz4.Length; i++)
{
	if (sz4[i] > sz4[maxIndex])
	{
		maxIndex = i;
	}
}
Console.WriteLine($"{sz4[maxIndex]}, amely a {maxIndex}.-en van");

// szóközök mentén sortörés
string felh = Console.ReadLine();
for (int i = 0; i < felh.Length; i++)
{
	if(felh[i]==' ')
	{
		Console.WriteLine();
	}
	else
	{
		Console.Write(felh[i]);
	}
}
Console.WriteLine();

// ugyan az mint az előző, csak fordított sorrendben
for (int i = felh.Length - 1; i >= 0; i--)
{
	if (felh[i] == ' ')
	{
		Console.WriteLine();
	}
	else
	{
		Console.Write(felh[i]);
	}
}
Console.WriteLine();

// döntsük el, hogy a megadott karakter az szám-e?
char ascii = '7';
if(ascii>=48 && ascii <= 57)
{
	Console.WriteLine("szám a karakter");
}
else
{
	Console.WriteLine("nem szám");
}
```
