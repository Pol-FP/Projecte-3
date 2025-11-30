# 📁 Carpeta `Arxius`

Aquesta carpeta conté totes les zones DNS utilitzades a l’activitat.  
Inclou els fitxers necessaris per definir les zones directes i inverses, així com la configuració associada.

---

## 📄 Contingut de la carpeta

### **1. `named.conf.options`**
**Funció:**  
Arxiu de configuració on es declara la xarxa que s'utilitza modificacio feta a la segona linea de la config a acl "trusted". 
A més tambe s'inclouen configuracions com habilitar la recursio i configurar a qui escolta el nostre servidor dns o configurar forwarders tot aixo es pot veure modificat a partir de la linia 15.
[named.conf.options](./named.conf.options)

### **2. `named.conf.local`**
**Funció:**  
Arxiu de configuració on es declaren les zones DNS utilitzades pel servidor.  
A partir de la linea 8 es fan modificacions com la declaració de la zona, Inclou el tipus de zona, ruta dels fitxers i rols (master/slave) aquest arxiu conet una zona directa una inversa i una esclava.
[named.conf.local](./named.conf.local)

### **3. `db.digicore-06.test`**
**Funció:**  
Fitxer de **zona directa** on es defineixen els registres DNS del domini (A, CNAME, MX, NS...).
Editada la configuracio del SOA i creats tots els registres A o CNAME requerits 
> Exemple: server   IN      A          192.168.1.201
> Exemple: data     IN      CNAME      dbserver
[db.digicore-06.test](./db.digicore-06.test)

### **4. `db.192.168.1`**
**Funció:**  
Fitxer de **zona inversa** que resol adreces IP → noms de domini.  
Aqui dins es creen registre PTR per la resolucio inversa de consultes i es configuren algunes opcions com el TTL i el SOA.
> Exemple: 202      IN     PTR     dbserver.digicore-06.test.
[db.192.168.1](./db.192.168.1)

## ✔️ Arxius creats

- `db.nomdelazona`
- `db.nomdelazona.inv`
- `named.conf.local`
- *(Afegeix els altres fitxers creats.)*
