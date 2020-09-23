<div align="center">

## Html tag stripper


</div>

### Description

reads in a Html file, removes the tags and sends the output to an output.txt file
 
### More Info
 
a Html file

only works on JSDK 1.4 and above

a text file


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[John Hunsley](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/john-hunsley.md)
**Level**          |Beginner
**User Rating**    |4.0 (20 globes from 5 users)
**Compatibility**  |Java \(JDK 1\.2\)
**Category**       |[String Manipulation](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/string-manipulation__2-60.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/john-hunsley-html-tag-stripper__2-3443/archive/master.zip)





### Source Code

```
/*
 *this program reads in a text file,
 *puts a carrage return in at the end of
 *each sentance. then sends that it to
 *an output text file
 *@author John Hunsley
 *@version 1.0 25/02/03
 *
*/
import java.util.*;
import java.io.*;
class HtmlStripper
{
	public static void main(String args[])
	{
		StringBuffer fileAsStringBuffer = new StringBuffer();//string buffer for file input
		String fileAsString = "intialized";//the file as a string
		/*****************read the whole file into a StringBuffer, line by line********************/
		try{
			BufferedReader input = new BufferedReader(
									 new FileReader("text.txt"));
			String line;
			while((line = input.readLine()) != null)
			{
				fileAsStringBuffer.append(line);
			}
			input.close();//close the buffer
			System.out.println("file saved as string");
			fileAsString = fileAsStringBuffer.toString();//set the String in the buffer as a String
		}
		catch(IOException e){
			System.out.println("IO Exception occured");
		}
/************strip tags******************/
fileAsString = fileAsString.replaceAll("\\<.*?\\>","");//strips all html tags
//write the String out to a text file
		try{
			File file = new File("output.txt");
			PrintWriter output = new PrintWriter(new FileWriter(file));
			output.println(fileAsString);
			output.close();
			System.out.println("String written to output text file");
			JOptionPane.showMessageDialog(null,
							 "String written to output text file");
		}
		catch(IOException e){
			System.out.println("IO Exception occured");
		}
}
```

