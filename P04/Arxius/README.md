# 📁 Carpeta `Arxius`

Aquesta carpeta conté totes les zones DNS utilitzades a l’activitat.  
Inclou els fitxers necessaris per definir les zones directes i inverses, així com la configuració associada.

---

## 📄 Contingut de la carpeta

### **1. `named.conf.options`**
**Funció:**  
Arxiu de configuració on es declara la xarxa utilitzada.  
S’ha realitzat una modificació a la segona línia, dins l’ACL `"trusted"`.  

A més, també s’hi inclouen configuracions com habilitar la recursió, definir a qui escolta el servidor DNS i establir *forwarders*.  
Totes aquestes modificacions es poden trobar a partir de la línia 15.

[named.conf.options](./named.conf.options)

---

### **2. `named.conf.local`**
**Funció:**  
Arxiu de configuració on es declaren les zones DNS utilitzades pel servidor.  

A partir de la línia 8 s’han realitzat modificacions, com ara la declaració de la zona, el tipus de zona, el camí dels fitxers i els rols (master/slave).  
Aquest arxiu conté una zona directa, una zona inversa i una zona esclava.

[named.conf.local](./named.conf.local)

---

### **3. `db.digicore-06.test`**
**Funció:**  
Fitxer de **zona directa** on es defineixen els registres DNS del domini (A, CNAME, MX, NS...).  
S’ha editat la configuració del SOA i s’han creat tots els registres A i CNAME requerits.

> Exemple: `server   IN   A       192.168.1.201`  
> Exemple: `data     IN   CNAME   dbserver`

[db.digicore-06.test](./db.digicore-06.test)

---

### **4. `db.192.168.1`**
**Funció:**  
Fitxer de **zona inversa** que resol adreces IP → noms de domini.  
En aquest fitxer s’han creat els registres PTR per a la resolució inversa de consultes, així com la configuració del TTL i del SOA.

> Exemple: `202   IN   PTR   dbserver.digicore-06.test.`

[db.192.168.1](./db.192.168.1)
