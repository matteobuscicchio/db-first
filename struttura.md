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
- edition           VARCHAR(20) NOTNULL
- description       TEXT NULL
- vote              TEXT NULL




<!--
    Istruzioni:
    Provare a strutturare il seguente database che modellizza un hotel: 
    Ci sono varie stanze, ognuna con le proprie caratteristiche. 
    Le diverse stanze vengono prenotate per periodi di tempo, da ospiti. 
    Ad ogni prenotazione devono essere associati tutti gli ospiti della stanza.

    LEGENDA

    PK = PRIMARY_KEY
    FK = FOREIGN_KEY
-->

# database  name :  Hotel

# table     name :  customers
- customer_id    :   PK      SMALL INT                          NOT NULL
- name           :           VARCHAR(20)                        NOT NULL
- surname        :           VARCHAR(20)                        NOT NULL
- birth_date     :           SMALL INT          DATE            NOT NULL
- legal_id_code  :           SMALL INT                          NOT NULL
- goup_id        :   FK      SMALL INT                          NULL            DEFAULT(0)
- length_of_stay :           SMALL INT          DATE            NULL            DEFAULT(1)

# table     name :  goups
- goup_id        :  PK      SMALL INT                          NOT NULL
- members        :          SMALL INT                          NOT NULL
- customer_id    :  FK      SMALL INT                          NOT NULL
- hotel_room_id  :  FK      SMALL INT                          NOT NULL


# table     name :  rooms
- hotel_room_id  :  PK      SMALL INT                           NOT NULL
- room_ype       :          VARCHAR(50)                         NOT NULL
- price          :          SMALL INT           FLOAT(6,2)      NOT NULL
- goup_id        :  FK      SMALL INT                           NOT NULL


# table     name :  bills
- order          :   PK      SMALL INT          UNIQUE          NOT NULL
- date           :           SMALL INT          DATE            NOT NULL
- price          :   FK      SMALL INT          FLOAT(6,2)      NOT NULL
- length_of_stay :   FK      SMALL INT          DATE            NULL            DEFAULT(1)
- raw_price      :           SMALL INT          FLOAT(6,2)      NOT NULL        DEFAULT(Price x Stay)
- service_name   :           VARCHAR(20)                        NOT NULL
- service_price  :           SMALL INT                          NOT NULL
- services_price :           SMALL INT                          NULL            DEFAULT(service_p(sum))
- raw_total_price:           SMALL INT          FLOAT(6,2)      NOT NULL        DEFAULT(raw_p + services_p)
- final_price    :           SMALL INT          FLOAT(6,2)      NOT NULL        DEFAULT(raw_t_p + tax)
- customer_id    :   FK      SMALL INT                          NOT NULL