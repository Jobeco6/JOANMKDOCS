# Còpies de Seguretat

Les còpies de seguretat són duplicats de dades importants que es guarden en un lloc segur per tal de protegir-les contra pèrdues o danys. Aquestes còpies es poden utilitzar per restaurar les dades originals en cas de fallada del sistema, errors humans, atacs de programari maliciós o altres incidents que puguin comprometre la integritat de la informació.

## Per a què serveixen les còpies de seguretat?

1. **Protecció contra pèrdues de dades**: Les còpies de seguretat asseguren que les dades es poden recuperar en cas de pèrdua accidental o intencionada.
2. **Recuperació de sistemes**: Permeten restaurar sistemes complets després d'una fallada crítica.
3. **Seguretat contra atacs**: En cas d'atacs de ransomware o altres tipus de programari maliciós, les còpies de seguretat permeten recuperar les dades sense haver de pagar rescats.
4. **Compliment normatiu**: Moltes regulacions exigeixen la creació de còpies de seguretat per garantir la protecció de dades sensibles.
5. **Tranquil·litat**: Saber que les dades estan segures proporciona una major tranquil·litat i confiança en la gestió de la informació.

És important realitzar còpies de seguretat de manera regular i emmagatzemar-les en ubicacions segures, preferiblement en diferents formats i llocs físics o en el núvol.

## Tipus de còpies de seguretat

1. **Còpia completa**: Una còpia completa és una còpia de seguretat de totes les dades seleccionades. Aquest tipus de còpia és el més senzill de restaurar, ja que conté totes les dades en un sol conjunt. S'utilitza quan es necessita una còpia íntegra de totes les dades, però requereix més espai d'emmagatzematge i temps per completar-se.

2. **Còpia diferencial**: Una còpia diferencial inclou només les dades que han canviat des de l'última còpia completa. Això significa que cada còpia diferencial creix amb el temps fins que es realitza una nova còpia completa. És útil per reduir el temps i l'espai necessaris per a les còpies de seguretat, però la restauració pot ser més complexa, ja que requereix la còpia completa més la còpia diferencial més recent.

3. **Còpia incremental**: Una còpia incremental només inclou les dades que han canviat des de l'última còpia de seguretat, ja sigui completa o incremental. Aquest tipus de còpia és molt eficient en termes d'espai i temps, però la restauració pot ser més complicada, ja que requereix la còpia completa inicial i totes les còpies incrementals fins al punt de restauració desitjat.

### Quan utilitzar cada tipus de còpia de seguretat?

- **Còpia completa**: Utilitzeu-la quan necessiteu una còpia íntegra de totes les dades i disposeu de suficient espai d'emmagatzematge i temps per completar-la. És ideal per a còpies de seguretat inicials o periòdiques (per exemple, setmanals o mensuals).

- **Còpia diferencial**: És adequada quan voleu equilibrar el temps i l'espai d'emmagatzematge amb la facilitat de restauració. Pot ser útil per a còpies de seguretat diàries després d'una còpia completa setmanal.

- **Còpia incremental**: Utilitzeu-la quan necessiteu còpies de seguretat freqüents (per exemple, diàries o fins i tot horàries) i voleu minimitzar l'espai d'emmagatzematge i el temps necessari per a cada còpia. És ideal per a entorns on les dades canvien constantment i es necessita una protecció contínua.

## Eines per a realitzar còpies de seguretat

### cp

`cp` és una eina de línia de comandes en sistemes Unix i Linux que s'utilitza per copiar fitxers i directoris d'una ubicació a una altra. És una eina senzilla i fàcil d'utilitzar per a còpies de seguretat bàsiques.

**Exemple d'ús:**
```sh
cp -r /path/to/source /path/to/destination
```
L'opció `-r` indica que es copien recursivament tots els fitxers i subdirectoris.

### dd

`dd` és una eina de línia de comandes que s'utilitza per copiar i convertir dades a nivell de blocs. És especialment útil per crear imatges de disc o còpies de seguretat de dispositius complets.

**Exemple d'ús:**
```sh
dd if=/dev/sdX of=/path/to/backup.img bs=4M
```
En aquest exemple, `if` especifica el fitxer d'entrada (el dispositiu de disc) i `of` especifica el fitxer de sortida (la imatge de còpia de seguretat). L'opció `bs` defineix la mida del bloc.

### rsync

`rsync` és una eina de còpia de fitxers i directoris que permet la sincronització eficient de dades entre diferents ubicacions. És molt utilitzada per a còpies de seguretat perquè només copia els fitxers que han canviat, estalviant temps i ample de banda.

**Exemple d'ús:**
```sh
rsync -avz /path/to/source /path/to/destination
```
L'opció `-a` activa el mode arxiu (preserva permisos, propietaris, etc.), `-v` activa el mode detallat (mostra el procés) i `-z` comprimeix les dades durant la transferència.

Aquestes eines són molt útils per a diferents necessitats de còpies de seguretat i poden ser combinades segons els requisits específics de cada entorn.