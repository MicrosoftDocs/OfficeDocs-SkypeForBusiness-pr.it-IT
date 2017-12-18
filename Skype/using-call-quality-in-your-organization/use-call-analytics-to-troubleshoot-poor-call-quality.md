---
title: "Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate in Skype for Business"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 6/22/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
description: "Use Call Analytics details about devices, networks, and connectivity to troubleshoot user problems with Skype for Business calls and meetings."
---

# Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate in Skype for Business

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Call Analytics ti aiuta a risolvere i problemi di chiamata o di connessione con Skype for Business. Call Analytics mostra informazioni dettagliate su dispositivi, reti e connettività per le chiamate e le riunioni di ciascun utente del tuo account Skype for Business. Se sono state aggiunte a Call Analytics informazioni relative a edifici, siti e tenant, verranno mostrate per ciascuna chiamata e sessione. Le informazioni disponibili tramite Call Analytics possono aiutarti a capire perché un utente ha avuto un'esperienza in soddisfacente nel corso di una chiamata o riunione. 
  
> [!NOTE]
> Call Analytics è attualmente in fase di anteprima. Il testo e le immagini qui riportati possono non corrispondere alla tua esperienza di utilizzo. 
  
## Risoluzione dei problemi di qualità delle chiamate con Call Analytics

Il livello di autorizzazione che ti è stato assegnato determina il tipo di informazioni a cui hai accesso in Call Analytics.
  
- **Amministratore Skype for Business**: hai accesso a tutte le informazioni in Call Analytics e nell'interfaccia di amministrazione di Skype for Business.
    
- **Agente helpdesk con autorizzazioni di Livello 1**: hai accesso a un sottoinsieme ridotto di dati in Call Analytics. Puoi risolvere i problemi relativi alle chiamate, ma dovrai trasferire a un agente di Livello 2 i problemi con le riunioni. Non hai accesso al resto dell'interfaccia di amministrazione di Skype for Business.
    
- **Agente helpdesk con autorizzazioni di Livello 2**: hai accesso a tutti i dati disponibili in Call Analytics. Puoi aiutare a risolvere i problemi relativi a chiamate e riunioni. Non hai accesso al resto dell'interfaccia di amministrazione di Skype for Business.
    
Rivolgiti al tuo amministratore Skype for Business se hai bisogno di aiuto con le autorizzazioni.
  
 **Aprire Call Analytics come agente helpdesk di Livello 1 o Livello 2**
  
1. Vai alla pagina [https://adminportal.services.skypeforbusiness.com](https://adminportal.services.skypeforbusiness.com) e accedi con il tuo nome utente e password.
    
2. In **Ricerca utente**, inizia a digitare il nome o l'indirizzo SIP dell'utente per cui vuoi risolvere i problemi di chiamata, poi seleziona l'utente dall'elenco.
    
    ![Screenshot of the User Search box of Call Analytics in the Skype for Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. In **Registro chiamate**, seleziona la chiamata o la riunione per cui risolvere i problemi.
    
    ![Screenshot shows the call history page for a user with information such as the user's contact details, a summary of the 7-day quality and activity for meetings and calls, and an overview of dates and times, recipients, and audio quality,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Seleziona la scheda **Avanzate**, poi cerca le righe in giallo o in rosso, che indicano una bassa qualità della chiamata o problemi di connessione. 
    
    Nei dettagli della sessione per ciascuna chiamata o riunione, i problemi minori sono indicati in giallo (per esempio, nella schermata seguente, ci sono valori in giallo per jitter medio, jitter massimo e tasso medio di perdita di pacchetti). Se un valore è in giallo, è fuori dall'intervallo di normalità e può contribuire a causare il problema, ma è poco probabile che ne sia la causa principale. Se un valore è in rosso, è un problema significativo, e probabilmente è la causa principale della bassa qualità di questa sessione. 
    
    ![Screenshot shows the Advanced tab of a user's Call history with the Inbound network section expanded to reveal that the data for average jitter, max jitter, and average packet loss rate are shown in a yellow color, meaning they are minor issues.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
Raramente, non è ricevuta qualità dei dati di utilizzo per le sessioni audio. Spesso ciò è dovuto l'eliminazione di chiamata e di una connessione con il client di chiusura. In questo caso, il sessione è "non disponibile".
  
Per le sessioni audio di qualità percepita (dagli utenti QoE) dati, nella tabella seguente vengono descritti i problemi principali che soddisfano una sessione come "scadente."
  
|**Problema**|**Area**|**Descrizione**|
|:-----|:-----|:-----|
|Impostazione delle chiamate  <br/> |Sessione  <br/> |Codice di errore che MS-diagnostica 20-29 indica la configurazione di chiamata non è riuscita. L'utente non è stato partecipare alla chiamata o riunione.  <br/> |
|Rete audio classificato insufficiente della chiamata  <br/> |Sessione  <br/> |Problemi di qualità di rete in aree, ad esempio la perdita di pacchetti, variazione e riduzione del NMOS, RTT, si sono verificati o nascosto rapporto. Per ulteriori informazioni sulle condizioni utilizzato per classificare scarse chiamate, vedere questo [post di blog di Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Dispositivo non funziona  <br/> |Dispositivo  <br/> | Un dispositivo non funziona correttamente. Dispositivo non funziona rapporti è: <br/>  DeviceRenderNotFunctioningEventRatio > = 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0.005 <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  
## Vedere anche
<a name="MT_Footer"> </a>

#### 

[Configurazione di Skype for Business Call Analytics](set-up-skype-for-business-call-analytics.md)

