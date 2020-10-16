---
title: Procedure di raccolta dati
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
description: Scopri in che modo Microsoft raccoglie i dati di censimento, utilizzo ed errore per comprendere l'utilizzo e i problemi relativi a Teams e Skype for Business e pianificare le migliorie del prodotto.
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651230"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Procedure di raccolta dati di Skype for Business e Microsoft Teams

Skype® for Business Server e Skype for Business Online, insieme alle app Skype for Business e Microsoft Teams, raccolgono i dati per aiutare Microsoft a comprendere il modo in cui vengono usati questi prodotti e i tipi di errore che si verificano, ad esempio gli errori di accesso. Queste informazioni sono utili per comprendere i modelli di utilizzo, pianificare nuove funzionalità e risolvere i problemi.

Mentre alcuni dati di utilizzo vengono raccolti automaticamente, è possibile raccogliere altri dati solo quando l'amministratore e/o l'utente sceglie di consentirlo. La raccolta dei dati rientra in queste tre categorie:

- Dati di censimento

- Dati di utilizzo

- Dati di segnalazione errore

## <a name="census-data"></a>Dati di censimento

I dati di censimento vengono acquisiti esclusivamente per fornire, supportare e migliorare Skype for Business. Microsoft Teams e Skype for Business Online. Include informazioni ambientali quali le versioni del sistema operativo e del dispositivo e le impostazioni geografiche e relative alla lingua. Include anche il numero di tentativi di accesso e di quelli non andati a buon fine. Seguono alcuni esempi specifici dei dati di censimento che vengono raccolti:

|**Tipo di dati**|**Esempio**|**Note**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |IT-IT  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |L'ID viene sottoposto ad hashing due volte: una volta nel client e nuovamente nel servizio di telemetria. L'hash garantisce che l'ID non possa essere collegato a un utente specifico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |L'ID dispositivo è un GUID generato in modo casuale una sola volta nel dispositivo e inviato al servizio di telemetria.  <br/> |

I dati di censimento NON contengono informazioni che identifichino l'organizzazione o gli utenti. Per ulteriori informazioni, consultare l'[Informativa sulla privacy di Skype® for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx).

I dati di censimento sono attivati per impostazione predefinita e non possono essere disattivati da amministratori o utenti finali.

## <a name="usage-data"></a>Dati di utilizzo

I dati di utilizzo includono informazioni come il numero di chiamate effettuate, il numero di messaggi istantanei inviati o ricevuti, il numero di riunioni a cui l'utente ha partecipato, la frequenza delle funzionalità usate e i problemi di stabilità.

I dati di utilizzo potrebbero contenere informazioni che identificano la propria organizzazione, ad esempio contoso.com. Seguono alcuni esempi specifici dei dati di censimento che vengono raccolti:

|**Tipo di dati**|**Esempio**|**Note**|
|:-----|:-----|:-----|
|Messaggio istantaneo inviato  <br/> |12  <br/> ||
|Messaggio istantaneo ricevuto  <br/> |5  <br/> ||
|Partecipa a una riunione (tentativi)  <br/> |5  <br/> ||
|Partecipa a una riunione (tentativi andati a buon fine)  <br/> |4  <br/> ||
|Verbale della riunione/chiamata  <br/> |30 minuti  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Questo è il nome dell'organizzazione registrata in Office 365 ed è trasmessa in testo non crittografato, che significa che non è offuscato.  <br/> |

I dati di utilizzo NON contengono informazioni che identifichino gli utenti.

La raccolta dei dati di utilizzo è attivata per impostazione predefinita, ma gli amministratori on premise possono disattivarla tramite l'impostazione dei criteri di gruppo DisableAutomaticSendTracing in Skype® for Business Server. La disattivazione di questa impostazione interessa tutti gli utenti dell'organizzazione. Per ulteriori informazioni, consultare [Configurare i criteri di bootstrap del client](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies).

Gli utenti finali non possono attivare o disattivare la raccolta dei dati di utilizzo.

Per l'app Riunioni Skype e le pagine Web Join Launcher, è possibile controllare la telemetria tramite questo criterio:

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

Per impostazione predefinita, questo criterio è impostato su false, quindi la raccolta della telemetria è disattivata per impostazione predefinita. Questa opzione è per pool e controlla tutti gli utenti che si connettono con l'app Riunioni Skype a una riunione ospitata nel server.

## <a name="error-reporting-data"></a>Dati di segnalazione errore

I dati di segnalazione errore possono contenere informazioni su prestazioni e affidabilità, configurazione dei dispositivi, qualità della connessione di rete, codici di errore, log degli errori ed eccezioni. Seguono alcuni esempi specifici dei dati di segnalazione errore che vengono raccolti:

|**Tipo di dati**|**Esempio**|**Note**|
|:-----|:-----|:-----|
|Direzione messaggio  <br/> |Ricevuto  <br/> ||
|Stato conversazione  <br/> |Inattivo  <br/> ||
|ID thread conversazione  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> |amosmarble <br/> |L'ID viene inviato in testo non crittografato, che viene sottoposto ad hashing dal servizio di telemetria prima di archiviarlo  <br/> |

I dati di segnalazione errore possono contenere anche informazioni personali, ad esempio l'indirizzo IP dell'utente e il Session Initiation Protocol Uniform Resource Identifier (SIP URI). Consultare l'[Informativa sulla privacy di Skype® for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) per una spiegazione dettagliata di quali dati vengono raccolti.

La segnalazione errore richiede due cose:

- L'impostazione del criterio di gruppo DisableAutomaticSendTracing è impostata su False nel server o nell'interfaccia di amministrazione del tenant (è lo stato predefinito). Per ulteriori informazioni, consultare [Configurare i criteri di bootstrap del client](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies).
    
- Gli utenti finali scelgono esplicitamente dalla scheda Generale (facendo clic sull'icona a forma di ingranaggio ![Un'icona che rappresenta un ingranaggio ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) si apre la finestra di dialogo **Opzioni** con la scheda **Generale** visualizzata) nel client Skype for business.
    
 
![Screenshot della casella di controllo della raccolta dei dati nella finestra di dialogo Opzioni](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Per l'app Riunioni Skype, MeetingUxEnableTelemetry controlla anche la segnalazione errori, anche se per gli arresti anomali in Windows, il controllo delle impostazioni del sistema Watson carica le informazioni sugli arresti anomali. Non è disponibile un'impostazione utente per l'app Riunioni Skype, come nella finestra di dialogo client desktop.

Consultare [Impostare le opzioni generali in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) per ulteriori informazioni.

Consultare [Configurare la rete per Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) per configurare la rete.

Se si usa Office 365 o Microsoft 365 gestiti da 21Vianet in Cina, vedere [Configurare la rete per Skype for Business Online gestito da 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).

## <a name="related-topics"></a>Argomenti correlati
[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
