```c#
// printeljük ki, mit látunk?
int sz1 = 65;
int sz2 = 76;
int sz3 = 77;
int sz4 = 65;
Console.WriteLine($"{sz1} {sz2} {sz3} {sz4}");

// és most?
Console.WriteLine($"{(char)sz1} {(char)sz2} {(char)sz3} {(char)sz4}");

// alakítsuk nagybetűssé az "x, y, z"-t pl--> X, Y, Z
Console.WriteLine($"{'x' - 32} {'y' - 32} {'z' - 32}");


// írassuk ki az a,b,c betűit egymás alá
for (int i = 97; i <= 122; i++)
{
	Console.WriteLine($"{i}-->{(char)(i-32)}");
}

// szöveg mint tömb-------------------------------------------------
string beka = "beka";
Console.WriteLine(beka.Length); // szöveg hossza
Console.WriteLine(beka[0]); // szöveg első eleme (első karakter)
Console.WriteLine((int)beka[0]); // a szöveg első elemének az ASCII kódja (azonosítója)

// készítsen egy programot ami bekér egy szöveget,
// és minden második karakterést írja csak ki
Console.WriteLine("adj meg egy szöveget");
string szoveg = Console.ReadLine();
for (int i = 1; i < szoveg.Length; i+=2) // kettesével léptetem
{
	Console.Write(szoveg[i]);
}
Console.WriteLine();

// minden 5. karaktert írjunk csak ki
Console.WriteLine("adj meg egy szöveget");
string szoveg2 = Console.ReadLine();
for (int i = 5; i < szoveg2.Length; i += 5)
{
	Console.Write(szoveg2[i]);
}
Console.WriteLine();

// a bekért szöveget fordított sorrendben
Console.WriteLine("adj meg egy szöveget");
string sz= Console.ReadLine();
for (int i = sz.Length-1; i >=0; i--)
{
	Console.WriteLine(sz[i]);
}
Console.WriteLine();

// van-e t betű a bekért szövegben
Console.WriteLine("add meg a szöveget és megmondom, hogy van-e benne t");
string vlmi = Console.ReadLine();
int szamlalo = 0;
for (int i = 0; i < vlmi.Length; i++)
{
	if (vlmi[i] == 't')
	{
		szamlalo++;
	}
}
if(szamlalo>0) Console.WriteLine("van t betű");

// ----------------------------------------------------------
// (kis érdekesség)
// konstansok típusa futásidőben
Console.WriteLine("6".GetType());
Console.WriteLine('6'.GetType());
Console.WriteLine(6.GetType());
Console.WriteLine(6.0.GetType());
// ----------------------------------------------------------

// kérjünk be egy hosszú
// szöveget és az utolsó 5 karakterét írjuk ki
Console.WriteLine("adj meg egy hosszú szöveget");
string hosszuSzoveg = Console.ReadLine();
for (int i = (hosszuSzoveg.Length-1)-5; i < hosszuSzoveg.Length; i++)
{
	Console.Write(hosszuSzoveg[i]);
}
Console.WriteLine();

// nézzük meg van-e a bekért szövegben magánhangzó, ha igen--> írjuk ki hogy van és hogy hány db
Console.WriteLine("adj merg egy szoveget");
string sz100 = Console.ReadLine();
int db = 0;
for (int i = 0; i < sz100.Length; i++)
{
	if(    sz100[i]=='a' 
		|| sz100[i]=='e' 
		|| sz100[i]=='i' 
		|| sz100[i]=='u' 
		|| sz100[i]=='o')
	{
		db++;
	}
}
if (db > 0)
{
	Console.WriteLine("van magánhangzó benne");
	Console.WriteLine(db);
}

// a bekért szövegből a magánhanzókat cseréljük le i-re, pl kerekpar-->kirikpir
Console.WriteLine("adj merg egy szoveget");
string sz101 = Console.ReadLine();
for (int i = 0; i < sz101.Length; i++)
{
	if (sz101[i] == 'a'
		|| sz101[i] == 'e'
		|| sz101[i] == 'u'
		|| sz101[i] == 'o')
	{
		Console.Write('i');
	}
	else
	{
		Console.Write(sz101[i]);
	}
}

// alakítsuk a keresztneveünket nagybetűssé
string nev= "benjamin";
for (int i = 0; i < nev.Length; i++)
{
	Console.Write((char)(nev[i]-32));
}


Console.ReadKey();
```
