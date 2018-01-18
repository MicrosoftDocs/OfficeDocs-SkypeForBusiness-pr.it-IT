---
title: Configurare le audioconferenze per Skype for Business e Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: 'Informazioni su come configurare servizi di conferenza telefonica o audio per le persone nell''azienda che desiderano partecipare a conferenze telefoniche mediante un telefono. '
ms.openlocfilehash: 6d8fae08a5dc8e6a1cf6bc05b458840c47fc83ed
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurare le audioconferenze per Skype for Business e Microsoft Teams

In alcuni casi gli utenti dell'organizzazione saranno necessario utilizzare un telefono per chiamare una riunione. Skype per le aziende e Teams Microsoft includono la funzionalità di audioconferenza per solo questa situazione! Le persone possono chiamare Skype per le riunioni aziendali o Microsoft Teams mediante un telefono, anziché utilizzare il Skype per applicazioni aziendali o Microsoft Teams su un dispositivo mobile o PC. 
  
È sufficiente configurare conferenze Audio per gli utenti che prevedono di programmare o condurre riunioni. I partecipanti alla riunione che effettua la chiamata non è necessario alcun licenze assegnate loro o altre impostazioni.
  
Per le domande frequenti sui servizi di conferenza Audio, vedere [domande frequenti di conferenze Audio](audio-conferencing-common-questions.md).
  
## <a name="step-1-buy-and-assign-licenses"></a>Passaggio 1: Acquistare e assegnare licenze
<a name="__top"> </a>

È necessario essere un [ruoli di amministratore su Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) per eseguire questo passaggio.
  
1. Scoprire se audioconferenza in Office 365 è disponibile nel paese/area geografica. [Disponibilità paese e alle aree per le conferenze Audio e la chiamata Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). 
    
2. Scopri le licenze che è necessario acquistare per conferenze Audio e il relativo verrà costo. Vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)e acquistare le licenze. 
    
3. [Assegnare o rimuovere licenze per Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) è stato acquistato per gli utenti dell'organizzazione che intende pianificazione o lead riunioni.
    
4. Se è stato acquistato Communications crediti licenze e le licenze di componente aggiuntivo **Per conferenze Audio** , assegnarli troppo. Per ulteriori informazioni, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a>Passaggio 2: Scegliere il provider di servizi di conferenza audio
<a name="__top"> </a>

Un provider di servizi di conferenza audio fornisce un *ponte per conferenze audio*. Bridge conferenza imposta i numeri di telefono di accesso esterno, pin e gli ID conferenza per le riunioni. Decidere se utilizzare Microsoft o un provider di servizi di conferenza audio di terze parti:
  
> [!NOTE]
> Gli utenti di Microsoft Teams non utente un provider di servizi di conferenza audio di terze parti. 
  
- **Microsoft come provider di servizi di conferenza audio**: se si desidera che la soluzione più semplice per le conferenze audio, scegliere Microsoft come provider di servizi di conferenza audio.
    
- **Terze parti come provider di servizi di conferenza audio**: se si partecipa a un paese dove audioconferenze con accesso esterno in Office 365 non è disponibile, la qualità del servizio non è grande a causa della posizione o si dispone di un contratto esistente, scegliere un audio di terze parti provider di servizi di conferenza. Per trovare un provider, andare a [Individuare Microsoft](http://go.microsoft.com/fwlink/?LinkId=797530).
    
> [!TIP]
> All'interno dell'organizzazione, è possibile avere alcune persone che utilizzano Microsoft come i provider di servizi di conferenza audio gli utenti che utilizzano un provider di terze parti. Ma sarà più complicato consente di impostare e gestire. 
  
Per un confronto dettagliato tra Microsoft come provider di audio e un provider di terze parti, vedere [confronto tra i provider di servizi di conferenza audio](compare-audio-conferencing-providers.md). 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a>Passaggio 3: Assegnare il provider di servizi di conferenza audio agli utenti di condurre o pianificare riunioni
<a name="__top"> </a>

Ora che si è deciso per il provider di servizi di conferenza audio, è necessario assegnare il provider alle persone all'interno dell'organizzazione condurre o pianificare riunioni. Effettuare una delle operazioni seguenti: 
  
- [Assegnare Microsoft come provider di servizi di conferenza audio](assign-microsoft-as-the-audio-conferencing-provider.md).
    
- [Assegnare una terza parte come provider di servizi di conferenza audio](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
## <a name="step-4-set-up-meeting-invitations"></a>Passaggio 4: Impostare le convocazioni di riunione
<a name="__top"> </a>

La procedura seguente è **facoltativo**, ma una quantità elevata di admins like eseguirle:
  
1. [Personalizza convocazioni di riunione](../set-up-skype-for-business-online/customize-meeting-invitations.md). I numeri di accesso impostate per l'utente verranno aggiunta automaticamente per gli inviti alle riunioni inviati ai partecipanti. Tuttavia, è possibile aggiungere Guida personalizzata e collegamenti legali, un messaggio di testo e immagine piccola società.
    
2. [Set di numeri di telefono per conferenze Audio per inclusi in inviti agli organizzatori della riunione](set-the-phone-numbers-included-on-invites.md). Questo è il numero di telefono che verrà visualizzata in alle riunioni pianificate dall'utente.
    
3. [Impostare le lingue di operatore automatico per le conferenze Audio](set-auto-attendant-languages-for-audio-conferencing.md) che utilizza l'operatore automatico di audioconferenza per saluti salutare un chiamante quando si effettua la chiamata a un numero di telefono di audioconferenza. Questo passaggio si applica solo se si utilizza Microsoft come provider di audio.
    
4. [Impostare la lunghezza del PIN per le riunioni di conferenze Audio](set-the-pin-length-for-audio-conferencing-meetings.md).
    
> [!NOTE]
> Questa funzionalità non è ancora disponibile per i clienti con Office 365 gestito dal 21Vianet in Cina. Per ulteriori informazioni, vedere [informazioni su Office 365 gestito dal 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE). 
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Argomenti correlati

[Domande più comuni di servizi di conferenza audio](audio-conferencing-common-questions.md)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numeri di telefono per le conferenze Audio](phone-numbers-for-audio-conferencing.md)
  
[Impostare le opzioni per riunioni online e conferenze telefoniche](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

