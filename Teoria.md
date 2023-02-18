# Lekcja 1

## Grupy poleceń jężyka:

- DML (Data Manipulation Languge) - ta grupa służy do wykonywania zapytań. Korzystamy z niej do wydobywania danych z bazy danych.
- DDL (Data Definition Languge) - ta grupa służy do dodawania nowych [krotek](./Definicje.md###Krotka)
- DCL (Data Control Languge) - ta grupa służy do towrzenia [tablic](./Definicje.md###Tablica).

Każde polecenie SQL kończymy ';'

## Typy atrybutów
(Język SQL ma wiele implementacji i każda z nich ma inne typy podstawowe, te są znajdują się w prawie każdej z nich.)
Ważniejsze rodzaje wartości atrybutu:
- CHAR(n) - napis o stałej długości 'n'
- VARCHAR(n) - napis o zmiennej długość mniejszej niż 'n'
- NUMBER(p,s) - numer o danej precyzji i skali, precyzja to liczba cyfr a skala to liczba cyfr po przecinku.
- DATE - data
- TIMESTAMP - czas z dokładnością do ułamków sekundy
- INTERVAL - przedział czasu

## DLM

### Wybór [atrybutów](./Definicje.md###Atrybut) z tablicy za pomocą SELECT


**SELECT** - wybierz, wyświetl atrybut/y 


Wybranie wszystkich atrybutów w [relacji](./Definicje.md###Relacjie).
```sql
    SELECT *
    FROM nazwaTablicy;
```


Wybieranie atrybutów po ich nazwach z relacji.
```sql
    SELECT atrybut1, atrybut2, atrybut3
    FROM nazwaTablicy;
```
Operatory arytmetyczne  -, +, *, / 

```sql
    SELECT atrybut1 * 12, atrybut2 + 200, atrybut3 - 100, atrybut4 / 2
    FROM nazwaTablicy;
```

 
**AS** - jako - pozwala na nazwanie danego atrybutu przy jego wyświetlaniu.

```sql
SELECT atrybut1 AS nazwa1
FROM nazwaTablicy;
```

**||** - sklejenie napisów, traktuje/tłumaczy wartości do napisów np. 3 -> '3'. 

```sql
SELECT atrybutu1 || atrybut2
FROM nazwaTablicy;
```

```sql
SELECT 'Nazwa produktu: '||atrybut1
FROM nazwaTablicy;
```

**NVL(atrybut, wartość)** - w przypadku pustej wartości danego atrybutu wykorzystuje wartość

```sql
SELECT NVL(atrybut1,wartość)
FROM nazwaTablicy;
```

**DISTINCT** - eliminuje duplikaty

```sql
SELECT DISTINCT atrybut1
FROM nazwaTablicy;
```

**ORDER BY** - porządkuje wyniki
- **DESC** - malejąco
- **ASC** - rosnąco

Porządkuj po atrybut1 potem po atrybut2.
```sql
SELECT atrybut1, atrybut2
FROM nazwaTablicy
ORDER BY atrybut1, atrybut2 ASC;
```
Porządkuj po atrybut1 rosnąco potem po atrybut2 malejąco
```sql
SELECT atrybut1, atrybut2
FROM nazwaTablicy
ORDER BY atrybut1 ASC, atrybut2 DESC;
```

