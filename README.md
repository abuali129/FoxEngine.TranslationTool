v0.2.6.ffnt.mod

FfntTool Modded

Used v0.2.6 as a base to allow negative values of HorizontalSpace & HorizontalShift read and write for .ffnt
+ Unknown2 in GlyphMap.cs is refer to CharacterSpacing, play with this value to find your sweet spot of Character Spacing.

should be work on both, GZ & TPP.

SubpTool & LangTool untouched


Original Readme below
-----------
# FoxEngine.TranslationTool
A bundle of tools related to text editing Fox Engine / MGSV Ground Zeroes files.

This bundle contains the following tools:

Name      | Description
--------- | ------------
FfntTool  | Font unpacker/repacker
LangTool  | String table unpacker/repacker
SubpTool  | Subtitle unpacker/repacker


## Requirements
```
Microsoft .NET Framework 4.5
```

## Remarks
Repacking might lead to crashes or endless loading times with the current version. This is due to not every value being saved in the xml file.


## FfntTool
A Fox Engine bitmap font (.ffnt) unpacker and repacker.

### Usage
```
FfntTool file_path [output_path]
```

### Examples

Unpacking a font file. This will create the file called *KanjiFont.ffnt.xml* and a folder called *KanjiFont*. The font bitmaps will be exported as png files to the *KanjiFont* folder. Each layer of the bitmap font is exported as a single black and white png image.
```
FfntTool KanjiFont.ffnt
```

Repacking a font file. This will create the file called *KanjiFont.ffnt*. The bitmap font layers will be read and merged. Only pixels with the color white will be included in the resulting font.
```
FfntTool KanjiFont.ffnt.xml
```

## LangTool
A Fox Engine localizable string table (.lng) unpacker and repacker.

### Usage
```
LangTool file_path [output_path]
```

### Examples

Unpacking an .lng file. This will create the file *gz_menu.lng#eng.xml*.
```
LangTool gz_menu.lng#eng
```

Repacking an .lng file. This will create the file *gz_menu.lng#eng*
```
LangTool gz_menu.lng#eng.xml
```

## SubpTool
A Fox Engine subtitle pack unpacker and repacker.

### Usage
```
SubpTool [options] file_path [output_path]
```

### Options
The language of the file may be specified to correctly decode certain subtitles. Not specifying a language option will default to the ISO-8859-1 (Latin 1) encoding.

Option | Language   | Encoding
------ | ---------- | --------
-eng   | English    | ISO-8859-1
-fre   | French     | ISO-8859-1
-ger   | German     | ISO-8859-1
-ita   | Italian    | ISO-8859-1
-spa   | Spanish    | ISO-8859-1
-rus   | Russian    | ISO-8859-5
-ara   | Arabic     | UTF-8
-jpn   | Japanese   | UTF-8
-por   | Portuguese | UTF-8

### Examples

Unpacking a subtitle package.
```
SubpTool common.subp
```

Unpacking an encoded subtitle package.
```
SubpTool -jpn JpnText\common.subp
```

Repacking a subtitle package.
```
SubpTool common.subp.xml
```
