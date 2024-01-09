```c#
// írassuk ki az 'a' betűt majd annak az ASCII kódbeli értékét
Console.WriteLine('a');
Console.WriteLine((int)'a');
// írassuk ki az 'b' betűt majd annak az ASCII kódbeli értékét
Console.WriteLine('b');
Console.WriteLine((int)'b');
// írassuk ki az 'z' betűt majd annak az ASCII kódbeli értékét
Console.WriteLine((int)'z');

// hogyan tudunk kis 'a'-ból nagy 'A'-t csinálni?
// 1. lépés megnézzük az 'A' értékét, majd a 'a' értékét
// kiprinteljük a konzolra, majd megnézzük a kettő különbségét
// látjuk, hogy 32 a differencia
Console.WriteLine((int)'A');
Console.WriteLine((int)'a');
// ezt a 32-es differenciát felhasználva tudunk
// kis 'a'-ból nagy 'A'-t gyártani
Console.WriteLine((char)('a'-32));

// Alakítsuk át egy név minden karakterét nagybetűssé
string nev = "benjamin";
// ezen plusz információk alapján:
// letudjuk akármelyik elemét a [index]-el hivatkozni
Console.WriteLine(nev[0]);
// megtudjuk egy szöveg hosszát mondani a length-el
Console.WriteLine(nev.Length);
// maga a feladat
for (int i = 0; i < nev.Length; i++)
{
	Console.Write((char)(nev[i]-32));
}
Console.WriteLine(); // ez azért kell hogy a következő sorra ugorjon, ne ugyan abban a sorban folytatódjon a kód

// az előző nev változót írassuk ki hátulról haladva
// a karakteren végig haladva, azaz fordított sorrendben
for (int i = nev.Length-1; i  >= 0; i--)
{
	Console.Write(nev[i]);
}
Console.WriteLine();


// maximum értéket megtaláljuk a nevunkbe
// azaz azt a karaktert ami a legnagyobb ASCII kódbeli értékkel bír
// azaz minél távolabb van az ABC kezdő értékeitől
int max = nev[0];
for (int i = 0; i < nev.Length; i++)
{
	if (nev[i] > max) 
	{
		max = nev[i];
	}
}
Console.WriteLine(max); // ez a maximum érték ASCII, 10es számrendszerben
Console.WriteLine((char)max); // ez pedig a konkrét karakter

// írassuk ki az abc minden második karakterét
// ahhoz kell tudnunk, hogy mi az 'a' tizes számredszerben-->97
// és hogy mi a 'z' tizes számrendszerben-->122
for (int i = 97; i <= 122; i+=2)
{
	Console.WriteLine($"{(char)i}");
}


Console.ReadKey();
```
