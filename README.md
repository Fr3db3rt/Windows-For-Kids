# Windows-For-Kids

## Parenting Windows Systems

#### *Check status, logged in time, etc., for local and remote machines ...*

``` cmd
C:\> query user
 BENUTZERNAME          SITZUNGSNAME       ID  STATUS  LEERLAUF   ANMELDEZEIT
 manfred               console             4  Aktiv       Kein   28.04.2025 12:03

# or remote
C:\> query user /server:$SERVER
 BENUTZERNAME          SITZUNGSNAME       ID  STATUS  LEERLAUF   ANMELDEZEIT
 leo                   console             3  Aktiv       Kein   03.05.2025 18:26

C:\ >query user /server:acer-w11-leo
 BENUTZERNAME          SITZUNGSNAME       ID  STATUS  LEERLAUF   ANMELDEZEIT
 leo                   console             3  Aktiv       Kein   03.05.2025 18:26

C:\> query session /server:acer-w11-leo
 SITZUNGSNAME      BENUTZERNAME             ID  STATUS  TYP         GERÄT
 services                                    0  Getr.
 console           Leo                       3  Aktiv
 rdp-tcp                                 65536  Abhör.
```

#### *Set _Login-Time_ restrictions* to certain hours
*does only apply to **LOGIN** to certain times...*  
*does **NOT LOGOUT** users, if they are already logged in!*

``` powershell
# in remote PowerShell session:
[Acer-W11-Leo]: PS C:\> net user Leo /TIMES:"Mo-Fr,13:00-19:00;Sa-So,13:00-15:00"
Der Befehl wurde erfolgreich ausgefhrt.
~~~

*verify settings*
~~~ powershell
[Acer-W11-Leo]: PS C:\> net user Leo
Benutzername                        Leo
Vollst„ndiger Name
Beschreibung
Benutzerbeschreibung
L„nder-/Regionscode                 000 (Standardsystemvorgabe)
Konto aktiv                         Ja
Konto abgelaufen                    Nie

Letztes Setzen des Kennworts        28.02.2025 19:37:09
Kennwort l„uft ab                   Nie
Kennwort „nderbar                   28.02.2025 19:37:09
Kennwort erforderlich               Nein
Benutzer kann Kennwort „ndern       Ja

Erlaubte Arbeitsstationen           Alle
Anmeldeskript
Benutzerprofil
Basisverzeichnis
Letzte Anmeldung                    03.05.2025 18:26:34

Erlaubte Anmeldezeiten              Sonntag 13:00:00 - 19:00:00
                                    Montag 13:00:00 - 15:00:00
                                    Dienstag 13:00:00 - 15:00:00
                                    Mittwoch 13:00:00 - 15:00:00
                                    Donnerstag 13:00:00 - 15:00:00
                                    Freitag 13:00:00 - 15:00:00
                                    Samstag 13:00:00 - 19:00:00

Lokale Gruppenmitgliedschaften      *Benutzer
                                    *Remotedesktopbenutzer
Globale Gruppenmitgliedschaften     *Kein
Der Befehl wurde erfolgreich ausgefhrt.
```


