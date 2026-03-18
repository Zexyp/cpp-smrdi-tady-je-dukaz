# CPP smrdí, tady je důkaz

Nebude to moc formální a budu kašlat na dobrej styl vypravování a na pravopis.

Budu srovnávat C s C++ primárně v oblastech, kde C++ hází víc klacků pod nohy než C, ale nedá se říct, že by to bylo fér srovnání.
Pokud se jedná o velkej neembeded projekt, tak je samozřejmě C++ menší zlo než C, ale ve srovnání s Rustem C++ stejně dostane na prdel.

Začal bych zlehounka, a to u overloadění bitshiftu (`<<` a `>>`)
Streamy jsou sice fajn věc, ale když se s nima pracuje přes overloaděný bitshifty, tak z toho vzniká hodně pastí.

Následující konstrukce je jednou z nich, člověk musí myslet na závorky, jinak se mu z toho stanou reálný bitshifty a negace a to pak rapidně mění význam.
```cpp
if (!std::cin >> ...)
```

Člověk by doufal, že vytiskne výsledek logickýho andu, ale ani omylem. Na cpp reference je na poměry cpp reference relativně hezky popsanýá operator precedence.
```cpp
std::cout << A && B ...
```
Jelikož `<<` má větší prioritu než `&&`, tak se provede `std::cout << A` a ve 2. kroku se provede `&&` a jelikož ten potřebuje nějaký číslo, tak se ten stream převede na `true`, pokud neselhal a vyhodnotí se (selhání/neselhání `&&` B) a výsledek je `1` nebo `0`.


