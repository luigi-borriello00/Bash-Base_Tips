# BASH BASE TIPS

* `find /path` - Start to "/path" and search the file/dir passed by adding `-name`; you can also specify the type with `-d` or `-f` <br>
    * `find /usr/ -maxdepth 3 -type f -name "*.h" -print   `   <br>
        ---- > 'Stampa tutti i file presenti in tutte le dir di profondità massima 3 a partire da /usr/ e che finiscono per .h'        <br>
    * `find /usr/ -maxdepth 3 -type f -name "*.h" -exec wc -l '{}' \; ` <br>
        ---- > 'Cerca i file come il precedente ma questo giro stampa il numero di righe di ciascuno (ogni file trovato va a sostituire le {})'       
* ` GPG -D ./NOMEFILE | tar xvzf` - Extraxt and decrypt a file with GPG
* ` TOUCH ./filename ` - Create a file
* ` LS ` - Show the files in the current directory
* `CAT` - Show the content of a file
* `MV /oldPath /newPath` - Move a file or a directory
* `PS` - Show the processes running in the system
* `SUDO *command*` - Run a command as root
* `DU` - Show the disk usage of the current directory
    `DU -H` - Show the disk usage in human readable format
* `KILL` - Kill a process
* `BG` -    
* `FG` - 
* `READ` - Read a file
* `READ` -u {FD} -> Read from a file descriptor
* `WC` - Count the number of lines, words and characters in a file
* `ALIAS` - Assign a command to a shortcut *(ES. ALIAS V='LS --COLOR=NEVER')*
* `KILLALL *processName*` - Kill all processes with a given name
* `VI` - Open a file in vim editor
* `NANO` - Open a file in nano editor
* `START` - Start a program
* `EXIT` - Show the status of the runned script
* `CP /oldPath /newPath` - Copy a file or a directory
* `RM` - Delete a file or a directory
* `GREP` "STRING" - Search a string in a file or an Input
* `TEE` - 
* `HEAD` -N "n" NOMEFILE - Show the first n lines of a file
* `TAIL` - Show the last n lines of a file
* `SED` 's/oldString/newString/g' - Replace a string in a file
* `CUT` -b 4- NOMEFILE -> Show the first **n** bytes of a file


## ISTALLAZIONE PACCHETTI
* `APT-GET` -> INSTALLA/DISINSTALLA PACCHETTI
* `SUDO APT-GET UPDATE` -> AGGIORNA LA LISTA DEI PACKS INSTALLABILI
* `SUDO APT-GET INSTALL "NM"` -> INSTALLA PACK DI NOME "NM"
* `SUDO APT-GET PURGE "NM"` -> DISINSTALLA PACK
* `SUDO APT-GET INSTALL` --REINSTALL "NM" -> REINSTALLA SOVRASCRIVENDO LA VECCHIA INSTALLAZIONE
* `APTITUDE` -> PACK INSTALLABILE CHE A SUA VOLTA PERMETTE DI SCARICARE PACKS
* `WGET` -> PACK CHE SALVA NEL FS LOCALE I FILE PASSATO(LINK)(DIR CORRENTE)

## ISTRUZIONI CONTROLLO DI FLUSSO\\

* `FOR DO DONE` -------> for name in a bb ccc ; do echo $name ; echo ciao ciao ; done
* `WHILE DO DONE` 
* `IF THEN ELIF THEN ELSE FILE`
* `((QUALCOSA))` --> "QUALCOSA" DEVE ESSERE VALUTATO ARITMETICAMENTE


## USARE IN UNO SCRIPT GLI ARGOMENTI A RIGA DI COMANDO PASSATOGLI <br>
ESISTONO VARIABILI D'AMBIENTE CHE CONTENGONO GLI ARGOMENTI PASSATI A RIGA DI COMANDO

* `$#` - NUMERO DI ARGOMENTI PASSATI ALLO SCRIPT
* `$0` - NOME DEL PROCESSO IN ESECUZIONE
* `$1` - PRIMO ARGOMENTO, ($2 SECONDO E COSI VIA)
* `"$#`* - TUTTI GLI ARGOMENTI CONCATENATI E SEPARATI DA SPAZI, SE QUOTATO, QUOTA TUTTI GLI ARGOMENTI INSIEME ("$1 $2 ....ECC")
* `$@` - COME $* MA SE QUOTATO GLI ARGOMENTI VENGONO QUOTATI SEPARATAMENTE ("$1" "$2" ... ECC)
* `$?` - CONTIENE L'EXIT STATUS DELLO SCRIPT
* `${!NOMEVARIABILE}` - METTE NELLA VARIABILE IL VALORE CONTENUTO NELL'ARGOMENTO IL CUI NOME E' CONTENUTO IN ESSA
* `$$` - PROCESS ID DELLA SHELL CORRENTE

## REDIZIONAMENTO INPUT/OUTPUT

* `<` - REDIREZIONA L'INPUT VERSO UN FILE ESEMPIO: "GREP CIAO < CIAO.TXT"
* `>` - REDIREZIONA L'OUTPUT VERSO UN FILE CANCELLANDO IL VECCHIO CONTENUTO DEL FILE
* `>>` - COME IL PRECEDENTE ANCHE SE INVECE DI CANCELLARE OGNI VOLTA IL CONTENUTO METTE IN CODA
* `&>` - REDIREZIONA SIA LO STANDARD OUTPUT CHE LO STANDARD ERROR
* `2>` - REDIREZIONA IL SOLO STANDARD ERROR.
* `|` - REDIREZIONA L'OUTPUT DI UN FILE NELL'INPUT DI UN ALTRO FILE
* `< &n OPPURE > &n ` - REDIREZIONA SUL FILE DESCRIPTOR "1"
<br>
TUTTI QUESTI OPERATORI SI POSSONO CONCATENARE 
<br>
## PARAMETER EXPANSION

* %% - CERCA OCCORRENZA DI SUBSTRINGA IN STRINGA E TOGLILA(parte dal fondo) -> "STRINGA%%SUBSTRINGA"
* ## - UGUALE AL PRECEDENTE MA PARTE DALL'INIZIO
