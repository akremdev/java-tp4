# java-tp4

`Classe Maison : `

```java
package personne;
import java.io.*;
public class maison implements Serializable{
public String adresse;
public maison(String adresse) {
this.adresse = adresse;
System.out.println("Creation maison ");
}
public String getAdresse(){ return adresse;}
public String toString(){ return " la maison est a l adresse: " +
adresse;
}
}

```
`Classe Ecriture OBJET : `

```java
package personne;
import java.io.*;
public class EcritureObjet {
public static void main(String[] args) {
maison m1 = new maison("Gabess");
maison m2 = new maison("Sousse");
maison m3 = new maison("Tunis");
ObjectOutputStream fo;try { fo = new ObjectOutputStream(new
FileOutputStream("c:/test/fObjet.data"));
fo.writeObject(m1);
fo.writeObject(m2);
fo.writeObject(m3);
fo.close(); }
catch (FileNotFoundException e) { e.printStackTrace(); }
catch (IOException e) { e.printStackTrace();
}
try { ObjectInputStream fol = new ObjectInputStream(new
FileInputStream("c:/test/fObjet.data"));
maison m4= (maison) fol.readObject();
maison m5= (maison) fol.readObject();
maison m6= (maison) fol.readObject();
System.out.println(m4 );
System.out.println(m5 );
System.out.println(m6 );
fol.close();
} catch (FileNotFoundException e) {
e.printStackTrace();
} catch (IOException e) {
e.printStackTrace();
} catch (ClassNotFoundException e) {
e.printStackTrace();
}}
}
```
