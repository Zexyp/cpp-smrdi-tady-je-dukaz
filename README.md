Nebude to moc formální a budu kašlat na dobrej styl vypravování a na pravopis.

Budu srovnávat c s c++ primárně v oblastech kde c++ hází víc klacků pod nohy než c, ale nedá se říct, že by to bylo fér srovnání.
Pokud se jedná o velkej neembeded projekt, tak je samozřejmě lepší c++ menší zlo než c, ale ve srovnání s rustem c++ stejně dostane na prdel.

Začal bych z lehounka a to u overloadění bitshiftu (<< a >>)
Streamy jsou sice fajn věc, ale když se s nima pracuje přes overloaděný bitshifty, tak z toho vzniká hodně pastí.

    if (!std::cin >> ...)  je jednou z nich, člověk musí myslet na závorky, jinak se mu z toho stanou reálný bitshifty a negace a to pak rapidně mění význam.
    std::cout << A && B ... člověk by doufal, že vytiskne výsledek logickýho andu, ale ani omylem. na cpp referenc je na poměry cpp reference relativně hezky popsanýá operator precedence.
                            jelikož << má větší prioritu než &&, tak se proede std::cout << A a ve 2. kroku se provede && a jelikož ten potřebuje nějaký číslo, tak se ten stream převede na true, pokud neselhal a vyhodnotí se (selhání/neselhání && B) a výsledek je 1 nebo 0.


