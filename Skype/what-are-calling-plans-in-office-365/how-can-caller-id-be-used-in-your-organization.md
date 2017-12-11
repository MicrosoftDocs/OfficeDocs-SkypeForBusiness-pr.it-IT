---
title: "Come usare l'ID chiamante nella tua organizzazione"
ms.author: tonysmit
author: tonysmit
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
description: "ID chiamante può essere controllato per le chiamate in ingresso e in uscita per gli utenti di sistema telefonico utilizzando un criterio denominato CallingLineIdentity."
---

# Come usare l'ID chiamante nella tua organizzazione

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](5a0bd8ba-3334-46ee-becf-1025597737f6.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/5a0bd8ba-3334-46ee-becf-1025597737f6). 
  
ID chiamante può essere controllato per le chiamate in ingresso e in uscita per gli utenti di sistema telefonico utilizzando un criterio denominato CallingLineIdentity.
  
La funzionalità ID chiamante è disponibile per tutti gli utenti di sistema telefonico indipendentemente dalla connettività di rete PSTN:
  
- Connettività PSTN online
    
- Connettività PSTN locale con Skype for Business Cloud Connector Edition (richiede Cloud Connector Edition 1.4.2 o versione successiva)
    
- Connettività PSTN locale con Skype for Business Server (richiede Skype for Business Server 2015 CU5 o versione successiva)
    
> [!NOTE]
> Questo criterio non è disponibile in Skype for Business 2015 Server. 
  
## ID chiamante in uscita

Ci sono tre opzioni disponibili per l'ID chiamante PSTN in uscita:
  
- Numero di telefono assegnato all'utente, ovvero l'impostazione predefinita.
    
- Un numero di telefono classificato come  *servizio*  e il numero *verde*  la chiamata plan di messaggistica unificata in Office 365 telefono il numero di inventario. In genere è assegnato a una coda di chiamata o all'operatore automatico dell'organizzazione.
    
- Impostato su anonimo.
    
Tuttavia, non è possibile assegnare questi tipi di numeri di telefono all'ID del chiamante in uscita:
  
- Tutti i numeri di telefono che sono classificati come  *utente*  nel proprio telefono chiamando plan di messaggistica unificata numero inventario
    
- Un numero di telefono locale Skype for Business Server
    
Per impostare l'ID chiamante per un utente, consulta [Impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md).
  
### Controllo dell'ID chiamante in uscita da parte dell'utente finale

L'attributo EnableUserOverride consente agli utenti di uno o più di modificare le impostazioni di ID chiamante su **anonimo**. Si applica solo quando un criterio di CallingLineIdentity è configurato con un parametro CallingIDSubstitute LineURI o Sostituisci. Il valore predefinito di EnableUserOverride è False.
  
Gli utenti finali è possibile impostare il loro ID chiamante su **anonimo** utilizzando la scheda **Chiamare impostazioni** in di Skype for Business client desktop.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versione** <br/> |**Supportato** <br/> |
|A portata di clic  <br/> |Current Channel (Canale attuale), pubblicato in data 6 dicembre 2016 - versione 1611 (build 7571.2072)  <br/> |Sì  <br/> |
|A portata di clic  <br/> |Prima release di Deferred Channel (Canale differito) prevista per il 22 febbraio 2017 - versione 1701 (build 7766.2060)  <br/> |Sì  <br/> |
|A portata di clic  <br/> |Posticipato canale rilasciato 13 giugno 2017-versione 1701 (Build 7766.2092)  <br/> |Sì  <br/> |
|MSI  <br/> |Skype per le aziende  <br/> |No  <br/> |
|Mac  <br/> |Skype per le aziende  <br/> |No  <br/> |
   
Gli utenti finali possono inoltre modificare le loro impostazioni ID chiamante nella pagina delle impostazioni utente all'indirizzo [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
  
## ID chiamante in entrata

L'attributo BlockIncomingCallerID consente di bloccare l'ID chiamante su chiamate PSTN in ingresso. È possibile impostare questo attributo, ma non è disponibile per gli utenti finali nella pagina impostazioni dell'utente. Ed è attualmente disponibile solo con la connettività PSTN Online.
  
Per impostare l'ID chiamante per un utente, consulta [Impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  
## Vedere anche
<a name="MT_Footer"> </a>

#### 

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)
  
[Periodo di chiamata in uscita di conferenze audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
[Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

