﻿
Moving https://bitbucket.org/DimaStefantsov/unidecodesharpfork project to GitHub (Dima no longer works with .NET).
Also the goal is to port it to .net core

# Purpose
It often happens that you have text data in Unicode, but you need to represent it in ASCII. For example when integrating with legacy code that doesn’t support Unicode, or for ease of entry of non-Roman names on a US keyboard, or when constructing ASCII machine identifiers from human-readable Unicode strings that should still be somewhat intelligible (a popular example of this is when making an URL slug from an article title).

# Overview

**Unidecode.NET** is .NET library dll, written in C#.
It provides string or char extension method Unidecode() that returns transliterated string. It supports huge amount of languages.
And it's very easy to add your language if it's not supported already!

# Installation
Unicode.NET published as NuGet package: https://www.nuget.org/packages/Unidecode.NET/

To install Unidecode.NET, run the following command in the [Package Manager Console](https://docs.nuget.org/consume/package-manager-console)

`Install-Package Unidecode.NET`

#Example code

Take a look at the list of assertions:
```cs
Assert.AreEqual("Bei Jing ", "\u5317\u4EB0".Unidecode());
Assert.AreEqual("Rabota s kirillitsey", "Работа с кириллицей".Unidecode());
Assert.AreEqual("aouoAOUO", "äöűőÄÖŨŐ".Unidecode());
Assert.AreEqual("Hello, World!", "Hello, World!".Unidecode());
Assert.AreEqual("'\"\r\n", "'\"\r\n".Unidecode());
Assert.AreEqual("CZSczs", "ČŽŠčžš".Unidecode());
Assert.AreEqual("a", "ア".Unidecode());
Assert.AreEqual("a", "α".Unidecode());
Assert.AreEqual("a", "а".Unidecode());
Assert.AreEqual("chateau", "ch\u00e2teau".Unidecode());
Assert.AreEqual("vinedos", "vi\u00f1edos".Unidecode());
```
