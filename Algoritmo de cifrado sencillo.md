# Algoritmo de cifrado sencillo
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2016/03/06/algoritmo-de-cifrado-sencillo-2/
```PowerShell
$text="abcdefghij abcd"
$var=8
(0..($text.Length-1) | % {[char]::ConvertFromUtf32([char]::ConvertToUtf32($text[$_].ToString(),0)+$var)}) -join ""

```
# Algoritmo de cifrado sencillo
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/02/11/algoritmo-de-cifrado-sencillo/
```PowerShell
$text="abcdefghij abcd"
$e=""

foreach ($line in $text) {
$n=""
$n+= foreach ($word in ($line.Split()))
{
$chars = for ($i=0;$i -lt $word.length;$i++)
{
$x=$word[$i]
$x=[char]::ConvertToUtf32("$x",0)
[int]$y=$x+8
[char]::ConvertFromUtf32($y)
}
$chars -join ""
}
$e+=$n
}
$e

```
