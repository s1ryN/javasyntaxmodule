# javasyntaxmodule
⚫ Balíky a moduly

Rozsáhlejší programy obsahují velké množství tříd. Java seskupuje programy do balíků (package) a počínaje JDK 9 také do modulů (module).

 

Balík = skupina tříd

V Javě platí, že všechny třídy, které patří do jednoho balíku, musí ležet ve stejném adresáři a tento adresář se musí jmenovat stejně jako balík. 

 

⚫ Příklad 1: jedna třída, jeden balík

 

/* Třída v Javě = soubor Main.java */

/*@version 1.001*/

/*@author Lenka*/

package balik;

 

/**Třída Trida má za úkol vypsat <B>Ahoj lidi!</B>. 

Je to jediná třída v našem programu a nemá žádný skutečný smysl.

*/

public class Main {

/**Jediná metoda <I> prvnitrida obsahuje všechnu funkcionalitu 

* programu </I>.

@param args Parametry příkazové řádky programu

*/

 

    public static void main(String[] args)

    {

        System.out.println("Ahoj lidi!");

   

   }

 


 

⚫ Příklad 2: dvě třídy, jeden balík

Celé jméno třídy se pak skládá ze jména balíku, k němuž je tečkou připojeno jméno třídy.

 

/* První třída v Javě = soubor PrvniTrida.java */

/*@version 1.001*/

/*@author Lenka*/

package pozdrav;        

 

/**Třída PrvniTrida má za úkol vypsat <B>Ahoj lidi!</B>. 

Je to jediná třída v našem programu a nemá žádný skutečný smysl.

*/

public class PrvniTrida {

/**Jediná metoda <I> prvnitrida obsahuje všechnu funkcionalitu 

* programu </I>.

@param args Parametry příkazové řádky programu

*/

 

    public static void prvnitrida()

    {

        System.out.println("Ahoj lidi!");

    }

}

Celé jméno třídy je pozdrav.PrvniTrida

Celé jméno třídy níže je pozdrav.Main

/* Druhá třída v Javě = soubor Main.java */

/*@version 1.001*/

/*@author Lenka*/

package pozdrav;     

 

/**Třída pozdrav.Main má za úkol spustit <B>pozdrav.PrvniTrida.prvnitrida() </B>. 

Je to jediná třída v našem programu.

*/

public class Main {

/**Jediná metoda <I> obsahuje všechnu funkcionalitu 

* programu </I>.

@param args Parametry příkazové řádky programu

*/

 

    public static void main(String[] args)

    {

        pozdrav.PrvniTrida.prvnitrida();

    }

}



 

 

⚫ Příklad 3: dvě třídy, dva balíky

Celé jméno třídy se pak skládá ze jména balíku, k němuž je tečkou připojeno jméno třídy.

Obsah souboru Ahoj.java:

package program;

public class Ahoj {

    public static void ahoj()

 

    {

        System.out.println("Ahoj studenti VOŠ a SPŠ Křižíkova!");

    }

}

Obsah souboru Main.java:

package pozdrav;

public class Main {

 

    public static void main(String[] args)

    {

        program.Ahoj.ahoj();

    }

}


 

 

 


 

 


 




 

⚫  Moduly

Třídu Main umístíme do balíku program a ten umístíme do do modulu modulpozdrav.

Obsah souboru Main.java:

package program;

public class Main {

    public static void main(String[] arg)

    {

        System.out.println("Nazdar!");

    }

}

Modul musí být v adresáři, jehož jméno se shoduje se jménem tohoto modulu. 

V tomto adresáři musí být uložen soubor module-info.java obsahující deklaraci modulu a podadresáře obsahující jednotlivé balíky, které jsou součástí modulu.

Obsah souboru module-info.java:

 

module modulpozdrav

 {

  exports program;

  }


 

 



 

 

 

 





 

 

⚫  Deklarace balíku a OOP (objektově orientované programování) = příklad 4: jeden balík a dvě třídy

/* První třída v Javě = soubor PrvniTrida.java */

/*@version 1.001*/

/*@author Lenka*/

package pozdrav;        

 

/**Třída PrvniTrida má za úkol vypsat <B>Ahoj lidi!</B>. 

Je to jediná třída v našem programu a nemá žádný skutečný smysl.

*/

public class PrvniTrida {

/**Jediná metoda <I> prvnitrida obsahuje všechnu funkcionalitu 

* programu </I>.

@param args Parametry příkazové řádky programu

*/

 

    public static void prvnitrida()

    {

        System.out.println("Ahoj lidi!");

    }

}

 

 

Celé jméno třídy je pozdrav.PrvniTrida

Celé jméno třídy níže je pozdrav.Main

Ve třídách uvnitř téhož balíku pozdrav můžeme kvalifikaci pozdrav vynechat.

/* Druhá třída v Javě = soubor Main.java */

/*@version 1.001*/

/*@author Lenka*/

package pozdrav;     

 

/**Třída pozdrav.Main má za úkol spustit <B>pozdrav.PrvniTrida.prvnitrida() </B>. 

Je to jediná třída v našem programu.

*/

public class Main {

/**Jediná metoda <I> obsahuje všechnu funkcionalitu 

* programu </I>.

@param args Parametry příkazové řádky programu

*/

 

    public static void main(String[] args)

    {

            PrvniTrida zdravim = new PrvniTrida();

            zdravim.prvnitrida();

    }

}





⚫  Příkaz import

Jména tříd s kvalifikací jménem balíku mohou být dlouhá, proto můžeme použít příkaz import a jméno balíku vynechat. Import balíku neznamená import všech jeho podbalíků.

 

import jmeno_baliku.jmeno_tridy;

import jmeno_baliku.*;

Do balíku java.lang patří například třídy String a Objekt. Překladač se vždy chová tak, jako by na počátku každého zdrojového programu byl příkaz:

import java.lang.*;

Když příkaz package neuvedeme, umístí překladač třídy do implicitního balíku (nepojmenovaného)

⚫  Statický import

Příkaz statický import umožňuje vynechávat při používání statických složek tříd kvalifikaci jménem třídy.

 

import static jmeno_tridy.jmeno_slozky;

import static jmeno_tridy.*;

Jméno třídy může obsahovat i jméno balíku.

 

Například:

import static java.lang.Math.*;  // stačí napsat import static Math.*;

...

y=sin(x); 

z=sqrt(r);

 

⚫  Struktura modulu

Moduly přinášejí silné zapouzdření (= ukrytí části implementace). 

Nultá úroveň je zapouzdření metody, 

první úroveň je zapouzdření třídy,

druhá úroveň je zapouzdření balíku 

a třetí úroveň je zapouzdření modulu. 

 

Struktura modulu je stejně jako struktura balíku vázána na adresářovou strukturu. Zdrojový kód modulu je obvykle uložen v adresáři stejného jména jako je jméno modulu.

V tomto adresáři je uložen i zdrojový soubor module - info.java. Tento soubor obsahuje deklaraci modulu, deklarace exportů a závislostí. 

Dále obsahuje podadresáře odpovídající jednotlivým balíkům, které modul tvoří.

 

 

 

⚫  Deklarace modulu

open module jmeno_modulu

 

Před klíčovým slovem module může být open, který říká, že daný modul umožňuje neomezený přístup pomocí reflexe.

⚫  Deklarace exportu (direktiva exports)

je jedna z direktiv modulu. Oznamuje, které balíky dává modul k dispozici ostatním částem programu.

 

exports jmeno_baliku;  // balík může používat kdokoliv

exports jmeno_baliku to seznam_modulu;   // balík mohou používat jen moduly vyjmenované v seznamu modulů

 

⚫  Deklarace závislosti ( direktiva requires)

Je to druhá z možných direktiv modulu. Tato deklarace oznamuje, které moduly daný modul potřebuje ke svému fungování.

requires jmeno_modulu;   // modul potřebuje modul určený jménem modulu
requires static jmeno_modulu;    // modul určený jménem modulu je potřeba v době překladu, při běhu je nepovinný
requires transitive jmeno_modulu; // modul potřebuje modul určený jménem modulu a navíc ho zveřejňuje (každý, kdo čte tento modul čte automaticky i modul určený jménem modulu)



⚫  Otevřenost vůči reflexi (specifikace open, direktiva opens)

Uvedeme-li před klíčovým slovem module slovo open, říkáme tím, že ke všem balíkům modulu můžeme přistupovat pomocí reflexe, a to odkudkoliv.

Jestliže chceme možnost použití reflexe omezit pouze na vybrané moduly, použijeme místo toho direktivu:

opens jmeno_baliku; // otevření balíku vůči reflexi pro kohokoliv

opens jmeno_baliku to seznam_modulu; // otevření balíku vůči reflexi pro moduly uvedené v seznamu modulů

seznam_modulu je seznam čárkou oddělených jmen modulů

  

⚫  Využívané služby (direktiva uses)

 

Služba je instance potomka abstraktní třídy nebo rozhraní. 

Pro specifikaci, že modul využívá určitou službu, slouží direktiva uses:

uses abstraktni_trida_nebo_rozhrani;

 

Například:

module java.sql  { 

requires public java.logging;

requires public java.xml;

exports java.sql;

exports javax.sql;

exports javax.transaction.xa;

uses java.sql.Driver; }

 

⚫  Poskytované služby (direktiva provides)

Pro specifikaci, že modul poskytuje určitou službu, slouží direktiva provides:

provides abstraktni_trida_nebo_rozhrani with tridy;

Za slovem provides následuje jméno abstraktní třídy nebo rozhraní, které odpovídá jménu uvedenému v direktivě uses.

Za slovem with následují konkrétní třídy, které implementují ono rozhraní nebo jsou potomkem oné abstraktní třídy (je-li jich více, oddělujeme je čárkou).

 

Například:

module com.mysql.jdbc { 

requires java.sql;

requires org.slf4j;

exports com.mysql.jdbc;

provides java.sql.Driver with com.mysql.jdbc.Driver; }  //com.mysql.jdbc.Diver je třída implementující rozhraní java.sql.Driver

⚫  Standardní moduly

Všechny standardní moduly jsou uloženy v podadresáři jmods adresáře s instalací JDK a jsou zabaleny pod svým jménem do archivů zip, i když mají příponu jmod.

Například: modul java.base je uložen pod jménem java.base.jmod

 

Modul java.base obsahuje například balíky:

java.lang s třídou Object, String, System, ...

java.io s nástroji pro vstup a výstup

java.math pro matematické funkce

 

Modul  java.desktop obsahuje například balíky:

java.awt s nejstarší knihovnou pro tvorbu GUI

javax.swing s novější knihovnou pro tvorbu GUI

javax.imageio pro vstup a výstup obrázků

Není v něm ale knihovna JavaFX pro tvorbu GUI.

 

 

⚫  Příklad 5: program s dvěma moduly

Obsah souboru module-info.java z adresáře modulpozdrav (Nastavíme se na scr modulu a v nabídce File - New vybereme  module-info.java):

module modulpozdrav { 

exports pozdrav;

 }


Obsah souboru Pozdrav.java z adresáře pozdrav (podadresář adresáře modulpozdrav):

package pozdrav;

public class Pozdrav { 

        public static void pozdrav() { 

                   System.out.println ("uctiva poklona");

        }

}


 

Obsah souboru module-info.java z adresáře modulprogram (Nastavíme se na scr modulu a v nabídce File - New vybereme  module-info.java):

module modulprogram { 

         requires modulpozdrav;

 }


Obsah souboru Main.java z adresáře program (podadresář adresáře modulprogram) :

package program;

import pozdrav.*;

public class Main {

    public static void main(String[] args)

            {

                    Pozdrav.pozdrav();

             }

}


 

 

Nejdříve vytvoříme nový projekt:

 


Poté vytvoříme nový modul modulprogram (v nabídce menu File-New-Module...):


 

 

 

A vytvoříme nový modul modulpozdrav (v nabídce menu File-New-Module...):

 


Po přeložení projektu je potřeba ještě upravit nastavení:


A to v nabídce File - Project Structure...



Kde vytvoříme přes ikonu + toto:


Vznikne toto:


A nyní již projekt lze přeložit:



A lze spustit:

