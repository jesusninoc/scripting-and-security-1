# Ejemplos de ejecución de comandos en Bash y PowerShell (parte 2)
## Bash, Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2008/09/30/ejemplos-de-ejecucion-de-comandos-en-bash-y-powershell-parte-2/
```Shell
echo 'hola:adios' | cut -d ':' -f1

```
```PowerShell
('hola:adios').Split(':')[0]

echo 'hola:adios' | %{$_.split(':')[0]}

```
```Shell
echo 'hola/adios' | tr '/' '\\'

```
```PowerShell
('hola/adios').replace('/','\\')

echo 'hola/adios' | %{$_ -replace '/', '\'}

```
