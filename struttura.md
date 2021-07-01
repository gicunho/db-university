

## University Table

# departments
- id                    INT | AUTO_INCREMENT | UNIQUE | PRIMARY_KEY | NOTNULL
- nome                  VARCHAR(50) | NOTNULL
- (!) corso_laurea      VARCHAR(50) | NOTNULL

# corsi_laurea
- id                INT | AUTO_INCREMENT | UNIQUE | PRIMARY_KEY | NOTNULL
- nome              VARCHAR(50) | NOTNULL
- lingua            VARCHAR(50) | NULL
- durata            VARCHAR(50) | NULL
- materia           VARCHAR(50) | NOTNULL

# insegnanti
- id                INT | AUTO_INCREMENT | UNIQUE | PRIMARY_KEY | NOTNULL
- nome              VARCHAR(50) | NOTNULL
- cognome           VARCHAR(50) | NOTNULL
- materia           VARCHAR(30) | NULL

# studenti
- id                INT | AUTO_INCREMENT | UNIQUE | PRIMARY_KEY | NOTNULL
- nome              VARCHAR(50) | NOTNULL
- cognome           VARCHAR(50) | NOTNULL

# appello_esami
- id                INT | AUTO_INCREMENT | UNIQUE | PRIMARY_KEY | NOTNULL
- id_studenti       INT | FK | NOTNULL
- id_insegnanti     INT | FK | NOTNULL
- id_corso          INT | FK | NOTNULL

