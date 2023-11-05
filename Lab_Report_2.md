# Lab Report 2 - Part 1
Code for *StringServer.java*
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.List;
import java.net.URLDecoder;

class StringHandler implements URLHandler 
{
    List<String> stringList = new ArrayList<>();
    int lineNumber = 1;

    public String handleRequest(URI url) 
    {
        if (url.getPath().equals("/add-message")) 
        {
            String[] parameters = url.getQuery().split("=");
            if (parameters.length == 2 && parameters[0].equals("s")) 
            {
                try 
                {
                    // decode the string correctly to handle spaces and special characters
                    String stringToAdd = URLDecoder.decode(parameters[1], "UTF-8");
                    String formattedMessage = lineNumber + ". " + stringToAdd;
                    stringList.add(formattedMessage);
                    lineNumber++;
                } 
                catch (Exception errorMsg) 
                { return "Error decoding string"; }
            }
        }
        return String.join("\n", stringList);
    }
}
public class StringServer 
{
    public static void main(String[] args) throws IOException 
    {
        if (args.length == 0) 
        {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
        int port = Integer.parseInt(args[0]);
        Server.start(port, new StringHandler());
    }
}
```
## Screenshots of using `/add-message`
![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/91d8f37e-085a-4383-b55b-dca9c107a1cd)
- Method Called: `handleRequest(URI url)`
- Arguments: URI url with path `/add-message?s=Hello`
- Relevant Fields:
   - `stringList` is an ArrayList initially empty.
   - `lineNumber` is an integer initially set to 1.
- Behavior:
  1. The request URL is parsed, and it is found to have the path `/add-message`.
  2. The query parameter `s` is extracted, which is "Hello".
  3. The `URLDecoder.decode` method is used to decode the string correctly.
  4. The formatted message is created as "1. Hello".
  5. This formatted message is added to `stringList`, which now contains one element.
  6. The `lineNumber` is incremented to 2.
  7. The response will be `1. Hello`.

![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/cecacc30-ad33-419a-9e3a-f258ce17b6b6)
- Method Called: `handleRequest(URI url)`
- Arguments: URI url with path `/add-message?s=How%20are%20you`
- Relevant Fields:
   - `stringList` is an ArrayList with one element "1. Hello".
   - `lineNumber` is an integer with the value 2.
- Behavior:
  1. The request URL is parsed, and it is found to have the path `/add-message`.
  2. The query parameter `s` is extracted, which is "How%20are%20you".
  3. The `URLDecoder.decode` method is used to decode the message, resulting in "How are you."
  4. The formatted message is created as "2. How are you".
  5. This formatted message is added to `stringList`, which now contains two elements.
  6. The `lineNumber` is incremented to 3.
  7. The response will be:
     ```
     1. Hello
     2. How are you
     ```
  8. The relevant fields in this case, `stringList` and `lineNumber`, have changed to reflect the added string and updated lineNumber in response to the requests.

# Part 2
Using the command line, show with `ls` and take screenshots of:
1. The path to the private key for your SSH key for logging into ieng6 (on your computer or on the home directory of the lab computer)

    ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/c3bd8d4b-4abf-47ca-bdde-9923de36d256)

2. The path to the public key for your SSH key for logging into ieng6 (within your account on ieng6)

    ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/8ba879f7-33ab-4ce5-8f18-c79e5e96dec7)

3. A terminal interaction where you log into ieng6 with your course-specific account without being asked for a password.

    ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/78a3bf00-aa43-4a76-9beb-1a3e2a12a45c)

# Part 3
From week 3's lab, I learned how to set up SSH keys for secure and passwordless access to my remote course-specific account on ieng6. I generated an SSH key pair using the ssh-keygen command, copied the public key to the remote server, and configured it to allow me to log in without entering my password each time, enhancing both security and convenience. Additionally, I was introduced to two essential commands, ssh-keygen for key generation and scp for secure file copying between local and remote machines.
