# 📁 Carpeta `Arxius`

Aquesta carpeta conté totes les zones DNS utilitzades a l’activitat.  
Inclou els fitxers necessaris per definir les zones directes i inverses, així com la configuració associada.

---

## 📄 Contingut de la carpeta

### **1. `db.nomdelazona`**
**Funció:**  
Fitxer de **zona directa** on es defineixen els registres DNS del domini (A, CNAME, MX, NS...).  
> Exemple: resolució de noms per al domini `exemple.local`.

### **2. `db.nomdelazona.inv`**
**Funció:**  
Fitxer de **zona inversa** que resol adreces IP → noms de domini.  
> Exemple: resolució inversa per a la xarxa `192.168.1.0/24`.

### **3. `named.conf.local`**
**Funció:**  
Arxiu de configuració on es declaren les zones DNS utilitzades pel servidor.  
Inclou el tipus de zona, ruta dels fitxers i rols (master/slave).

### **4. Altres fitxers**
Inclou aquí qualsevol altre fitxer creat durant l’activitat i la seva funció:
- `db.127`
- `db.root`
- `db.broadcast`
- *(Afegeix la funció de cadascun.)*

---

## 🛠️ Modificacions realitzades

### ✏️ Fitxer `db.nomdelazona`
- Modificació 1:  
- Modificació 2:  

### ✏️ Fitxer `db.nomdelazona.inv`
- Modificació 1:  
- Modificació 2:  

### ✏️ Fitxer `named.conf.local`
- Modificació 1:  
- Modificació 2:  

---

## ✔️ Arxius creats

- `db.nomdelazona`
- `db.nomdelazona.inv`
- `named.conf.local`
- *(Afegeix els altres fitxers creats.)*
