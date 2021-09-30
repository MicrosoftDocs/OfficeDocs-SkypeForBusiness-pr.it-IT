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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Informazioni su quali telefoni di Polycom, HP e Mitel utilizzano Skype for Business e sulle licenze necessarie. '
ms.openlocfilehash: 4b4a5e48a531a694b006126221ddc7fcba40e1c3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013150"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Ottenere telefoni per Skype for Business online

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

Skype for Business Online qualifica e supporta i telefoni desktop per gli utenti che vogliono avere un'esperienza telefonica tradizionale, invece di usare l'app Skype for Business. Questo argomento riguarda i telefoni e le versioni del firmware supportati per l'uso in Skype for Business Online e altre informazioni utili per configurare i telefoni nell'organizzazione.

> [!NOTE]
> Skype For Business verrà lentamente sostituito da Microsoft Teams come metodo di comunicazione principale in Microsoft 365 e Office 365.  Per [altre informazioni,](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/) vedere Una nuova visione per le comunicazioni intelligenti Office 365 informazioni.
>
>Per ottenere gli aggiornamenti più recenti e le informazioni più aggiornate sui dispositivi supportati, vedere i Microsoft Teams [per le comunicazioni intelligenti.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)
  
## <a name="supported-phones"></a>Telefoni supportati
  
Microsoft collabora e collabora a stretto contatto con Polycom, Yealink e AudioCodes per sviluppare e certificare un'ampia gamma di dispositivi tramite il programma PARTNER IP Telefono Program (PIP) per il Sistema telefonico.
  
Quando si ordinano nuovi telefoni per Skype for Business, è importante acquistare telefoni con *l'ID prodotto corretto.* Questi ID prodotto assicurano che nei telefoni ricevuti sia già installata Skype for Business versione qualificata online.
  
|Partner telefonico  |ID prodotto specifico Skype for Business  |
|:-----|:-----|
|Polycom   |ID prodotto - 019   |
|Yealink   |SIP-TXXG Skype for Business Edition   |
|AudioCodes   |UCXXXHDEG (SfB)   |
   
Per altre informazioni sui telefoni Polycom, vedere [Libreria di documentazione Poly.](https://documents.polycom.com/category/voice)
  
Per maggiori dettagli sui telefoni Yealink, consulta [Telefoni IP per Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Per altre informazioni sui telefoni AudioCodes, [Skype for Business telefoni IP](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Telefono Edition è supportato con Skype for Business Online, ma non con Microsoft Teams. Il supporto mainstream per la piattaforma LPE è terminato entro il 10 aprile/2014, con supporto esteso fino all'11/11/2023 per allinearsi al ciclo di vita del supporto dei prodotti di Lync Server 2013. Per [informazioni dettagliate sul](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) ciclo di vita di LPE, vedere Ciclo di vita dei prodotti Microsoft. I modelli CAP di LPE non sono supportati con Skype for Business Online.
>
> Nei prossimi mesi, Office 365 non supporterà nessuna versione di TLS precedente alla 1.2. Poiché il sistema operativo sottostante di LPE non supporta TLS 1.2, LPE non sarà più supportato per la connessione a Office 365. Per ulteriori informazioni, consulta [Preparazione per l'utilizzo obbligatorio di TLS 1.2 in Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="supported-firmware"></a>Firmware supportato

Questa è la versione minima del software necessaria per il funzionamento dei telefoni Sistema telefonico:
  

|Tipo di telefono |Firmware minimo |Data di rilascio |
|:-----|:-----|:-----|
|Ottimizzato (Lync Phone Edition)   |4.0.7577.4463   |Maggio 2015   |
|Serie Polycom VVX certificata   |5.4.0A   |Dicembre 2015   |
|Yealink   |X.8.1.52   |Febbraio 2017   |
|AudioCodes   |3.0.0.459.1   |Dicembre 2016   |

Per altre informazioni sulle attuali versioni certificate del firmware, vedere Skype for Business [telefoni IP.](../../../SfbPartnerCertification/certification/devices-ip-phones.md)

> [!NOTE]
> I telefoni Lync Phone Edition (LPE) configurati per la distribuzione locale devono essere aggiornati alla versione minima o successiva del firmware richiesta prima di trasferire gli utenti in Skype for Business online. Se il trasferimento degli utenti dalla distribuzione locale a Skype for Business online avviene prima dell'aggiornamento del firmware nei telefoni, questi telefoni non potranno connettersi a Skype for Business online. 
  
## <a name="required-licenses"></a>Licenze obbligatorie

Skype for Business Online non richiede alcuna licenza Microsoft aggiuntiva oltre alle licenze utente. Per altre informazioni sulle licenze utente richieste, vedere licenze Skype for Business [e Microsoft Teams componenti aggiuntivi](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
I modelli di licenza del produttore possono variare tra sip aperto Skype for Business firmware certificato. Se stai rinnovando un modello di certificato con un firmware Open SIP, devi verificare i requisiti di licenza del firmware con il produttore.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype for Business Set di funzionalità telefoni connessi online

Per le funzionalità e le funzionalità complete dei dispositivi, consulta le guide per gli utenti del produttore.
  

|Funzionalità  |Polycom 3PIP  |Yealink 3PIP |AudioCodes 3PIP |LPE |
|:-----|:-----|:-----|:-----|:-----|
|Accedi con le credenziali utente   |Sì  |Sì   |Sì   |No   |
|Accesso tramite PC (accoppiamento), solo per Windows   |Sì   |Sì   |Sì   |Sì   |
|Accedi con (accesso Web)  <br/>  <br/> **Nota:** Controllare la matrice di supportabilità nella guida alla distribuzione.  |Sì   |Sì   |Sì   |No   |
|Partecipa a una riunione con un singolo clic   |Sì   |Sì   |Sì   |Sì   |
|Clic per comporre (accoppiamento)   |Sì   |Sì   |Sì   |Sì > |
|Controlli per le riunioni   |Sì   |Sì   |Sì   |Sì   |
|Casella vocale visuale   |Sì   |Sì   |Sì   |Sì   |
|Blocco telefono   |Sì   |Sì   |Sì   |Sì   |
|Aggiornamento del dispositivo   |Sì   |Sì   |Sì   |Sì   |
|Provisioning in banda   |Sì   |Sì   |Sì   |Sì   |
|QoE   |Sì   |Sì   |Sì   |No  |
|Invio registro  <br/> <br/> **Nota:** Attualmente, tutti i log vengono caricati solo nel team di supporto Microsoft. l'accesso dei clienti alle log delle telefonate non è ancora disponibile.           |Sì   |Sì   |Sì   |Sì   |
|Autenticazione moderna   |Sì   |Sì   |Sì   |No   |
|Numero di emergenza multiplo   |Sì   |No   |No   |Sì   |
|Integrazione calendario Exchange*   |Sì   |Sì   |Sì   |Sì  <br/> <br/> **Nota:** Richiede il tethering del PC           |
|Integrazioni presenza   |Sì   |Sì   |Sì   |Sì   |
|Elenco aziendale   |Sì   |Sì   |Sì   |Sì   |
|Delega   |Sì   |Sì   |Sì   |No   |
|Integrazione immagine contatto   |No   |Sì  |No   |Sì   |


     
> [!NOTE]
> CX 600 oppure ogni altro telefono Aries non supporta l'autenticazione a più fattori (MFA). Se si forza l'MFA, questi dispositivi non saranno in grado di effettuare l'accesso. Questi dispositivi devono utilizzare solo l'Org ID come forma di autenticazione.
 
## <a name="what-else-should-you-know"></a>Informazioni aggiuntive
Per le istruzioni dettagliate di configurazione, vedi la sezione [Distribuzione dei telefoni per Skype for Business Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Argomenti correlati
[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Vantaggi offerti dal Sistema telefonico](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
