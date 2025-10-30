# 🔐 T06: Fonaments del servei DNS

La consultora EverPia ha rebut l’encàrrec de DigiCore, una empresa de màrqueting digital que experimenta errors de connectivitat en certes aplicacions. El seu equip tècnic sospita que la causa principal és una resolució de noms (DNS) incorrecta o lenta.

🎯 **Objectiu del projecte**  
Realitzar una auditoria teòrica i pràctica del servei DNS per formar el personal del client i oferir eines de diagnosi ràpides.

---

## 🧩 **Fase Teòrica: Sessió Formativa**
Cal preparar una píndola formativa (vídeo de 10-15 minuts) que expliqui els conceptes següents:

### ✅ **Conceptes Clau**
- **Jerarquia i Estructura DNS**  
  Explicació de l’estructura en arbre: *Root > TLDs > Segon Nivell*.
- **Procés de Resolució**  
  Diferència entre consulta iterativa i recursiva. Què és un *Root Server* i un servidor autoritatiu.
- **Tipus de Zones**  
  - Zona directa vs inversa  
  - Zona primària vs secundària
- **Tipus de Registres**  
  - A: Nom → IP  
  - PTR: IP → Nom  
  - CNAME, MX, NS, SRV
- **Resposta Autoritativa**  
  Com identificar-la.
- **TTL (Time To Live)**  
  Impacte en propagació i rendiment.
- **SOA (Start of Authority)**  
  Informació essencial: correu administrador, número de sèrie.
- **Reenviadors**  
  Condicionals i incondicionals.
- **Resolució local**  
  mDNS i mecanismes sense servidor.

📄 **Resultat esperat:**  
Un vídeo formatiu + document resum amb esquemes i exemples.

---

## 🛠 **Fase Pràctica: Diagnosi amb CLI**
Demostració amb eines en Linux/macOS (dig) i multiplataforma (nslookup).  
Equip: Zorin amb interfícies NAT i adaptador pont.

### **Comandes i Anàlisi**
#### 🔹 Comanda 1: Consulta Bàsica (Registre A)
``
