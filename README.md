# Discount Ticket PoC — Public Showcase

Middleware distribuito per la gestione concorrente di codici sconto tramite Node.js, Redis e Salesforce.

## Overview

Questa repository rappresenta la versione pubblica e documentativa della Proof of Concept.

L’obiettivo del progetto è dimostrare:

* gestione della concorrenza
* assegnazione atomica di risorse limitate
* integrazione middleware con Salesforce
* utilizzo di Redis come coda distribuita
* resilienza architetturale sotto carico

---

# Architettura

```text
                    ┌─────────────────┐
                    │ Client / API    │
                    │ Consumer        │
                    └────────┬────────┘
                             │
                             ▼
                  ┌────────────────────┐
                  │ Node.js Middleware │
                  │ Express API        │
                  └────────┬───────────┘
                           │
          ┌────────────────┴────────────────┐
          ▼                                 ▼
┌────────────────────┐          ┌────────────────────┐
│ Redis / Upstash    │          │ Salesforce         │
│ Atomic Code Queue  │          │ Assignment Storage │
└────────────────────┘          └────────────────────┘
```

---

# Tecnologie utilizzate

* Node.js
* Express.js
* Redis / Upstash
* Salesforce
* JSforce
* k6

---

# Obiettivi della PoC

La PoC è stata progettata per verificare:

* comportamento sotto carico concorrente
* prevenzione assegnazioni duplicate
* throughput middleware
* gestione race condition
* limiti infrastrutturali hosting/runtime

---

# Risultati principali

## Aspetti positivi

* Nessuna assegnazione duplicata
* Atomicità garantita tramite Redis
* Architettura semplice e scalabile
* Salesforce fuori dal path critico

## Limiti individuati

* Saturazione connessioni HTTP sotto carico elevato
* Timeout infrastrutturali
* Limiti hosting free tier

---

# Sicurezza

Questa repository NON contiene:

* codice completo
* configurazioni reali
* credenziali
* endpoint produttivi
* integrazioni sensibili

---

# Repository Privata

La repository completa contiene:

* implementazione middleware completa
* integrazione Salesforce
* load testing avanzato
* script k6
* endpoint reali
* configurazioni deployment

L’accesso può essere richiesto privatamente.

---

# Contatti

Per richiedere accesso alla repository privata o maggiori informazioni:

* aprire una issue
* oppure contattarmi direttamente tramite GitHub

---

# Licenza

MIT
