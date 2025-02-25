# Algoritmo di validazione CIG

## CIG rilasciato da Simog (prima versione)
Sia ANNNNNNKKK la struttura del codice; <br>
<br>
- A appartiene a [0-9];
- N diverso da '0000000';
- N è la conversione in stringa di un intero progressivo espresso in notazione decimale compresi eventuali 0 nelle posizioni più significative;
- KKK= Hex (ANNNNNN * 211 mod 4091).

## CIG rilasciato da Simog (seconda versione) e PCP
Sia ANNNNNNKKK la struttura del codice:<br>
- A appartiene a [A-U],
- N è la conversione in stringa di un intero progressivo espresso in notazione esadecimale compresi eventuali 0 nelle posizioni più significative
- KKK = Hex((Dec(NNNNNN) + Ord (A)) * 211 mod 4091)

## CIG rilasciato da SmartCIG
Sia AKKCCCCCCC la struttura del codice: <br>
- A appartiene a {X, Y, Z};
- C è la conversione in stringa di un intero progressivo espresso in notazione esadecimale compresi eventuali 0 nelle posizioni più significative;
- C diverso da '0000000';
- KK = Hex(Dec(C)*211 mod 251=).

## Nota:<br>
Hex() è la funzione di conversione da decimale a esadecimale <br>
Dec() la funzione inversa di Hex(), <br>
Ord() è la funzione che restituisce l’ordinale della lettera nell’alfabeto (A=1, B=2, …, J=10, …..) <br>
'*' rappresenta la moltiplicazione algebrica <br>
'mod' rappresenta la funzione di modulo <br>
