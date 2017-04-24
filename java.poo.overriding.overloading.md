## surchage et redéfinition

```bash
public class A {

    public void x(int i) {
    }

    public void y(int i) {
    }
}

public class B extends A {

    public void x(int i) { // redéfinition de la méthode x(int)
        super.x(int i);
        //.....
    }

    public void y(double d) { // surcharge de la méthode y
    }
}
```


* La redéfinition d’une méthode héritée doit impérativement conserver la déclaration de la méthode parent (type et nombre de paramètres, la valeur de retour et les exceptions propagées doivent être identiques).


* Si la signature de la méthode change, ce n’est plus une redéfinition mais une surcharge. Cette nouvelle méthode n’est pas héritée : la classe mère ne possède pas de méthode possédant cette signature .