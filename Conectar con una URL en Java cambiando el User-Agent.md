# Conectar con una URL en Java cambiando el User-Agent
## Java 
### URL: https://www.jesusninoc.com/2012/10/01/conectar-con-una-url-en-java-cambiando-el-user-agent/
```Java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.URL;
import java.net.URLConnection;

public class UserAgent
{
	public static void main(String[] args) throws IOException
	{
		URL url = new URL("http://www.jesusninoc.com");
		String inputLine;
		
		URLConnection hc = url.openConnection();
		hc.setRequestProperty("User-Agent", "Mozilla/5.0 (Macintosh; U; Intel Mac OS X 10.4; en-US; rv:1.9.2.2)");
		BufferedReader br = new BufferedReader(new InputStreamReader(hc.getInputStream()));
		while ((inputLine = br.readLine()) != null)
		{
			System.out.println(inputLine);
		}
		br.close();
	}
}

```
