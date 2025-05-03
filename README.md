# Windows-For-Kids

## Parenting Windows Systems

#### *Check status, logged in time, etc. for local and remote maczhines ...*

~~~
C:\> query user
 BENUTZERNAME          SITZUNGSNAME       ID  STATUS  LEERLAUF   ANMELDEZEIT
 manfred               console             4  Aktiv       Kein   28.04.2025 12:03

# or in remote session (es. PowerShell)
C:\> query user /server:$SERVER
 BENUTZERNAME          SITZUNGSNAME       ID  STATUS  LEERLAUF   ANMELDEZEIT
 leo                   console             3  Aktiv       Kein   03.05.2025 18:26

C:\>query user /server:acer-w11-leo
 BENUTZERNAME          SITZUNGSNAME       ID  STATUS  LEERLAUF   ANMELDEZEIT
 leo                   console             3  Aktiv       Kein   03.05.2025 18:26

C:\>query session /server:acer-w11-leo
 SITZUNGSNAME      BENUTZERNAME             ID  STATUS  TYP         GERÄT
 services                                    0  Getr.
 console           Leo                       3  Aktiv
 rdp-tcp                                 65536  Abhör.
~~~

