---
title: Vota la mia chiamata in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Riepilogo: informazioni sulla caratteristica Vota la mia chiamata in Skype for Business Server.'
ms.openlocfilehash: e146bba647c9586d96682bf8056417630676726e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188708"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Vota la mia chiamata in Skype for Business Server

**Riepilogo:** Informazioni sulla caratteristica Vota la mia chiamata in Skype for Business Server.

Vota la mia chiamata è stata una nuova funzionalità nei client Skype for business 2015 e 2016 in Windows che offre alle aziende un modo per ottenere feedback dagli utenti finali.

La finestra Vota la mia chiamata offre un sistema di classificazione "stella" e i token predefiniti per le chiamate audio e video. Inoltre, gli amministratori possono abilitare un campo personalizzato per inviare commenti e suggerimenti.

Tasso di raccolta i dati delle chiamate non sono attualmente inclusi in un report di monitoraggio esistente, ma con un rapporto di monitoraggio distinto. I dati vengono raccolti nelle tabelle SQL a cui è possibile accedere eseguendo query SQL.

## <a name="rate-my-call-prerequisites"></a>Valutare i prerequisiti per le chiamate

Prima che gli utenti della distribuzione di Skype for Business Server possano accedere alla funzionalità chiamata, è necessario distribuire e configurare il set di componenti seguente:

-  È necessario avere installato Skype for Business Server (versione 9160 o successiva).

- Gli utenti possono installare e aggiornare l'ultima versione di Skype for business e chiedere anche di usare l'interfaccia utente di Skype for business.

- Gli utenti devono essere ospitati nel pool Front End di Skype for Business Server.

- È necessario disporre di un database di monitoraggio di Skype for Business Server distribuito e associato ai pool di Skype for Business Server.

- È consigliabile distribuire Call Quality Dashboard (Call Quality Dashboard).

## <a name="configure-rate-my-call"></a>Configurare Vota la chiamata

La caratteristica tasso di chiamata è abilitata per impostazione predefinita nel criterio client con le impostazioni seguenti:

- Valutare la percentuale di visualizzazione della chiamata-10%

- Vota la mia chiamata Consenti feedback degli utenti personalizzati disabilitati

Non è necessaria alcuna azione per abilitare la caratteristica di base, ma se si vuole ricevere un feedback personalizzato, è necessario abilitarlo separatamente. Il cmdlet di Windows PowerShell seguente è un esempio di abilitazione del feedback degli utenti finali personalizzati e della modifica dell'intervallo tra il 10% e il 80%.

```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>Tasso di accesso ai dati delle chiamate

I dati degli utenti vengono raccolti in due tabelle nel database di monitoraggio.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -Questa tabella contiene i risultati del polling dei token da parte degli utenti finali.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -Questa tabella contiene le definizioni di token.

Le definizioni di token sono codificate nel modo seguente:

|||
|:-----|:-----|
|1  <br/> |DistortedSpeech  <br/> |
|2  <br/> | ElectronicFeedback <br/> |
|3  <br/> | BackgroundNoise <br/> |
|4  <br/> |MuffledSpeech  <br/> |
|5  <br/> |Echo  <br/> |
|21  <br/> | FrozenVideo <br/> |
|22  <br/> | PixelatedVideo <br/> |
|23  <br/> | BlurryImage <br/> |
|24  <br/> | PoorColor <br/> |
|25  <br/> | DarkVideo <br/> |
|101  <br/> |Audio_SilentLocal  <br/> |
|102  <br/> |Audio_SilentRemote  <br/> |
|103  <br/> |Audio_Echo  <br/> |
|104  <br/> |Audio_BackgroundNoise  <br/> |
|105  <br/> |Audio_LowSound  <br/> |
|106  <br/> |Audio_Dropped  <br/> |
|107  <br/> |Audio_DistortedSpeech  <br/> |
|108  <br/> |Audio_Interrupted  <br/> |
|109  <br/> |Audio_Other  <br/> |
|201  <br/> |Video_NoLocalVideo  <br/> |
|202  <br/> |Video_NoRemoteVideo  <br/> |
|203  <br/> |Video_LowQuality  <br/> |
|204  <br/> |Video_FrozenVideo  <br/> |
|205  <br/> |Video_StoppedUnexpectedly  <br/> |
|206  <br/> |Video_DarkVideo  <br/> |
|207  <br/> |Video_NoAudioSync  <br/> |
|208  <br/> |Video_Other  <br/> |
|301  <br/> |Pstn_DialPad  <br/> |
|401  <br/> |SS_NoContentLocal  <br/> |
|402  <br/> |SS_NoContentRemote  <br/> |
|403  <br/> |SS_CantPresent  <br/> |
|404  <br/> |SS_LowQuality  <br/> |
|405  <br/> |SS_Freezing  <br/> |
|406  <br/> |SS_StoppedUnexpectedly  <br/> |
|407  <br/> |SS_LargeDelay  <br/> |
|408  <br/> |SS_Other  <br/> |
|501  <br/> |Reliabilty_Join  <br/> |
|502  <br/> |Reliabilty_Invite  <br/> |

 **[QoeMetrics]. [dbo]. [CallQualityFeedback]** Questa tabella contiene i risultati del polling da "stella" voto e feedback dei clienti, se abilitata.

I dati delle tabelle possono essere chiamati tramite una **query \* select from [Table.Name]** o tramite Microsoft SQL Server Management Studio.

È possibile usare le query SQL seguenti:

 **Audio**

```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 **Video**

```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a>Aggiornamento delle definizioni di token

Gli ultimi client Skype for business segnalano nuovi ID token di\> problema (100) che potrebbero non essere presenti in [QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef] tabella. Per aggiornare la tabella di database con le definizioni di token più recenti, il comando SQL seguente può essere eseguito nel database di monitoraggio tramite Microsoft SQL Server Management Studio. Questo comando sostituisce tutte le voci di [QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef] tabella.

```
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


