# dot-gimei
.NET port of [gimei](https://github.com/willnet/gimei), inspired by [go-gimei](https://github.com/mattn/go-gimei)

## Installation
Available via [Nuget](https://www.nuget.org/packages/dot-gimei/)

```powershell
PM> Install-Package dot-gimei
```

## Usage
```csharp
using System;
using DotGimei;

class Program
{
    public static void Main(string[] args)
    {
        var name = Gimei.NewName();
        Console.WriteLine(name);                // �֓� �z��
        Console.WriteLine(name.Kanji);          // �֓� �z��
        Console.WriteLine(name.Hiragana);       // �����Ƃ� �͂��
        Console.WriteLine(name.Katakana);       // �T�C�g�E �n���i
        Console.WriteLine(name.Last.Kanji);     // �֓�
        Console.WriteLine(name.Last.Hiragana);  // �����Ƃ�
        Console.WriteLine(name.Last.Katakana);  // �T�C�g�E
        Console.WriteLine(name.First.Kanji);    // �z��
        Console.WriteLine(name.First.Hiragana); // �͂��
        Console.WriteLine(name.First.Katakana); // �n���i
        Console.WriteLine(name.IsMale);         // false

        var male = Gimei.NewMale();
        Console.WriteLine(male);          // ���� ���m
        Console.WriteLine(male.IsMale);   // true
        Console.WriteLine(male.IsFemale); // false

        var address = Gimei.NewAddress();
        Console.WriteLine(address);                     // ���R���哇�S��a����ؒ�
        Console.WriteLine(address.Kanji);               // ���R���哇�S��a����ؒ�
        Console.WriteLine(address.Hiragana);            // ������܂��񂨂����܂����܂Ƃ��񂢂Ȃ����傤
        Console.WriteLine(address.Katakana);            // �I�J���}�P���I�I�V�}�O�����}�g�\���C�i�M�`���E
        Console.WriteLine(address.Prefecture);          // ���R��
        Console.WriteLine(address.Prefecture.Kanji);    // ���R��
        Console.WriteLine(address.Prefecture.Hiragana); // ������܂���
        Console.WriteLine(address.Prefecture.Katakana); // �I�J���}�P��
        Console.WriteLine(address.Town);                // �哇�S��a��
        Console.WriteLine(address.Town.Kanji);          // �哇�S��a��
        Console.WriteLine(address.Town.Hiragana);       // �������܂����܂Ƃ���
        Console.WriteLine(address.Town.Katakana);       // �I�I�V�}�O�����}�g�\��
        Console.WriteLine(address.City);                // ��ؒ�
        Console.WriteLine(address.City.Kanji);          // ��ؒ�
        Console.WriteLine(address.City.Hiragana);       // ���Ȃ����傤
        Console.WriteLine(address.City.Katakana);       // �C�i�M�`���E

        var prefecture = Gimei.NewPrefecture();
        Console.WriteLine(prefecture); // �X��
    }
}
```
## Notes

* [Default data](https://github.com/matarillo/dot-gimei/tree/master/data) is embedded into the DLL.
* If you want to replace the default data into custom one, use [Generator](https://github.com/matarillo/dot-gimei/blob/8bfb595576b61c6c30ea1a686346f9a170b7400b/DotGimei/Gimei.cs#L118) class.
* Now [Name](https://github.com/matarillo/dot-gimei/blob/master/DotGimei/Name.cs) class has a property `Gender` which type is [GenderIdentity](https://github.com/matarillo/dot-gimei/blob/master/DotGimei/GenderIdentity.cs).

## License
MIT

## Author
INOMATA Kentaro (@matarillo)
