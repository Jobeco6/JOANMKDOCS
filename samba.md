
# **Samba: Solució de Software de Codi Obert per SMB/CIFS**
## **Presentació de Samba**

**Samba** és un programari gratuït i de codi obert que implementa el protocol **SMB/CIFS**, facilitant la transmissió de dades i la gestió d’**impressores** en xarxes híbrides. El seu objectiu principal és oferir una integració sense friccions entre els entorns de **Windows** i de **Unix/Linux**.

### **Característiques i Avantatges de Samba**

- Permet la compartició de recursos com **fitxers** i **impressores** en entorns mixtos.
- Facilita la integració de servidors **Linux/Unix** en xarxes predominantment **Windows**.
- Proporciona una gestió centralitzada de l’autenticació i dels permisos d’accés.

## **Comparació amb NFS**

| **Aspecte**          | **Samba**                                                                  | **NFS**                                            |
|----------------------|----------------------------------------------------------------------------|----------------------------------------------------|
| **Protocol**         | **SMB/CIFS**                                                               | **NFS (Network File System)**                      |
| **Compatibilitat**   | Dissenyat per funcionar en entorns diversos amb suport per **Windows** i **Linux** | Optimitzat principalment per a **Unix/Linux**      |
| **Autenticació**     | Ofereix autenticació robusta amb control detallat dels permisos            | Basada en l’identificació del host i l’adreça IP     |
| **Usos Comuns**      | Compartició de recursos, ús d’**impressores** i administració centralitzada  | Transferència ràpida de fitxers                     |

## **Procediment d’Instal·lació de Samba**

1. **Actualització de la llista de paquets:**
    ```
    sudo apt-get update
    ```
2. **Instal·lació de Samba:**
    ```
    sudo apt-get install samba
    ```

![Explicació visual](<custom 3/samba/1.png>){ width=50% }

Més endavant s’explicarà com crear el **directori** a compartir, assignant-li els permisos pertinents. Cal que el propietari i el grup siguin **nobody:nogroup**; en aquest exemple, s’usa el permís **777** per simplificar el procés.

![Explicació visual](<custom 3/samba/2.png>){ width=50% }

## **Edició del Fitxer de Configuració smb.conf**

Per configurar la compartició del **directori** creat, s’ha de modificar el fitxer de configuració de Samba, ubicat a **`/etc/samba/smb.conf`**, afegint-hi una configuració bàsica.

![Explicació visual](<custom 3/samba/3.png>){ width=50% }

En aquest exemple, es defineix el **directori** compartit juntament amb opcions com **guest ok** i **browsable** (que pot ser "yes" o "no" segons els requisits). També es configuren els paràmetres **directory mask** i **create mask** per gestionar els permisos dels **directoris** i **fitxers**.

Pel que fa als permisos específics:

- L’opció **read list** concedeix accés de lectura exclusiva a l’usuari **jesus** i al grup **professors** (identificat amb l’arrova **@**).
- L’opció **write list** permet només a **jesus** l’èmfasi en l’escriptura.
- L’usuari **joan** no rebrà permisos ni accés al recurs compartit.

Un cop fet això, reiniciem i comprovem que s'hagi fet correctament.

![Explicació visual](<custom 3/samba/4.png>){ width=50% }

Ara, creem els usuaris i els assignem als grups amb la següent comanda:

```
useradd -M -s /sbin/nbologin "nom"
```

i després amb un tail comprovem que els usuaris s'hagin creat correctament.

![Explicació visual](<custom 3/samba/5.png>){ width=50% }

Ara, per a que la gentu pugui accedir-hi remotament al servidor samba, el que s'ha de fer és assignar una contrasenya a l'usuari amb la següent comanda:

```
smbpasswd -a "nom"
```

![Explicació visual](<custom 3/samba/6.png>){ width=50% }

Un cop ja hem assignat contrasenya a cada usuari ja podrem passar al client.

## Configuració client samba

El primer que hem de fer a la màquina del client per a poder connectar-nos a samba, és instal·lar smbclient a la nostra màquina de client.


![Explicació visual](<custom 3/samba/7.png>){ width=50% }
