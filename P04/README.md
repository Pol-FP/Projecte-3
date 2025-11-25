# 🧩 P04: Instal·lant un servidor de noms (DNS) amb BIND9

## Introducció

L’empresa DigiCore ens ha encarregat la implantació completa del seu sistema DNS intern. Actualment, els seus treballadors accedeixen als serveis mitjançant adreces IP, cosa que genera problemes d’usabilitat, manteniment i consistència. La solució proposada consisteix en implementar un servidor DNS basat en **BIND9**, que permeti treballar amb noms de domini fàcils de recordar i adaptats al seu entorn intern.

Per a la prova de concepte s’utilitzarà el domini **digicore-XX.test**, on *XX* correspon al número assignat a cada alumne.

L’objectiu general del repte és aconseguir una infraestructura DNS funcional i professional, capaç de resoldre consultes directes (nom → IP) i inverses (IP → nom), així com implementar mecanismes de transferència de zona amb altres companys.

---

## 🎯 Objectius del projecte

- Instal·lar i configurar un servidor DNS primari utilitzant **BIND9**.
- Crear la **zona directa** i la **zona inversa** del domini assignat.
- Configurar un client Linux perquè utilitzi el servidor DNS intern.
- Verificar que la resolució de noms i IPs funciona correctament.
- Implementar la **transferència de zona** entre companys i configurar una zona secundària.
- Documentar tot el procés en un dossier tècnic.

---

## 🧰 Preparació prèvia

Abans d’iniciar la configuració del DNS, s’ha de:

- Crear una màquina virtual **Ubuntu Server** amb les especificacions indicades (4 GB RAM, 20 GB disc).
- Configurar dues interfícies de xarxa: *bridged* i *host-only*.
- Instal·lar els paquets necessaris, com ara el servidor DNS BIND9 i el servei SSH.

Aquest servidor serà el node principal sobre el qual es configurarà tota la infraestructura DNS.

---

## 🛠️ Accions a realitzar

A continuació es descriuen les diferents tasques que cal completar durant la pràctica:

### **1. Configuració del fitxer `named.conf.options`**
Cal habilitar la resolució recursiva per a la xarxa local i afegir un reenviador extern.  
Després, cal reiniciar el servei i comprovar-ne l’estat.

### **2. Configuració d’un client**
S’ha d’utilitzar una màquina Linux com a client, configurant el seu DNS per apuntar al servidor creat.  
Cal verificar que hi ha resolució funcional tant interna com externa.

### **3. Definició de zones DNS**
Cal editar `named.conf.local` per afegir dues zones:
- La zona directa del domini **digicore-XX.test**  
- La zona inversa corresponent a la xarxa utilitzada

### **4. Creació de la zona directa**
S’ha de crear un fitxer de zona que inclogui:
- Registre SOA
- Registre NS
- Registres A per als servidors
- Un registre CNAME

Aquest fitxer s’ha de situar dins una nova carpeta dedicada a les zones DNS.

### **5. Creació de la zona inversa**
S’ha de crear un fitxer de zona inversa que contingui:
- Registre SOA
- Registre NS
- Registres PTR corresponents

Aquest fitxer també s’ha de guardar dins la carpeta de zones.

### **6. Comprovacions**
Cal reiniciar el servei DNS i verificar:
- Resolució directa de noms
- Resolució inversa d’adreces IP

Aquestes proves s’han de realitzar des del client.

### **7. Transferència de zona**
Cal modificar la configuració de la zona directa per permetre la transferència a la IP d’un company.  
Posteriorment, s’ha de configurar una zona secundària d’un altre domini a la pròpia màquina i verificar que es replica correctament.

---

## 📄 Documentació final

Cal preparar un dossier tècnic que inclogui:

- Arxius editats de BIND9
- Arxius de les Zones Creades

---

## 📄 Solució

En acabar la pràctica, s’ha d’obtenir:

- [Arxius Solució](Arxius)
