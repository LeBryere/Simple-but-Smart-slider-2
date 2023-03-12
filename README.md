# Ecommerce Slider v2.1

<!-- 

// A függvény inicializálja a diavetítőt az átadott elemen (item).
// Kiválasztjuk a diavetítőben található diák elemeket.
// Beállítjuk a kezdő értékeket.
// Létrehozzuk az előző gombot.
// Létrehozzuk a következő gombot.
// Ha több mint 1 dia van, hozzáadjuk a navigációs elemeket az item-hez.
// Beállítjuk az aktuális és előző diákat.
// Az "navigate" függvény megváltoztatja a diákat.
// Ha jobbra megyünk, növeljük a "current" változó értékét.
// Ha balra megyünk, csökkentjük a "current" változó értékét.
// Beállítjuk az aktuális és előző diákat.
// Ha az egér a diavetítőre kerül, kikapcsoljuk az automatikus frissítést.
// Ha az egér a diavetítőről lekerül, visszakapcsoljuk az automatikus frissítést.

// érzékelő eszközökkel történő navigáció
// érintés mozgatása eseménykezelő
// jobbra-balra irányú mozgás észlelése
// balra mozgás esetén jobbra navigálunk
// érintés befejezésekor az x és y értékek nullázása



// "The function initializes the slideshow on the given element (item).
// We select the slide elements in the slideshow.
// We set the initial values.
// We create the previous button.
// We create the next button.
// If there is more than one slide, we add the navigation elements to the item.
// We set the current and previous slides.
// The "navigate" function changes the slides.
// If we go right, we increase the value of the "current" variable.
// If we go left, we decrease the value of the "current" variable.
// We set the current and previous slides.
// If the mouse is over the slideshow, we turn off automatic updates.
// If the mouse leaves the slideshow, we turn automatic updates back on.

// Navigation with sensor devices.
// Event handler for touch movement.
// Detect right-left movements.
// If we move left, we navigate right.
// Resetting x and y values when touch is finished."


Az általános funkciója ennek a kódnak az, hogy egy olyan képeslap effektet hoz létre, amelyben egy lista elemei között lehet lapozni, vagy a rendszer automatikusan halad a listán. A kód az alábbiakat tartalmazza:

* A lista elemeket kiválasztja és eltárolja az "items" változóban.
* Az aktuális elem indexét az "current" változó tárolja.
* Az "autoUpdate" változó azt jelzi, hogy a rendszer automatikusan lapoz-e, vagy sem.
* Az "timeTrans" változó azt az időt tárolja, amelyet az automatikus lapozás végrehajtásához használnak.
* A kódban előállít egy "nav" elemet, amely tartalmazza a navigációs nyilakat, a számlálót, az előző gombot és a következő gombot.
* A "counter" elem a lista elemek számát és a jelenlegi elem indexét jeleníti meg.
* Az "items" listaelemeknek megfelelően a megfelelő osztályneveket rendeli hozzájuk a rendszer.
* Az "autoUpdate" változót akkor állítja be, hogy a rendszer automatikusan lapozzon-e, vagy sem, ha az egérrel belépünk vagy kilépünk a képeslapról.
* A "navigate" függvény az előző vagy a következő elemre navigál, és frissíti a számlálót a jelenlegi elem indexével.
* Az előző és a következő gombra való kattintás esetén az "navigate" függvényt hívja meg.
* Az "items" listaelemekre történő kattintásra vagy az előző/következő gombokra történő kattintáson kívül a billentyűzet balra és jobbra nyilai is használhatók a navigációhoz.
* Az "item" elemre való érintéssel az érintőképernyős navigáció támogatása van beállítva, ahol a képernyőn történő balra vagy jobbra húzással lehet navigálni az elemeken.
* A kód minden ".cd-slider" osztályú elemen meghívja az "init" függvényt, amely elindítja az összes funkciót.

Összességében a kód egyszerű, de hatékony módja annak, hogy interaktívabbá tegye az oldalakat és felkeltse a látogatók figyelmét.


A függvénydefiníció kezdetén egy init() függvényt definiálunk, amely egy item paramétert vár. A függvény először kiválasztja az összes li elemet az item-en belül, majd beállít néhány változót. Ezek közé tartozik a current változó, amely az aktuális diát tartalmazza, az autoUpdate változó, amely igaz értéket tartalmaz, ha az automatikus frissítés engedélyezett, és egy timeTrans változó, amely az automatikus frissítés időközét határozza meg.

Ezután létrehozunk egy navigációs menüt, amely tartalmaz két gombot (prevbtn, nextbtn) és egy számlálót (counter). A menüt hozzáadjuk az item-hez, ha több, mint egy elem van. Az aktuális diát beállítjuk current osztályként, és ha több, mint egy elem van, akkor az utolsó elemet beállítjuk prev_slide osztályként.

Ezután egy navigate() függvényt definiálunk, amely a megadott irány szerinti navigációt végrehajtja. Az aktuális dia current osztályát eltávolítjuk, majd a következő vagy előző diát határozzuk meg az irány függvényében. Ezután a megfelelő osztályokat állítjuk be az elemeknek, és frissítjük a számlálót.

Ezután hozzáadjuk az eseménykezelőket. Az item-hez hozzáadjuk az mouseenter és az mouseleave eseménykezelőket, hogy az automatikus frissítés leálljon, amikor az egér belép az elembe, és újrainduljon, amikor az egér elhagyja az elemet. Az autoUpdate változó alapértelmezés szerint igaz, és ha az automatikus frissítés engedélyezve van, akkor a setInterval() függvénnyel beállítjuk az időzítőt, amely a megadott időközönként meghívja a navigate() függvényt.

Hozzáadjuk a prevbtn és nextbtn gombok eseménykezelőit, amelyek a megfelelő irányba hajtanak végre navigációt. Hozzáadjuk a billentyűzetkezelő eseménykezelőt, amely lehetővé teszi a felhasználó számára, hogy a bal és jobb nyilak használatával navigáljon. Végül hozzáadjuk az érintéskezelő eseménykezelőket 

Ezután a kódrészletben meghatározzuk a navigate függvényt, amely a navigációért felelős. A függvény a paraméterként kapott dir változó értékének függvényében dönti el, hogy balra vagy jobbra kell-e lapozni. A current változó értékét is ennek megfelelően frissíti. Az items lista elemeinek megfelelően beállítja a className értékeit, és frissíti a számláló értékét.

Ezután az egérmozgásra és érintőképernyős eseményekre vonatkozó eseménykezelőket adunk hozzá. Az item elemre rámutatva az autoUpdate változó értékét false-ra állítjuk, így az automatikus lapozás leáll. Az egérmutató eltávolításakor az autoUpdate értéke visszaáll true-ra, és az automatikus lapozás folytatódik.

Ezután az automatikus lapozásért felelős időzítőt állítjuk be, amely a timeTrans változó értékének megfelelően navigál a diák között. A prevbtn és nextbtn gombokra kattintva a navigate függvényt hívjuk meg, és a billentyűzetről történő navigációt is kezeljük.

Végül hozzáadunk eseménykezelőket az érintőképernyős eszközökhöz, amelyek a balra és jobbra húzásra reagálnak, és megfelelően navigálnak a diák között.

Végül a függvény az összes cd-slider osztályú elemre hívja meg az init függvényt, hogy inicializálja a diavetítőt az összes megfelelő elemen.




The general function of this code is to create a postcard effect in which the elements of a list can be navigated by paging or the system automatically advances through the list. The code includes the following:

* Selects and stores the list elements in the "items" variable.
* Stores the current element index in the "current" variable.
* The "autoUpdate" variable indicates whether the system pages automatically or not.
* The "timeTrans" variable stores the time used to perform automatic paging.
* Generates a "nav" element in the code that contains navigation arrows, a counter, a previous button, and a next button.
* The "counter" element displays the number of list items and the current element index.
* Assigns the appropriate class names to the list elements corresponding to the "items".
* Sets the "autoUpdate" variable to automatically page or not when the mouse enters or exits the postcard.
* The "navigate" function navigates to the previous or next element and updates the counter with the current element index.
* Calls the "navigate" function when clicking the previous or next button.
* In addition to clicking on list items or previous/next buttons, the left and right arrow keys on the keyboard can also be used for navigation.
* Touch support is set for the "item" element, where swiping left or right on the screen navigates through the elements.
* The code calls the "init" function on every element with the ".cd-slider" class, which initiates all functions.

Overall, the code is a simple but effective way to make pages more interactive and catch visitors' attention.


At the beginning of the function definition, we define an init() function that expects an item parameter. The function first selects all li elements within the item and sets some variables. These include the current variable that contains the current slide, the autoUpdate variable that holds a true value if automatic update is enabled, and a timeTrans variable that determines the interval for automatic update.

Next, we create a navigation menu that contains two buttons (prevbtn, nextbtn) and a counter. We add the menu to the item if there is more than one element. We set the current slide as the current class, and if there is more than one element, we set the last element as the prev_slide class.

Then, we define a navigate() function that performs navigation in the specified direction. We remove the current class of the current slide and determine the next or previous slide depending on the direction. Then, we set the appropriate classes for the elements and update the counter.

Next, we add the event handlers. We add the mouseenter and mouseleave event handlers to the item to stop automatic update when the mouse enters the element and restart it when the mouse leaves the element. The autoUpdate variable is true by default, and if automatic update is enabled, we set the timer with the setInterval() function, which calls the navigate() function at the specified interval.

We add event handlers for the prevbtn and nextbtn buttons, which perform navigation in the appropriate direction. We add a keyboard event handler that allows the user to navigate using the left and right arrows. Finally, we add touch event handlers.

Then, in the code snippet, we define the navigate function that is responsible for navigation. The function decides whether to flip left or right based on the value of the dir variable passed as a parameter. It also updates the value of the current variable accordingly. It sets the className values of the items in the list appropriately and updates the counter value.

Next, we add event handlers for mouse movement and touch screen events. When pointing to the item element, we set the value of the autoUpdate variable to false, so automatic flipping stops. When the cursor is removed, the autoUpdate value returns to true, and automatic flipping continues.

Then, we set up the timer responsible for automatic flipping, which navigates between slides according to the value of the timeTrans variable. When clicking on the prevbtn and nextbtn buttons, we call the navigate function, and we also handle navigation from the keyboard.

Finally, we add event handlers for touch screen devices, which respond to swiping left and right and navigate between slides accordingly.

Finally, the function calls the init function for all elements with the cd-slider class to initialize the slideshow on all appropriate elements.


 -->