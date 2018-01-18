---
title: "Utilizzo delle chiamate Analitica per la risoluzione dei Skype insufficiente per le aziende qualità delle chiamate"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Utilizzare chiama Analitica dettagli sui dispositivi, reti e connettività per la risoluzione dei problemi degli utenti con Skype per chiamate di lavoro e le riunioni."
ms.openlocfilehash: 043c7eac6099f23217c155ad91bf818aa4e57892
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a>Utilizzo delle chiamate Analitica per la risoluzione dei Skype insufficiente per le aziende qualità delle chiamate

Analitica chiamata consente di risolvere i problemi di connessione o chiamata con Skype per le aziende. Chiamata Analitica Visualizza informazioni dettagliate sui dispositivi, reti e connettività per le chiamate e le riunioni di ogni utente nel Skype per conto di Business. Se si crea, siti e tenant sono state aggiunte informazioni per chiamare Analitica verranno inoltre visualizzato per ogni chiamata e della sessione. Informazioni disponibili tramite chiamata Analitica consentono di capire perché un utente è insufficiente o esperienza della riunione. 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Risoluzione dei problemi di qualità chiamata tramite chiamata Analitica

Il livello di autorizzazione assegnato all'utente determina il tipo di informazioni è possibile accedere a chiamare Analitica:
  
- **Skype per Business admin**: si ha accesso a tutte le informazioni nel chiamare Analitica in Skype per interfaccia di amministrazione di Business.
    
- **Agenti help desk con autorizzazioni di livello 1**: viene visualizzato un numero limitato di dati di chiamare Analitica. È possibile risolvere le chiamate, ma sarà consegnare problemi con le riunioni per un agente di livello 2. Si dispone dell'accesso per il resto del Skype per interfaccia di amministrazione di Business.
    
- **Agenti help desk con autorizzazioni di livello 2**: visualizzazione di tutti i dati disponibili in chiamate Analitica e può semplificare la risoluzione dei problemi con le chiamate e le riunioni. Si dispone dell'accesso per il resto del Skype per interfaccia di amministrazione di Business.
    
Se hai bisogno di informazioni con le autorizzazioni, vedere il Skype per Business admin.
  
 **Aprire chiamare Analitica come agente help desk livello 1 o livello 2**
  
1. Accedere all'interfaccia di amministrazione di Office 365 e accedere utilizzando l'account di lavoro o della scuola. Nel web browser andare al *https://adminportal.services.skypeforbusiness.com*.
    
2. In **Ricerca utente**, iniziare a digitare il nome o sip l'indirizzo dell'utente le cui chiamate da risolvere i problemi e quindi selezionare l'utente dall'elenco.
    
    ![Cattura di schermata della casella di ricerca di utenti della chiamata Analitica in Skype per Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. Nella **cronologia delle chiamate**, selezionare la chiamata o una riunione che si desidera risolvere i problemi.
    
    ![Schermata che mostra la pagina cronologia delle chiamate per un utente con le informazioni, ad esempio informazioni di contatto dell'utente, un riepilogo delle attività per le riunioni e le chiamate e qualità di 7 giorni e una panoramica delle date e ore, i destinatari e qualità audio,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Selezionare la scheda **Impostazioni avanzate** e quindi individuare gli elementi gialli e rossi indicano problemi di connessione o qualità chiamate.
    
    Nei dettagli della sessione per ogni chiamata o riunione problemi secondari visualizzato in giallo. (Ad esempio, nella schermata seguente i valori sono di colore giallo per instabilità medio, dall'instabilità massima e frequenza di perdita di pacchetti Media.) Se un elemento è giallo, è all'esterno dell'intervallo normale e può contribuire al problema, ma non viene in genere presentarsi principale del problema. Caso di colore rosso, è un problema importante ed è probabile che le cause principali della qualità delle chiamate per la sessione corrente. 
    
    ![Schermata che mostra la scheda Avanzate della cronologia delle chiamate di un utente con la sezione di rete in ingresso espansa per visualizzare i dati di instabilità medio, dall'instabilità massimo e frequenza di perdita di pacchetti medie verranno mostrati in un colore giallo, vale a dire che sono problemi secondari.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
In casi rari, qualità dei dati di utilizzo non viene ricevuta per le sessioni audio. Spesso ciò è dovuto la chiamata della selezione e la connessione con il client che venga interrotto. In questo caso, la valutazione della sessione è "non disponibile".
  
Per le sessioni audio di qualità dei dati QoE (dagli utenti QoE), nella tabella seguente vengono descritti i problemi principali che soddisfano una sessione come "scarso".
  
|**Problema**|**Area**|**Descrizione**|
|:-----|:-----|:-----|
|Impostazione delle chiamate  <br/> |Sessione  <br/> |Codice di errore che MS-diagnostica 20-29 indica l'impostazione della chiamata non è riuscita. L'utente non è stato unirsi alla chiamata o riunione.  <br/> |
|Rete audio classificati chiamate  <br/> |Sessione  <br/> |Problemi di qualità di rete si sono verificati nelle aree, ad esempio la perdita di pacchetti, dall'instabilità, riduzione prestazioni NMOS, RTT, o nascosti rapporto. Per ulteriori informazioni sulle condizioni utilizzato per classificare le chiamate insufficiente, vedere il [blog di Microsoft post](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Dispositivo non funzionante  <br/> |Dispositivo  <br/> | Un dispositivo non funziona correttamente. Dispositivo non funziona rapporti è: <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>Argomenti correlati
[Configurazione di Skype per Business chiamare Analitica](set-up-call-analytics.md)

[Che cos'è la differenza tra Analitica delle chiamate e chiamate Dashboard qualità?](difference-between-call-analytics-and-call-quality-dashboard.md)

