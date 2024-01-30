# Part 1

## ChatServer

```
{
import com.sun.net.httpserver.HttpExchange;

import java.io.IOException;
import java.net.URI;

class ChatHandler implements URLHandler {
    private StringBuilder chatMessages = new StringBuilder();

    public String handleRequest(URI url) {
        String path = url.getPath();

        if (path.startsWith("/add-message")) {
            String[] parameters = url.getQuery().split("&");

            String user = null;
            String message = null;

            for (String parameter : parameters) {
                String[] keyValue = parameter.split("=");
                if (keyValue.length == 2) {
                    if (keyValue[0].equals("user")) {
                        user = keyValue[1];
                    } else if (keyValue[0].equals("s")) {
                        message = keyValue[1];
                    }
                }
            }

            if (user != null && message != null) {
                String newMessage = user + ": " + message + "\n";
                chatMessages.append(newMessage);
                return chatMessages.toString();
            }
        }

        return "Invalid request";
    }
}

public class ChatServer {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new ChatHandler());
    }
}

} 
```



