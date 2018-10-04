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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Informazioni su quali telefoni di Polycom, HP e Mitel utilizzano Skype for Business e sulle licenze necessarie. '
ms.openlocfilehash: 8b218161268855a1b89aa54fd0e40c4b308db40d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371566"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Ottenere telefoni per Skype for Business online

Skype for Business Online qualifies and supports desktop phones for users who want to have a traditional phone experience, rather than use the Skype for Business app. This topic covers the phones and firmware versions that are supported for use in Skype for Business Online and other information that can help you when you are setting up phones in your organization.
  
Per ottenere gli aggiornamenti più recenti e la maggior parte delle informazioni aggiornate sui dispositivi supportati, vedere [Skype per il catalogo dei dispositivi Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
## <a name="supported-phones"></a>Telefoni supportati

Per Skype per gli utenti aziendali Online, è possibile scegliere tra diversi modelli di *certificati per Skype per i telefoni aziendali* e telefoni che eseguono Lync Phone Edition (LPE) elencato in Skype per categoria Business Online in [Skype per dispositivo Business Catalogo](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
Microsoft è collaborazione e stretta collaborazione con Polycom, Yealink e AudioCodes per sviluppare e la certificazione un'ampia gamma di dispositivi tramite Partner IP Phone programma (PIP) per il sistema telefonico in Office 365 e Skype per Business Server.
  
When ordering new phones for Skype for Business, it is important to buy phones with the *right product ID*. These product IDs will ensure that the phones you receive have the Skype for Business Online qualified version already installed.
  
|||
|:-----|:-----|
|**Partner telefonico** <br/> |**ID prodotto specifico Skype for Business** <br/> |
|Polycom  <br/> |ID prodotto - 019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Per maggiori dettagli sui telefoni Polycom, consulta [Soluzioni vocali per Microsoft](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
  
Per maggiori dettagli sui telefoni Yealink, consulta [Telefoni IP per Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Per ulteriori informazioni sul AudioCodes telefoni, vedere [Skype per i telefoni IP Business](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Phone Edition is supported with Skype for Business Online, but not with Microsoft Teams. Mainstream support for the LPE platform ended by April/10/2014, with extended support until April/11/2023 to align with the product support lifecycle of Lync Server 2013. See [Microsoft Product Lifecycle](https://support.microsoft.com/en-us/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) for details on the LPE lifecycle. LPE CAP models aren't supported with Skype for Business Online.
>
> Later this year, Office 365 will not support any version of TLS older than 1.2. Since the underlying operating system of LPE does not support TLS 1.2, LPE will not be supported to connect to Office 365 anymore. See [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365) for more information.
  
## <a name="supported-firmware"></a>Firmware supportate

Si tratta della versione software minima necessaria per i telefoni supportati per l'utilizzo con Sistema telefonico in Office 365:
  
||||
|:-----|:-----|:-----|
|**Tipo di telefono** <br/> |**Firmware minimo** <br/> |**Data di rilascio** <br/> |
|Ottimizzato (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Maggio 2015  <br/> |
|Serie Polycom VVX certificata  <br/> |5.4.0A  <br/> |Dicembre 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Febbraio 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Dicembre 2016  <br/> |
   
> [!NOTE]
> I telefoni Lync Phone Edition (LPE) configurati per la distribuzione locale devono essere aggiornati alla versione minima o successiva del firmware richiesta prima di trasferire gli utenti in Skype for Business online. Se il trasferimento degli utenti dalla distribuzione locale a Skype for Business online avviene prima dell'aggiornamento del firmware nei telefoni, questi telefoni non potranno connettersi a Skype for Business online. 
  
## <a name="required-licenses"></a>Licenze necessarie

Skype for Business Online doesn't require any additional Microsoft license other than the user licenses. To learn more about the required user licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Manufacturer licensing models might vary between open SIP and Skype for Business Certified firmware. If you are repurposing a certified model with an Open SIP firmware, you will need to verify firmware license requirements with the manufacturer.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype per set di caratteristiche di Business Online connessi telefoni

Per dispositivo completa caratteristiche e funzionalità, controllare le guide utente produttore.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Funzionalità** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|Accedi con le credenziali utente  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Accesso tramite PC (accoppiamento), solo per Windows  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Accedi con (accesso Web)  <br/>  <br/> **Nota:** Controllare la matrice di supporto nella Guida alla distribuzione.           |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Partecipa a una riunione con un singolo clic  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Clic per comporre (accoppiamento)  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Controlli per le riunioni  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Casella vocale visuale  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Blocco telefono  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Aggiornamento del dispositivo  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Provisioning in banda  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|QoE  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Invio registro  <br/> <br/> **Nota:** Attualmente, tutti i registri vengono caricati al team di supporto Microsoft di sola lettura. accesso cliente alle telefonate non sono ancora disponibili.           |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Autenticazione moderna  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Numero di emergenza multiplo  <br/> |Sì  <br/> |No  <br/> |No  <br/> |Sì  <br/> |
|Integrazione calendario Exchange*  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> <br/> **Nota:** È necessario legare PC           |
|Integrazioni presenza  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Elenco aziendale  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Delega  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Integrazione immagine contatto  <br/> |No  <br/> |Sì  <br/> |No  <br/> |Sì  <br/> |
||||||

     
> [!NOTE]
> CX 600 or any other Aries phones don't support multifactor authentication (MFA). If you force MFA, these devices will fail to sign-in. These devices must use only Org ID for authetication.
 
## <a name="what-else-should-you-know"></a>Quali altre informazioni devi conoscere?
Per le istruzioni dettagliate di configurazione, vedi la sezione [Distribuzione dei telefoni per Skype for Business Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Argomenti correlati
[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](../getting-service-phone-numbers.md)

[Ecco cosa offre il Sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 