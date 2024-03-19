```c#
// egysorosba [MŰKÖDIK]
File.ReadAllText("olvass_be.txt").Split(' ').ToList().Select(x =>new{ismetlesSzam=(x[0]=='n')?1:Convert.ToInt32(x[0].ToString()),ismetloKarakter=(x[0]=='n')?'\n':string.Join("", x.Skip(1))=="sp"?' ':string.Join("",x.Skip(1))=="bS"?'\\':string.Join("", x.Skip(1))=="sQ"?'\'':x[1]}).ToList().ForEach(x =>{for(int i=0;i<x.ismetlesSzam;i++) Console.Write(x.ismetloKarakter);});

Console.WriteLine('\n');

// többsorosba
string szoveg= File.ReadAllText("olvass_be.txt");
szoveg += " ";
string parancs = "";
for (int i = 0; i < szoveg.Length; i++)
{
	if(szoveg[i]!=' ')
	{
		parancs += szoveg[i];
	}
	else
	{
		if (parancs[0] == 'n')
		{
			Console.WriteLine();
		}
		else
		{
			// akkor valószínűleg egy számmal kezdődik
			int ismetlesSzam = Convert.ToInt32(parancs[0].ToString());
			string rovidites = "";
			char kiir = parancs[1];
			for (int j = 1; j < parancs.Length; j++)
			{
				rovidites += parancs[j];
			}
			if (rovidites == "sp") kiir = ' ';
			else if (rovidites == "bS") kiir = '\\';
			else if (rovidites == "sQ") kiir = '\'';
			for (int j = 0; j < ismetlesSzam; j++)
			{
				Console.Write(kiir);
			}
		}
		parancs = "";
	}
   
}
Console.ReadKey();
```