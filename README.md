# Sistemi e Reti






## I registri

Sono dispositiva di memoria a ridotta capacitá (uno o due byte) posti dentro il microprocessore,
grazie ad essi possiamo manipolare in modo temporaneo dati e indirizzi

- Memoria a breve termine del calcolatore
- Sono celle di memoria utilizzate per immagazzinare le informazioni necessarie per
l'esecuzione delle istruzioni
- Ci sono registri generici (Registri per memorizzare gli operandi delle operazioni da
eseguire) e registri speciali
  - i registri speciali utilizzati dalla UC per scopi particolari;
  - i registri di uso generale (registri aritmetici)
- Il loro numero dipende dal tipo di CPU
- Gli operandi delle istruzioni aritmetico/logiche possono contenere un indirizzo di
registro



## Registri speciali
1. PC: program counter, registro contatore delle istruzioni -detto IP (instruction
pointer) in alcune macchine (Intel)
2. IR: instruction register, registro delle istruzioni

3. MAR: memory address register, registro di indirizzamento della memoria –
collegato al bus indirizzi
4. MDR: memory data register, registro dati di memoria –collegato al bus dati
5. PSW: processor status word, parola di stato del processore... detto anche
FLAGS in alcune macchine (Intel)


## I Registri Generali 
sono usati per l’esecuzione di istruzioni memorizzando,
ad esempio:
1. il contenuto di una parola di memoria letto dal processore
2. il risultato di un’elaborazione sul contenuto di uno o più registri
3. gli operandi di un’istruzione aritmetica


## Accumulatore (registro di uso generale)
E’ senza dubbio uno dei registri più utilizzati in quanto in esso vengono memorizzati i
risultati delle varie operazioni effettuate dalla ALU ed è interessato anche dalle
operazioni di ricezione e di invio dei dati. L'accumulatore è quindi un registro dotato di
ampie capacità di comunicazione con i vari blocchi che costituiscono il sistema e le sue
dimensioni generalmente corrispondono alla lunghezza della parola trattata.

L'accesso alla memoria principale è più lento dell'accesso a un registro come
l'accumulatore perché la tecnologia utilizzata per la memoria principale è più lenta (ma più
economica) di quella utilizzata per un registro. I primi sistemi informatici elettronici erano
spesso divisi in due gruppi, quelli con accumulatori e quelli senza. I sistemi informatici
moderni hanno spesso più registri di uso generale che funzionano come accumulatori.

Gli accumulatori migliorano notevolmente le prestazioni in sistemi
come questi fornendo un'area per appunti in cui i risultati di un'operazione possono essere
trasferiti a quella successiva con una riduzione delle prestazioni minima o nulla.



## PC:

Il program counter (PC), anche chiamato instruction pointer (IP) in alcuni processori, è un registro della CPU che contiene l'indirizzo di memoria dell'istruzione corrente che la CPU sta elaborando.
Durante l'esecuzione di un programma, il contenuto del PC viene costantemente aggiornato dalla CPU in modo che punti all'indirizzo di memoria dell'istruzione successiva da eseguire. Ad ogni esecuzione di un'istruzione, il PC viene incrementato in modo che punti all'indirizzo di memoria dell'istruzione successiva.

oppure:

Il Program Counter, o PC, è il contatore ordinale del processore, ovvero il sistema con
cui vengono messe in sequenza e avanzate le istruzioni.

La sua caratteristica è quella di essere inizializzato al reset in modo da partire con il
conteggio dalla locazione 0000h, ovvero dal vettore del RESET.
In questa locazione si troverà la PRIMA istruzione che verrà eseguita.
La sua lunghezza in bytes e la sua funzione stabilirà il valore successivo del PC, che
andrà a puntare all' istruzione logicamente seguente.

Il suo funzionamento si può schematizzare così:

1. al Reset, il Program Counter viene precaricato con l'indirizzo che contiene la
prima istruzione da eseguire.
2. Il meccanismo del Program Counter fa si che il contenuto della locazione di
memoria a quell'indirizzo venga prelevato, decodificato ed eseguito.
3. a seconda di quale opcode si tratti, il Program Counter viene aggiornato con
l'indirizzo che contiene l' istruzione successiva.



## Pile:
Le operazioni che si possono pensare per la struttura LIFO sono:
- Verificare se è piena (IsFull)
- Verificare se è vuota (IsEmpty)
- Inserire un elemento (Push)
- Togliere un elemento (Pop)
- Far restituire il primo elemento, senza estrarlo (TopElem)
- Cancellare tutti i dati (Clear)
In alcuni casi le strutture LIFO hanno una dimensione limitata, per cui è necessario
definire un valore massimo di elementi inseribili. Inoltre, per implementare una pila
servono:
- uno spazio di memoria ordinato, dove inserire gli elementi
-un indice, per sapere qual è l’ultimo elemento inserito.
L’indice deve tener conto di quanti elementi ci sono nella pila.
Top= 0 →→→→pila vuota
Top= max→→→→pila piena

![image](https://user-images.githubusercontent.com/87804260/223405566-ee251106-04d7-4909-9a32-4b7060a666b4.png)



## Code:
Le code
Con il termine Coda indichiamo una lista di lunghezza variabile che prende il nome di
Sistema FIFO (First In First Out). Una CODA o QUEUE (leggi “chiù”) è una sequenza
di elementi che può essere “accorciata” da un lato e allungata da un altro lato:
Dequeue: operazione che corrisponde alla estrazione di un elemento dalla coda
Enqueue: operazione che corrisponde all’inserimento di un elemento dalla coda


per la struttura Coda (queue) le operazioni “base” sono le
seguenti:

- inserire un elemento x in coda (EnQueue(x));
- togliere un elemento dalla coda (DeQueue());
- verificare se la coda è vuota (IsEmpty());
- cancellare tutti i dati (ClearQueue());
- leggere (senza toglierlo dalla coda) il primo elemento in attesa
(readHead());
- nel caso in cui si preveda una coda con capacità massima limitata
verificare se la coda ha raggiunto la sua massima capacità: (IsFull()).

![image](https://user-images.githubusercontent.com/87804260/223403660-3a740247-29f2-4b25-a073-c11255edb4bc.png)


## Stack pointer:
indica l'attuale posizione dello stack nella locazione della memroia del programma, la zona di memoria é organizzata secondo un registro LIFO(Last in, First Out); i dati vengono prelevati a partire dal ultimo dato introdotto fino al primo. É a discrezione del programmatore in quale area della RAM vuole memorizzare lo stack e le sue rispettive dimensioni.

Quando una funzione viene chiamata lo stack pointer viene spostato in basso per fare spazio alle variabili locali della funzione, una volta terminata la funzione, il puntatore si ripristina da solo.

Ci sono due registri riservati alla gestione dello stack: ESP contiene
l'indirizzo della “cima” dello stack, EBP contiene l'indirizzo della base del frame
corrente
![image](https://user-images.githubusercontent.com/87804260/223402951-e2d679d0-f5ad-4c54-83cf-2a2b7e4d2460.png)

Fasi:
- PUSH <registro>: Posiziona il contenuto del primo registro in cima allo stack
- POP <registro>: Preleva il contenuto del registro partendo dall'inizio dello stack

![image](https://user-images.githubusercontent.com/87804260/223403368-aed2978e-9b33-49fd-be49-d5fa15b59d3a.png)




## IR:
La funzione di questo registro è quello di memorizzare l'istruzione che
deve essere eseguita; tale istruzione è espressa in forma codificata per
cui la sua esecuzione può avvenire solo dopo la sua traduzione in
linguaggio macchina. Questa operazione avviene in un decodificatore,
collegato direttamente al registro istruzioni, che a sua volta attiva la logica di
controllo.
In conclusione quindi il registro istruzioni, collegato unidirezionalmente al
circuito di decodifica, mantiene memorizzata l'istruzione per il tempo
necessario alla sua esecuzione. Le dimensioni di questo registro sono
solitamente uguali alla lunghezza della parola trattata.


## MAR:
Un registro che memorizza il contenuto del programm counter e che lo contiene fino a quando l'istruzione contenuta non viene eseguita.
Quindi, il contenuto é uguale solo che; mentre il programma counter punta alla locazione successiva, il MAR prima finisce l'esecuzione dell'istruzione e poi passa all'istruzione della locazione successiva.

  ![image](https://user-images.githubusercontent.com/87804260/223408189-2b4a5137-3e0d-4144-b158-fc65c85a14aa.png)
  
  
  ## Flag
  É una variabile booleana che assume i due stati di vero o falso, che segnala se un evento é davvero accadatuo o no.
  
  Quando voglia impostare il flag, dobbiamo mettere il suo valore a "vero" altrimenti se voglia resettare il flag lo    impostiamo a "falso".
  

  ## Registri di stato (Flags)
  
  Il registro di stato può essere scomposto in più celle elementari (flags) che
consentono di ricavare una serie di informazioni relative allo stato delle
unità interne al microprocessore. Infatti il loro contenuto si modifica,
passando da "1" a "0" e viceversa, in conseguenza dell'esecuzione di
determinate operazioni permettendo una verifica dei risultati ottenuti.
  
  Il registro dei flag, chiamato cosí anche se non é effettivamente un registro, riesce a contenere 8 bit dei quali 6 utilizzabili.
  Ogni bit ha un significato:
- C: Carry Flag: Tiene in memoria il bit piú significativo dell'accomulatore.
- N: Subtract Flag: Verifica se l'ultima operazione era una sottrazione.
- P/V: Paritty/Overflow Flag:  l'overflow controlla se vi é stata un operazione aritmetica, mentre Parity se l'operazione era di tipo logico
  H: Half carry Fag: indica se é avvenuto in riporto tra i 4 bit meno significativi e i 4 piú significativi dell'accomulature.
 - Z: Zero Flag: Segnala che l'accomulatore di é azzerato.
 - S: Sign Flag: Risulta ugual al bit piú significativo del risultato in accomulatore
  
  ![image](https://user-images.githubusercontent.com/87804260/223413243-4aa0d7aa-8a1a-4f7a-83ad-5dceaa87e6c5.png)

  
  ## Flag di controllo:
  
 - DF = Direction Flag: serve per la manipolazione delle stringhe; vale 0 = manipolazione all'indirizzo minore. vale 1 = la manipolazione parte dall'indirizzo maggiore.
 - IF = Interrupt Flag: se vale 1= i segnali di interruzione vengono percepiti dalla CPU, altrimenti non vengono calcolati.
 - TF = Trap Flag: Se vale 1 viene eseguita una trap al termine di ogni istruzione.
  
  
  ## Program Status Word
  
Il PSW contiene i bit che segnala stati d'errore e codici di condizione come abilitazione/disabilitazione dell'interrupt e il passaggio da utente a utente privilegiato.
