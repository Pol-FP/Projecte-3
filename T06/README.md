# 🔐 T06: Fonaments del servei DNS

Com a membres cada cop més integrats de l’equip tècnic de la consultora EverPia, teniu davant un nou repte. El vostre client, una empresa de màrqueting digital (DigiCore), experimenta errors de connectivitat en certes aplicacions. El seu equip tècnic sospita que la causa principal podria ser una resolució de noms (DNS) incorrecta o lenta.

En resposta, se us ha encarregat realitzar una auditoria teòrica i pràctica del servei DNS per tal de formar el personal del client i oferir eines de diagnosi ràpides.

---

## 🎯 Objectiu del projecte

- Formar el personal tècnic de DigiCore en els conceptes fonamentals del DNS.
- Preparar una píndola formativa en format vídeo (10-15 minuts) amb explicacions clares.
- Realitzar una auditoria pràctica amb eines CLI per diagnosticar possibles problemes de resolució de noms.

---

## 🧩 Tasques a realitzar

### **Fase Teòrica**
1. Explicar la jerarquia i estructura del DNS (Root > TLD > Segon nivell).
2. Descriure el procés de resolució (iterativa vs recursiva).
3. Tipus de zones: directa, inversa, primària i secundària.
4. Tipus de registres clau: A, PTR, CNAME, MX, NS, SRV.
5. Conceptes essencials:
   - Resposta autoritativa
   - TTL (Time To Live)
   - SOA (Start of Authority)
   - Reenviadors (condicionals i incondicionals)
   - Resolució local (mDNS)
6. Preparar un vídeo formatiu amb esquemes i exemples.

### **Fase Pràctica**
1. Executar i analitzar les comandes següents amb **dig**:
   - `dig xtec.cat A` → IP, TTL, servidor que respon.
   - `dig tecnocampus.cat NS` → Servidors de noms autoritatius.
   - `dig escolapia.cat SOA` → Correu administrador i número de sèrie.
   - `dig -x 147.83.2.135` → Registres PTR associats a la IP.
2. Comprovació amb **nslookup** en mode interactiu:
   - Consulta bàsica no autoritativa (`type=A` sobre tecnocampus.cat).
   - Consulta autoritativa (usant IP del primer NS obtingut).
3. Validar resolució local (mDNS o fitxer hosts).
4. Crear un document `guia.md` amb:
   - Captures de les 6 comandes.
   - Explicacions detallades.
   - Proves de resolució local.

---

## 📄 Solució

Un dossier complet amb:
- Material formatiu (vídeo + resum teòric).
- Document `guia.md` amb resultats pràctics, anàlisi i captures.

Pots consultar la resolució completa de l’activitat al següent document:

👉 [**Accedir al video Introduccio DNS**](https://drive.google.com/file/d/1j0NRUsycJuhEbApfgolOBRX0FLe5hHcC/view)

👉 [**Accedir a la guia formativa DNS**](./T06_Guia.md)
