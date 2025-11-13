# 🧩 **T04: Serveis de Directori. LDAP**

Com a membres de l’equip tècnic de la consultora **EverPia**, heu rebut una nova tasca d’un client en plena expansió: **Innovatech**, una *start-up* tecnològica emergent que està experimentant un creixement accelerat.  
Aquesta empresa pateix un **caos en la gestió dels seus usuaris i accessos**, ja que cada servei intern (servidor de fitxers, wiki de documentació, etc.) utilitza la seva pròpia base de dades d’usuaris i contrasenyes, i a més els ordinadors clients usen **autenticació local**.

Aquesta situació genera diversos **problemes crítics**:

- ⚙️ **Ineficiència operativa:** Cal crear o eliminar manualment els comptes en múltiples sistemes cada vegada que s’incorpora o marxa un empleat.  
- 🔒 **Risc de seguretat:** Els usuaris acaben reutilitzant contrasenyes entre serveis per comoditat.  
- 📈 **Manca d’escalabilitat:** A mesura que l’empresa afegeix nous serveis, el problema esdevé insostenible.

Per resoldre aquesta problemàtica, el **CEO d’Innovatech** ha contactat amb **EverPia** per implementar una solució d’**autenticació centralitzada** basada en **OpenLDAP (Lightweight Directory Access Protocol)**.  
Aquesta tecnologia, de **codi obert i alta robustesa**, s’alinea amb la filosofia de l’empresa, ja que tots els seus equips utilitzen **GNU/Linux**.

---

## 🎯 **Objectiu del projecte**

- Implementar el servei **OpenLDAP** en un servidor Linux.  
- Configurar el **domini base** i la **jerarquia d’unitats organitzatives**.  
- Crear i integrar **usuaris i grups** per gestionar els accessos als diferents serveis de xarxa.  
- Configurar un **equip client** perquè autentiqui usuaris utilitzant el directori LDAP.  
- Elaborar una **documentació tècnica completa** del procés seguint el plec de condicions.

---

## 🧩 **Tasques a realitzar**

### **Fase Teòrica**
1. Investigar els conceptes fonamentals del servei de directori LDAP.  
2. Comprendre la jerarquia d’un domini LDAP i l’estructura DN (Distinguished Name).  
3. Analitzar el funcionament d’OpenLDAP com a sistema d’autenticació centralitzada.  
4. Estudiar com s’integren usuaris i grups dins del directori.  
5. Preparar un breu document explicatiu o vídeo amb els conceptes principals.

### **Fase Pràctica**
1. Instal·lar i configurar **OpenLDAP** al servidor principal.  
2. Definir el **domini base** (`dc=innovatech,dc=local`) i crear les **unitats organitzatives** pertinents (`people`, `groups`, etc.).  
3. Afegir **usuaris i grups** mitjançant fitxers `.ldif`.  
4. Configurar un **client Linux** perquè s’autentiqui contra el servidor LDAP.  
5. Validar el funcionament de l’autenticació centralitzada (login d’un usuari LDAP).  
6. Documentar tot el procés amb **captures i explicacions detallades** dins del fitxer `guia.md`.

---

## 📄 **Solució**

Un dossier complet amb:

- Documentació tècnica (`guia.md`) que inclogui:  
  - Configuració del servidor i del client.  
  - Estructura de directoris i usuaris.  
  - Captures de pantalla i comandes utilitzades.  
- Materials formatius utilitzats (UD04.AA1–AA5).  

Pots consultar els recursos oficials i la documentació de l’activitat als següents materials:

👉 [**Accedir al plec de condicions tècniques**](#)  
👉 [**Material de classe (Moodle)**](#)
