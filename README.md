Calculator Java – Staticka analiza i LOC

Fajl: Calculator.java

Broj linija koda (LOC): 57

Ciklomatska složenost metode evaluateExpression: 7

Kognitivna složenost metode evaluateExpression: 6

Ciklomatska složenost metode Calculate: 11

Kognitivna složenost metode Calculate: 8

Zapažanja:

Metoda evaluateExpression je dobro strukturisana i dokumentovana, ali bi mogla da se podeli na manje metode radi bolje čitljivosti i održivosti.

Metoda Calculate ima visoku složenost, što sugeriše potrebu za refaktorisanje radi poboljšanja jasnoće i performansi.

Klasa Operations je imenovana u jednini, ali možda bi bilo primerenije koristiti množinu.

Korišćenje Float može dovesti do grešaka u preciznosti u izračunavanjima.

Nedostaje obrada grešaka za nevalidne ulazne izraze.
