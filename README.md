```c#
Random random = new Random();
int sz = random.Next(10);//[0,9]
// [20,50]
int sz1 = random.Next(31)+20;
// [30,35]
int sz2 = random.Next(6)+30;
// [-5,5]
int sz3 = random.Next(11)-5;
// [-10,2]
int sz4 = random.Next(13)-10;
// [-10,-5]
int sz5 = random.Next(6)-10;
// [-30,-15]
int sz6 = random.Next(16)-30;

// képezzünk 3 random számot [-30, 50]
// írassuk ki a változók kezdeti értékét
// cserélgessük csökkenő sorrendbe
// majd megint írjuk ki a változók értékeit

// mondjuk meg a legnagyobb és a legkisebb különbségét
// mennyi ennek a különbségnek az abs
// a legkisebbet osszuk el a legnagyobbal !2 tizedes!

Random random1 = new Random();
int szam1 = random1.Next(81)-30;
int szam2 = random1.Next(81)-30;
int szam3 = random1.Next(81)-30;

Console.WriteLine($"{szam1} {szam2} {szam3}");

if (szam1 < szam2)
{
	int temp = szam1;
	szam1 = szam2;
	szam2 = temp;
}
if (szam1 < szam3)
{
	int temp = szam1;
	szam1 = szam3;
	szam3 = temp;
}
if (szam2 < szam3)
{
	int temp = szam2;
	szam2 = szam3;
	szam3 = temp;
}

Console.WriteLine($"{szam1} {szam2} {szam3}");


// mondjuk meg a legnagyobb és a legkisebb különbségét
int kulonbseg = szam1 - szam3;
Console.WriteLine(kulonbseg);

// mennyi ennek a különbségnek az abs
if (kulonbseg < 0)
{
	Console.WriteLine(kulonbseg*-1);
}
else
{
	Console.WriteLine(kulonbseg);
}

// a legkisebb/legnagyobb-->2tizedes
Console.WriteLine(Math.Round((szam1/Convert.ToDouble(szam3)),2));

// ciklusok--------------------------------

// while ciklussal
// a felh-tól kérjunk be 2 számot (x,y), az x-nek kisebbnek kell
// lennie az y-tól
// x-től y-ig ki kell listázni páros számokat

Console.WriteLine("Add meg az x értékét");
int x = Convert.ToInt32(Console.ReadLine());

Console.WriteLine("Add meg az y értékét");
int y = Convert.ToInt32(Console.ReadLine());

while (x!=y+1)
{
	Console.WriteLine(x);
	x++;
}

//készítsünk egy programot, amely 15 db '*'-ot ír ki a 
// képernyőre egymás mellé!!
int szamlalo = 0;
while (szamlalo<15)
{
	szamlalo++;
	Console.Write("*");
}

// Írassuk ki a számokat 1-től 20ig, és azok négyzetét
// 2-->4
// 3-->9

int szamlalo1 = 1;

while (szamlalo1<=20)
{
	Console.WriteLine($"{szamlalo1}-->{szamlalo1*szamlalo1}");
	szamlalo1++;
}


// Írassa ki 99-től 1-ig csökkenő sorrendben az összes pozitív, 3-al
// osztható egész számot
int valtozo = 99;
while(valtozo!=0)
{
	if(valtozo%2==0 && valtozo%3==0)
	{
		Console.WriteLine(valtozo);
	}
	valtozo--;
}

// kérjen be folyamatosan számokat mindaddig mig 0-t nem adunk meg
// ekkor irja ki, hogy "elég", és megáll
int felh = -1;

while (felh!=0)
{
	Console.WriteLine("Adj meg egy szamot");
	felh = Convert.ToInt32(Console.ReadLine());
	if (felh == 0)
	{
		Console.WriteLine("elég");
	}
}


// Számolja ki az éves középhőmérsékletet miután a felh. megadta
// a havi középhőmrésékleteket.

int honap = 1;
int osszHomerseklet = 0;
while (honap!=13)
{
	int honapHomerseklete = Convert.ToInt32(Console.ReadLine());
	osszHomerseklet = osszHomerseklet + honapHomerseklete;
	honap++;
}
Console.WriteLine($"Az éves középhőmérséklet: {osszHomerseklet/12.0}");

// döntsük el egy számról, hogy prímszám-e
int osztoDarabSzam = 0;
int primE = 5;
int amivelOsztunk = primE;
while (amivelOsztunk!=0)
{
	if (primE % amivelOsztunk == 0)
	{
		// ez egy osztója
		osztoDarabSzam++;
	}
	amivelOsztunk--;
}
if (osztoDarabSzam == 2)
{
	Console.WriteLine("a szám prim");
}
else
{
	Console.WriteLine("nem prim");
}



Console.ReadKey();
```
