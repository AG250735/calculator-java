Zadatak 1

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

--------------------------------------------------------------------------------------------------------------------------------------------------- 

Zadatak 2

TEST-RESULTS
Black-box testiranje kalkulatora

Ulaz: 4+5 → Očekivani rezultat: 9.0 → Status: OK

Ulaz: 10+5*4+3 → Očekivani rezultat: 33.0 → Status: OK

Ulaz: 10/0 → Očekivani rezultat: Infinity ili ERROR → Status: POTENCIJALNI PROBLEM: deljenje nulom nije obrađeno

Ulaz: 5++2 → Očekivani rezultat: ERROR → Status: OK (nevalidan izraz)

Ulaz: 3*2-1 → Očekivani rezultat: 5.0 → Status: OK

Ulaz: 2+3* → Očekivani rezultat: ERROR → Status: OK (nevalidan izraz)

Ulaz: -5+3 → Očekivani rezultat: -2.0 → Status: OK (negativni brojevi podržani)

Ulaz: 4.5+2.3 → Očekivani rezultat: 6.8 → Status: OK (Float preciznost)

Ulaz: (2+3)*4 → Očekivani rezultat: ERROR → Status: POTENCIJALNI PROBLEM: zagrade nisu podržane

Ulaz: 2 + 3 → Očekivani rezultat: 5.0 → Status: OK

Jedinični test metode Calculate (JUnit)

import static org.junit.Assert.assertEquals;
import org.junit.Test;
import java.util.Arrays;
import java.util.List;

public class CalculatorTest {

    @Test
    public void testCalculate() {
        // Test sa jednostavnim izrazom
        List<Float> numbers1 = Arrays.asList(4f, 5f);
        List<String> ops1 = Arrays.asList("+");
        Calculator.Calculate(numbers1, ops1);
        assertEquals(9f, Calculator.finalResult, 0.001);

        // Test sa složenim izrazom (10+5*4+3)
        List<Float> numbers2 = Arrays.asList(10f, 5f, 4f, 3f);
        List<String> ops2 = Arrays.asList("+", "*", "+");
        Calculator.Calculate(numbers2, ops2);
        assertEquals(33f, Calculator.finalResult, 0.001);
    }
}


Zapažanja

Kalkulator ne podržava zagrade, što može izazvati grešku pri unosu izraza sa ().

Float preciznost može dovesti do malih odstupanja pri decimalnim računanjima.

Deljenje nulom vraća Infinity umesto da prijavi grešku.

Nepotpuni ili nevalidni izrazi vraćaju "ERROR", što je prihvatljivo za black-box testiranje.
