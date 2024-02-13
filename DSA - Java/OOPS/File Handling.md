[Video Link](https://youtu.be/nqB3qAtDLKU?si=PFYO3kmbonnZIYAU&t=12072)
Next Topic [[]]

This notes is about Reading and writing a file 
### Reading from file
- This is similar to scanner class , we need to import File class 
- We need to create an object with passing path name as parameter for constructor
```Java
import java.io.FileNotFoundException;  
import java.util.Scanner;  
import java.io.File;  
  
public class Solution {  
    public static void main(String[] args) throws FileNotFoundException {  
        File myFile = new File("example.txt");  
        try{  
            Scanner reader = new Scanner(myFile);  
            while(reader.hasNextLine()){  
                System.out.println(reader.nextLine());  
            }  
        }catch(Exception E){  
            System.out.println(E);  
        }  
    }  
}
```

### Writing a file
```Java
import java.io.FileNotFoundException;  
import java.io.File;  
import java.io.FileWriter;  
  
public class Solution {  
    public static void main(String[] args) throws FileNotFoundException {  
        try{  
            File myFile = new File("example.txt");  
            FileWriter writer = new FileWriter(myFile);  
            writer.write("File was written");  //Incase if we gave an number , it's respective ASCII Value will be stored
            writer.close();  // Good practice to close the file
        }catch(Exception E){  
            System.out.println(E);  
        }  
    }  
}
```

After execution , ![[Pasted image 20240213125111.png]]

