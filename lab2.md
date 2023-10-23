Part1
code of ```StringServer```
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    ArrayList<String> lis=new ArrayList<String>();
        String result="";
        int num=1;
    public String handleRequest(URI url) {
        if (url.getPath().contains("/add")) {
                String[] word = url.getQuery().split("=");
                    result=result+String.format("%d. "+word[1]+"\n",num);
                    num+=1;
                    }
                    return result;
                }
            }


class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }
}
```
screenshots of ```/add-message?s=Hello```
