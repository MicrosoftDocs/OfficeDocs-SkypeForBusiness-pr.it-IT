---
title: Ottenere telefoni per Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 91f2d947-45fc-4fab-bd8b-2e313531c477
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Informazioni su quali telefoni di Polycom, HP e Mitel utilizzano Skype for Business e sulle licenze necessarie. '
ms.openlocfilehash: 92a91d97efabeaaebb074e41e41bc9a8812fa0c5
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780610"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Ottenere telefoni per Skype for Business online

Skype per Business Online qualifica e supporta i telefoni da scrivania per gli utenti che desiderano implementare un'esperienza di telefoni tradizionali, anziché utilizzare la app Skype for Business. In questo argomento vengono illustrati i telefoni e le versioni del firmware supportati per l'utilizzo di Skype for Business online e altre informazioni utili quando si impostano i telefoni all'interno della propria organizzazione.
  
Per ottenere gli ultimi aggiornamenti e le informazioni più aggiornate sui dispositivi supportati, consulta il [Catalogo di dispositivi per Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
## <a name="supported-phones"></a>Telefoni supportati

Per gli utenti di Skype for Business online, puoi scegliere tra diversi modelli nell'elenco  *Telefoni certificati per Skype for Business* e tra i telefoni che eseguono Lync Phone Edition (LPE) elencati nella categoria Skype for Business online nel[Catalogo di dispositivi Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
Microsoft lavora in stretta collaborazione con Polycom, Yealink e AudioCodes per sviluppare e certificare un'ampia gamma di dispositivi tramite Programma Partner Telefoni IP (PIP) per Sistema telefonico in Office 365 e Skype per Business Server.
  
Se si ordinano nuovi telefoni per Skype for Business, è importante acquistare telefoni con l' *ID prodotto giusto*. Questi ID prodotto assicurano che i telefoni che riceverai avranno la versione approvata per Skype for Business online già installata.
  
|||
|:-----|:-----|
|**Partner telefonico** <br/> |**ID prodotto specifico Skype for Business** <br/> |
|Polycom  <br/> |ID prodotto - 019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Per maggiori dettagli sui telefoni Polycom, consulta [Soluzioni vocali per Microsoft](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
  
Per maggiori dettagli sui telefoni Yealink, consulta [Telefoni IP per Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Per maggiori dettagli sui telefoni AudioCodes, consulta [Telefoni IP per Skype for Business](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Phone Edition è supportato su Skype for Business online, ma non su Microsoft Teams. Il supporto principale per la piattaforma LPE è terminato il 10 aprile 2014 e il supporto esteso terminerà l'11 aprile 2023 per allinearsi con il ciclo di vita del supporto dei prodotti Lync Server 2013. Consulta [Ciclo vitale dei prodotti Microsoft](https://support.microsoft.com/en-us/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) per i dettagli sul ciclo vitale di LPE. I modelli LPE PAC non sono supportati con Skype for Business online.
>
> Nei prossimi mesi, Office 365 non supporterà nessuna versione di TLS precedente alla 1.2. Poiché il sistema operativo sottostante di LPE non supporta TLS 1.2, LPE non sarà più supportato per la connessione a Office 365. Per ulteriori informazioni, consulta [Preparazione per l'utilizzo obbligatorio di TLS 1.2 in Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="supported-firmware"></a>Firmware supportato

Si tratta della versione software minima necessaria per i telefoni supportati per l'utilizzo con Sistema telefonico in Office 365:
  
||||
|:-----|:-----|:-----|
|**Tipo di telefono** <br/> |**Firmware minimo** <br/> |**Data di uscita** <br/> |
|Ottimizzato (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Maggio 2015  <br/> |
|Serie Polycom VVX certificata  <br/> |5.4.0A  <br/> |Dicembre 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Febbraio 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Dicembre 2016  <br/> |
   
> [!NOTE]
I telefoni Lync Phone Edition (LPE) configurati per la distribuzione locale devono essere aggiornati alla versione minima o successiva del firmware richiesta prima di trasferire gli utenti in Skype for Business online. Se il trasferimento degli utenti dalla distribuzione locale a Skype for Business online avviene prima dell'aggiornamento del firmware nei telefoni, questi telefoni non potranno connettersi a Skype for Business online. 
  
## <a name="required-licenses"></a>Licenze necessarie

Skype for Business online non richiede alcuna licenza Microsoft aggiuntiva rispetto alle licenze utente. Per saperne di più sulle licenze utente necessarie consulta [Licenze per i componenti aggiuntivi di Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Il modello di licenza del produttore potrebbe variare tra firmware certificato Skype for Business e Open SIP. Se stai rinnovando un modello di certificato con un firmware Open SIP, devi verificare i requisiti di licenza del firmware con il produttore.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Set di funzionalità telefoni connessi a Skype for Business online

Per le caratteristiche e funzionalità complete del dispositivo, consulta il manuale utente del produttore.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Funzionalità** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|Accedi con le credenziali utente  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Accesso tramite PC (accoppiamento), solo per Windows  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Accedi con (accesso Web)  <br/>  <br/> **Nota:** Controlla la matrice di supporto nella guida alla distribuzione.           |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Partecipa a una riunione con un singolo clic  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Clic per comporre (accoppiamento)  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Controlli per le riunioni  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Casella vocale visuale  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Blocco telefono  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Aggiornamento del dispositivo  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Provisioning in banda  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|QoE  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Invio registro  <br/> <br/> **Nota:** Attualmente, tutti i registri vengono caricati solo al team di Supporto Microsoft; l'accesso dei cliente alle telefonate non è ancora disponibile.           |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Autenticazione moderna  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Numero di emergenza multiplo  <br/> |Sì  <br/> |No  <br/> |No  <br/> |Sì  <br/> |
|Integrazione calendario Exchange*  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> <br/> **Nota:** È necessario il tethering del PC           |
|Integrazione presenza  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Elenco aziendale  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Delega  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Integrazione immagine contatto  <br/> |No  <br/> |Sì  <br/> |No  <br/> |Sì  <br/> |
||||||

     
> [!NOTE]
> CX 600 oppure ogni altro telefono Aries non supporta l'autenticazione a più fattori (MFA). Se si forza l'MFA, questi dispositivi non saranno in grado di effettuare l'accesso. Questi dispositivi devono utilizzare solo l'Org ID come forma di autenticazione.
 
## <a name="what-else-should-you-know"></a>Quali altre informazioni sono necessarie?
Per istruzioni dettagliate di configurazione, consulta la sezione [Distribuzione dei telefoni per Skype for Business Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Argomenti correlati
[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](../getting-service-phone-numbers.md)

[Ecco cosa offre il Sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilità di Audioconferenza e Piani di chiamata per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 