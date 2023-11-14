```c#
/*
	összetett logikai kifejezések
	if struktúra átalakítható-e switch-é
	egy paraméteres random, azokkal való művelet
	3 vagy több elem növekvő/csökkenő sorrendbe való cserélgetése
	while, do while ciklusok
 */
// növekvő sorrendbe rendezés
int a = 76;
int b = -6;
int c = 5;
Console.WriteLine($"{a} {b} {c}");
if (a > b)
{
	int temp = a;
	a = b;
	b = temp;
}
if (a > c)
{
	int temp = a;
	a = c;
	c = temp;
}
if (b > c)
{
	int temp = c;
	c = b;
	b = temp;
}
Console.WriteLine($"{a} {b} {c}");

// while ciklus

//10-1 ig csökkenő sorrendben listázzuk ki a számokat

int szam = 10;
while (szam>=1)
{
	Console.WriteLine(szam);
	szam--;
}


//1-20ig az összes páratlan
int szam1 = 1;
while (szam1<=20)
{
	if(szam1%2!=0)
	{
		Console.WriteLine(szam1);
	}
	szam1++;
}

// 1-20ig az összes 5el osztható
int szam2 = 1;
while (szam2 <= 20)
{
	if (szam2 % 5 == 0)
	{
		Console.WriteLine(szam2);
	}
	szam2++;
}

// 1-20ig az összes páros számot, ami egyben 5el is osztható
int szam3 = 1;
while (szam3 <= 20)
{
	if ((szam3 % 5 == 0) && (szam3 % 2 == 0))
	{
		Console.WriteLine(szam3);
	}
	szam3++;
}

// kérjen be a felh-tól egy számmot, és adja folyamatosan össze, amíg a felhasználó
// nem ad be a konzolról 0-t

// while ciklus elöl tesztel
// do while ciklus hátul tesztel, itt feltételtöl függetlenül lefut 1x a program
int osszeguk = 0;
int felh = 1;

while (felh!=0)
{
	Console.Write("Add meg az új számot: ");
	felh = Convert.ToInt32(Console.ReadLine());
	osszeguk = osszeguk + felh;
}

osszeguk = 0;
felh = 0;
do
{
	Console.Write("Add meg az új számot: ");
	felh = Convert.ToInt32(Console.ReadLine());
	osszeguk = osszeguk + felh;
} while (felh!=0);

// készítsünk egy faktoriális számláló alkalmazást
// 4! -->4*3*2*1
// 3! -->3*2*1
int aminekSzeretnenkAFaktorialisat = 4;
int faktorialisOsszeg = aminekSzeretnenkAFaktorialisat;

while (aminekSzeretnenkAFaktorialisat>=2)
{
	aminekSzeretnenkAFaktorialisat--;
	faktorialisOsszeg = faktorialisOsszeg * aminekSzeretnenkAFaktorialisat;
}
Console.WriteLine($"A 4! ={faktorialisOsszeg}");

// (5ért)--> Írja ki az első N db prímszámot, N--> az amit a felhasználó ad meg


// if struktúra átalakítható-e switch szerkezetté
// az alakítható át, ami "if, else if, else" vagy "if, else" láncolatot követ
// egy adott értéket hasonlít össze több konstanssal és nem pedig változóval
// logikai operátora szigorúan ==
// if, else if--> case
// else --> default

int x = 7;
int y = 8;
int z = 10;
if (x == y)
{
	Console.WriteLine("x és y egyenlőek");
}else if (x == z)
{
	Console.WriteLine("x és z egyenlőek");
}else
{
	Console.WriteLine("x nem egyenlő y-al sem pedig z-vel");
}
// nem alakítható át, mert az x változót y illetve z változóval hasinlítom össze
switch (x)
{
	case y:
		Console.WriteLine("x és y egyenlőek");
		break;
	case z:
		Console.WriteLine("x és z egyenlőek");
		break;
	default:
		Console.WriteLine("x nem egyenlő y-al sem pedig z-vel");
		break;
}


int x2 = 7;
int y2 = 8;
int z2 = 10;
if (x2 == 8)
{
	Console.WriteLine("x és y egyenlőek");
}
else if (x2 == 10)
{
	Console.WriteLine("x és z egyenlőek");
}
else
{
	Console.WriteLine("x nem egyenlő y-al sem pedig z-vel");
}
// átalakítható, mert a case eseteknél csak konstans lehet,
switch (x)
{
	case 8:
		Console.WriteLine("x és y egyenlőek");
		break;
	case 10:
		Console.WriteLine("x és z egyenlőek");
		break;
	default:
		Console.WriteLine("x nem egyenlő y-al sem pedig z-vel");
		break;
}


// átalakítható-e

int vegossszeg = 10_000;
string kedvezmeny = "10%";
if (kedvezmeny == "10%")
{
	Console.WriteLine($"A kedvezmenyes végösszeg: {vegossszeg*0.9}");
}else if (kedvezmeny == "50%")
{
	Console.WriteLine($"A kedvezmenyes végösszeg: {vegossszeg * 0.5}");
}
else if (kedvezmeny == "60%")
{
	Console.WriteLine($"A kedvezmenyes végösszeg: {vegossszeg * 0.4}");
}
else
{
	Console.WriteLine($"Nállunk nics ilyen kedvezmeny");
}
// átalakítható
switch (kedvezmeny)
{
	case "10%":
		Console.WriteLine($"A kedvezmenyes végösszeg: {vegossszeg * 0.9}");
		break;
	case "50%":
		Console.WriteLine($"A kedvezmenyes végösszeg: {vegossszeg * 0.5}");
		break;
	case "60%":
		Console.WriteLine($"A kedvezmenyes végösszeg: {vegossszeg * 0.4}");
		break;
	default:
		Console.WriteLine($"Nállunk nics ilyen kedvezmeny");
		break;
}


//átalakítható?
int ora = 12;
int perc = 30;
if(ora==10 && perc == 30)
{
	Console.WriteLine("Még van 2 órám kezésig");
}else if (ora == 12)
{
	Console.WriteLine("Még van fél órám a kezdésig");
}else
{
	Console.WriteLine("Elkéstem");
}
// az első feltétel "ora==10 && perc == 30" miatt nem alakítható át

Console.ReadKey();
```
