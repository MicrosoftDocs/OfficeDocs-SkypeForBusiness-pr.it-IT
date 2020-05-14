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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Informazioni su quali telefoni di Polycom, HP e Mitel utilizzano Skype for Business e sulle licenze necessarie. '
ms.openlocfilehash: f51465cc86baa37e54acddf732cc5f63e6274aa1
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220436"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Ottenere telefoni per Skype for Business online

Skype for Business Online qualifies and supports desktop phones for users who want to have a traditional phone experience, rather than use the Skype for Business app. This topic covers the phones and firmware versions that are supported for use in Skype for Business Online and other information that can help you when you are setting up phones in your organization.

> [!NOTE]
> Skype for business verrà sostituito lentamente da Microsoft teams come metodo di comunicazione principale in Microsoft 365 e Office 365.  Per altre informazioni, vedere [una nuova visione per comunicazioni intelligenti in Office 365](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/) .
>
>Per ottenere gli aggiornamenti più recenti e le informazioni più aggiornate sui dispositivi supportati, vedere i [dispositivi Microsoft teams per comunicazioni intelligenti](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).
  
## <a name="supported-phones"></a>Telefoni supportati
  
Microsoft collabora e lavora in stretta collaborazione con Polycom, Yealink e AudioCodes per sviluppare e certificare una vasta gamma di dispositivi tramite il programma PIP (partner IP Phone Program) per il sistema telefonico.
  
Quando si ordinano nuovi telefoni per Skype for business, è importante acquistare telefoni con il *giusto ID prodotto*. Questi ID prodotto garantiscono che i telefoni ricevuti abbiano già installato la versione qualificata di Skype for business online.
  
|||
|:-----|:-----|
|**Partner telefonico** <br/> |**ID prodotto specifico Skype for Business** <br/> |
|Polycom  <br/> |ID prodotto - 019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Per altre informazioni sui telefoni Polycom, Vedi [raccolta documentazione di Poly](https://documents.polycom.com/category/voice).
  
Per maggiori dettagli sui telefoni Yealink, consulta [Telefoni IP per Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Per altre informazioni sui telefoni AudioCodes, Vedi [telefoni IP di Skype for business](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Phone Edition è supportato con Skype for business online, ma non con Microsoft teams. Il supporto mainstream per la piattaforma LPE è terminato da aprile/10/2014, con il supporto esteso fino ad aprile/11/al 2023 per allinearsi al ciclo di vita del supporto tecnico di Lync Server 2013. Per informazioni dettagliate sul ciclo di vita di LPE, vedere ciclo di vita dei [prodotti Microsoft](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) . I modelli LPE CAP non sono supportati con Skype for business online.
>
> Nei prossimi mesi, Office 365 non supporterà nessuna versione di TLS precedente alla 1.2. Poiché il sistema operativo sottostante di LPE non supporta TLS 1.2, LPE non sarà più supportato per la connessione a Office 365. Per ulteriori informazioni, consulta [Preparazione per l'utilizzo obbligatorio di TLS 1.2 in Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="supported-firmware"></a>Firmware supportato

Questa è la versione minima richiesta per i telefoni supportati per l'utilizzo con il sistema telefonico:
  
||||
|:-----|:-----|:-----|
|**Tipo di telefono** <br/> |**Firmware minimo** <br/> |**Data di rilascio** <br/> |
|Ottimizzato (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Maggio 2015  <br/> |
|Serie Polycom VVX certificata  <br/> |5.4.0A  <br/> |Dicembre 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Febbraio 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Dicembre 2016  <br/> |

Per altre informazioni sulle versioni correnti del firmware certificate, vedere [telefoni IP di Skype for business](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones#conference-phones).

> [!NOTE]
> I telefoni Lync Phone Edition (LPE) configurati per la distribuzione locale devono essere aggiornati alla versione minima o successiva del firmware richiesta prima di trasferire gli utenti in Skype for Business online. Se il trasferimento degli utenti dalla distribuzione locale a Skype for Business online avviene prima dell'aggiornamento del firmware nei telefoni, questi telefoni non potranno connettersi a Skype for Business online. 
  
## <a name="required-licenses"></a>Licenze obbligatorie

Skype for business online non richiede una licenza Microsoft aggiuntiva diversa dalle licenze utente. Per altre informazioni sulle licenze necessarie per gli utenti, Vedi [licenze per i componenti aggiuntivi Skype for business e Microsoft teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
I modelli di licenza per i produttori possono variare tra il firmware aperto SIP e Skype for business Certified. Se stai rinnovando un modello di certificato con un firmware Open SIP, devi verificare i requisiti di licenza del firmware con il produttore.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Set di funzionalità telefoni connessi Skype for business online

Per le funzionalità e le funzionalità del dispositivo completo, controllare le guide utente del produttore.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Funzionalità** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|Accedi con le credenziali utente  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Accesso tramite PC (accoppiamento), solo per Windows  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Accedi con (accesso Web)  <br/>  <br/> **Nota:** Verificare la matrice di supporto nella Guida alla distribuzione.           |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Partecipa a una riunione con un singolo clic  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Clic per comporre (accoppiamento)  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Controlli per le riunioni  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Casella vocale visuale  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Blocco telefono  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Aggiornamento del dispositivo  <br/> |Sì  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |Supporto per più paesi  <br/> |
|Provisioning in banda  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |Supporto per più paesi  <br/> |Supporto per più paesi  <br/> |
|QoE  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |Sì  <br/> |Supporto per riunioni private con ID conferenza di riunione dinamici  <br/> |
|Invio registro  <br/> <br/> **Nota:** Attualmente tutti i registri vengono caricati solo nel team di supporto Microsoft; l'accesso dei clienti ai registri telefonici non è ancora disponibile.           |Sì  <br/> |Supporto per più paesi  <br/> |Supporto per più paesi  <br/> |Supporto per più paesi  <br/> |
|Autenticazione moderna  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |Sì  <br/> |Supporto per riunioni private con ID conferenza di riunione dinamici  <br/> |
|Numero di emergenza multiplo  <br/> |Sì  <br/> |No  <br/> |No  <br/> |Sì  <br/> |
|Integrazione calendario Exchange*  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |Supporto per più paesi  <br/> |Supporto per più paesi  <br/> <br/> **Nota:** Richiede il tethering del PC           |
|Integrazioni presenza  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |Supporto per più paesi  <br/> |Supporto per più paesi  <br/> |
|Elenco aziendale  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |Supporto per più paesi  <br/> |Sì  <br/> |
|Delega  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |Sì  <br/> |No  <br/> |
|Integrazione immagine contatto  <br/> |No  <br/> |Sì  <br/> |Supporto per riunioni private con ID conferenza di riunione dinamici  <br/> |Sì  <br/> |
||||||

     
> [!NOTE]
> CX 600 oppure ogni altro telefono Aries non supporta l'autenticazione a più fattori (MFA). Se si forza l'MFA, questi dispositivi non saranno in grado di effettuare l'accesso. Questi dispositivi devono utilizzare solo l'Org ID come forma di autenticazione.
 
## <a name="what-else-should-you-know"></a>Informazioni aggiuntive
Per le istruzioni dettagliate di configurazione, vedi la sezione [Distribuzione dei telefoni per Skype for Business Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Argomenti correlati
[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](../getting-service-phone-numbers.md)

[Vantaggi offerti dal Sistema telefonico](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
