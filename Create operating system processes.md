# Create operating system processes
## Java, Processes 
### URL: https://www.jesusninoc.com/2012/08/29/create-operating-system-processes/
```Java
import java.io.IOException;

public class Proceso
{
	public static void main(String[] args) throws IOException
	{
		ProcessBuilder pb = new ProcessBuilder("notepad");
		pb.start();
	}
}

```
