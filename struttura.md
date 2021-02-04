<!-- db-first
Istruzioni:
Create un file di testo per descrivere un database 
di un negozio di videogiochi.
Strutturate il file come fatto oggi in classe.  
Specificate: il nome del database, la tabella 
e le potenziali colonne con i tipi di dato. -->

# database  name :  GameStonk
# table     name :  Games
- id                INT PRIMARY_KEY NOTNULL
- barcode           SMALLINT UNIQUE NOTNULL
- title             VARCHAR(30) NOTNULL
- author            VARCHAR(30) NULL
- developer         VARCHAR(30) NULL
- publisher         VARCHAR(30) NOTNULL
- relise_date       YEAR NUll
- price             FLOAT(6,2) NOTNULL
- dlc               TINYINT NULL DEFAULT(0)
- language          VARCHAR(20) NOTNULL
- pegi              SMALLINT NOTNULL
- onLine_mode       TINYINT NOTNULL
- digital_copy      TINYINT NUILL DEFAULT(0)
- availability      TINYINT NUILL DEFAULT(0)