---
title: Pratiche di raccolta dati
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: Informazioni su come Microsoft raccoglie i dati di censimento, utilizzo e errore per comprendere i problemi relativi a team e Skype for business per pianificare i miglioramenti del prodotto.
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691532"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Procedure per la raccolta di dati in Skype for business e Microsoft Teams

Skype for Business Server e Skype for business online, insieme alle app Skype for business e Microsoft teams, raccolgono dati per aiutare Microsoft a capire come vengono usati questi prodotti e quali tipi di errori, ad esempio gli errori di accesso, si sono verificati. Queste informazioni consentono di comprendere i modelli di utilizzo, pianificare le nuove funzionalità e risolvere i problemi e risolvere i problemi.

Mentre alcuni dati di utilizzo vengono raccolti automaticamente, gli altri dati possono essere raccolti solo quando l'amministratore e/o l'utente sceglie di consentirlo. La raccolta dei dati rientra in queste tre categorie:

- Dati del censimento

- Dati sull'utilizzo

- Dati della segnalazione degli errori

## <a name="census-data"></a>Dati del censimento

I dati del censimento vengono acquisiti solo per consentire, supportare e migliorare Skype for business. Microsoft teams e Skype for business online. Include informazioni ambientali come le versioni del dispositivo e del sistema operativo e le impostazioni internazionali e della lingua. Include anche contatori per tentativi di accesso e errori. Ecco alcuni esempi specifici dei dati del censimento raccolti:

|**Tipo di dati**|**Esempio**|**Note**|
|:-----|:-----|:-----|
|NomeApp  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8,3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |L'ID viene hashato due volte: una volta sul client e di nuovo sul servizio di telemetria. L'hashing garantisce che l'ID non possa essere collegato a un utente specifico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |L'ID dispositivo è un GUID generato in modo casuale una volta sul dispositivo e inviato al servizio di telemetria.  <br/> |

I dati del censimento non contengono informazioni che identifichino l'organizzazione o gli utenti. Per altre informazioni, vedere l' [informativa sulla privacy di Skype for business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) .

I dati del censimento sono attivati per impostazione predefinita e non possono essere disattivati da amministratori o utenti finali.

## <a name="usage-data"></a>Dati sull'utilizzo

I dati sull'utilizzo includono informazioni come il numero di chiamate effettuate, il numero di messaggi istantanei inviati o ricevuti, il numero di riunioni Unite, la frequenza delle caratteristiche usate e i problemi di stabilità.

I dati di utilizzo possono contenere informazioni che identificano l'organizzazione, ad esempio contoso.com. Ecco alcuni esempi specifici dei dati di utilizzo raccolti:

|**Tipo di dati**|**Esempio**|**Note**|
|:-----|:-----|:-----|
|Messaggio istantaneo inviato  <br/> |12  <br/> ||
|Messaggi istantanei ricevuti  <br/> |5  <br/> ||
|Partecipare a una riunione (tentativi)  <br/> |5  <br/> ||
|Partecipare a una riunione (esito positivo)  <br/> |4  <br/> ||
|Minuti di chiamata/riunione  <br/> |30 minuti  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Questo è il nome dell'organizzazione registrata in Office 365 e viene trasmessa in testo non crittografato, quindi non è offuscata.  <br/> |

I dati di utilizzo non contengono informazioni che identifichino gli utenti.

La raccolta dei dati di utilizzo è attiva per impostazione predefinita, ma gli amministratori locali possono disattivarla usando l'impostazione dei criteri di gruppo di DisableAutomaticSendTracing in Skype for Business Server. La disattivazione di questa impostazione interessa tutti gli utenti dell'organizzazione. Per altre informazioni, vedere [configurare i criteri di avvio del client](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .

Gli utenti finali non possono attivare o disattivare la raccolta dati sull'utilizzo.

Per le app riunioni Skype e le pagine Web di avvio join, il modo per controllare la telemetria è attraverso questo criterio:

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

Questo criterio viene impostato su false, quindi la raccolta di telemetria è disinserita per impostazione predefinita. Questa impostazione è per pool e controlla tutti gli utenti che si connettono con l'app riunioni Skype a una riunione ospitata nel server.

## <a name="error-reporting-data"></a>Dati della segnalazione degli errori

I dati di segnalazione degli errori possono includere informazioni su prestazioni e affidabilità, configurazione dei dispositivi, qualità della connessione di rete, codici di errore, registri degli errori ed eccezioni. Ecco alcuni esempi specifici di dati di segnalazione degli errori raccolti:

|**Tipo di dati**|**Esempio**|**Note**|
|:-----|:-----|:-----|
|Direzione del messaggio  <br/> |In arrivo  <br/> ||
|Stato conversazione  <br/> |Inattivo  <br/> ||
|ID thread di conversazione  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|UserID  <br/> |amosmarble <br/> |L'ID viene inviato in testo non crittografato, a cui il servizio di telemetria viene hashato prima di archiviarlo  <br/> |

I dati di segnalazione degli errori possono contenere anche informazioni personali, ad esempio l'indirizzo IP dell'utente e l'URI SIP (Uniform Resource Identifier) del protocollo di avvio della sessione. Vedere l' [informativa sulla privacy di Skype for business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) per una spiegazione dettagliata delle raccolte.

La segnalazione degli errori richiede due elementi:

- L'impostazione di criteri di gruppo di DisableAutomaticSendTracing è impostata su false nel server o nell'interfaccia di amministrazione del tenant (questo è lo stato predefinito). Per altre informazioni, vedere [configurare i criteri di avvio del client](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .
    
- Gli utenti finali scelgono individualmente l'opt-in dalla scheda generale (fare clic sull'icona a ingranaggio ![ un'icona che rappresenta un ingranaggio ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) e quindi la finestra di dialogo **Opzioni** si apre con la scheda **generale** visualizzata) nel client Skype for business.
    
 
![Screenshot della casella di controllo raccolta dati nella finestra di dialogo Opzioni](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Per l'app riunioni Skype, MeetingUxEnableTelemetry controlla anche la segnalazione degli errori, anche se per gli arresti anomali in Windows, il controllo delle impostazioni di Watson carica le informazioni sull'arresto anomalo. Non sono disponibili impostazioni utente per l'app riunioni Skype, come nella finestra di dialogo client desktop.

Per altre informazioni, vedere [impostare le opzioni generali in Skype for business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) .

Per configurare la rete, è possibile vedere [configurare la rete per Skype for business online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) .

Se si usa Microsoft 365 o Office 365 gestito da 21Vianet in Cina, vedere [configurare la rete per Skype for business online gestito da 21ViaNet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).

## <a name="related-topics"></a>Argomenti correlati
[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
