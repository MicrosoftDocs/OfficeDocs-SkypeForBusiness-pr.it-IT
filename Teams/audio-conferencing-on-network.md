---
title: Servizi di conferenza in rete per audioconferenza
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Di seguito sono descritte le funzionalità in rete per le audioconferenze.
ms.openlocfilehash: 63a76bd8cb7765816c417d60640d931acbe856bae7c1c7c3531e9598524e59c3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351226"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>Servizi di conferenza in rete per audioconferenza

Le conferenze in rete consentono alle organizzazioni di inviare chiamate di audioconferenza in ingresso e in uscita ai numeri di accesso esterno Microsoft tramite Routing diretto. Questa funzionalità non è progettata per estendere il supporto delle audioconferenze ai numeri di accesso esterno di terze parti. Le conferenze in rete non sono supportate se vengono usate per instradare le chiamate in ingresso al servizio di audioconferenza tramite numeri di telefono con accesso esterno di terze parti o chiamate in uscita alla rete PSTN da Microsoft Audio Conferencing Bridge. 

Questo articolo descrive i prerequisiti e i passaggi di configurazione necessari per abilitare le conferenze in rete per l'organizzazione.

> [!IMPORTANT]
> Le conferenze in rete NON devono essere distribuite con apparecchiature di telefonia in India.
  
## <a name="prerequisites"></a>Prerequisiti

Prima di configurare le conferenze in rete, assicurarsi che l'organizzazione soddisfi i prerequisiti seguenti: 

- Assicurarsi che tutti gli utenti dell'organizzazione abilitati o abilitati per le audioconferenze utilizzino Teams per tutte le riunioni. L'instradamento delle chiamate di audioconferenza in ingresso e in uscita tramite conferenze in rete è supportato solo per le Teams riunioni.

- Assegnare licenze di audioconferenza a tutti gli utenti che usano servizi di conferenza in rete.

- Configurare il servizio di audioconferenza. Per altre informazioni, vedere [Configurare le audioconferenze per Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Configurare il session border controller (SBC) per il routing diretto. Per altre informazioni, vedere [Pianificare il routing diretto](direct-routing-plan.md) e Configurare il routing [diretto.](direct-routing-configure.md) 

  Se si configura il routing diretto solo ai fini delle audioconferenze, è necessario completare solo "Passaggio 1: Connessione SBC" per le conferenze in rete.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Abilitare il routing delle chiamate con accesso esterno alle audioconferenze Microsoft tramite routing diretto 

Per instradare le chiamate con accesso esterno effettuate dagli utenti locali al servizio di audioconferenza tramite Routing diretto, è necessario configurare le regole di routing appropriate per gli SBC e i sistemi PBC (Private Branch Exchange).

È necessario configurare le apparecchiature di telefonia dei siti per instradare le chiamate a qualsiasi numero di servizio del bridge di conferenza dell'organizzazione tramite un trunk di routing diretto.

È possibile trovare i numeri di servizio nell Teams intervalla di amministrazione in Riunioni **-> Conferencing Bridges** o usando il cmdlet di PowerShell di Skype for Business Online Get-CsOnlineDialInConferencingBridge. Per altre informazioni, vedere un elenco di numeri [di audioconferenza in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Questa funzionalità non è disponibile per gli utenti con la licenza di audioconferenza a pagamento al minuto.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Abilitare l'instradamento Teams chiamate in uscita tramite Routing diretto

Teams le chiamate in uscita di una riunione vengono avviate dall'interno di una riunione dell'organizzazione ai numeri PSTN, incluse le chiamate con chiamata al telefono e le chiamate per portare i nuovi partecipanti a una riunione. 

Per abilitare Teams routing esterno delle riunioni tramite Routing diretto agli utenti in rete, è necessario creare e assegnare un criterio di routing delle audioconferenze denominato "OnlineAudioConferencingRoutingPolicy". 

Il criterio OnlineAudioConferencingRoutingPolicy equivale al criterio CsOnlineVoiceRoutingPolicy per le chiamate PSTN 1:1 tramite routing diretto. Il criterio OnlineAudioConferencingRoutingPolicy può essere gestito usando i cmdlet seguenti:

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Per altre informazioni sul routing per il routing diretto, vedere [Configurare il routing vocale per il routing diretto.](direct-routing-voice-routing.md)


Per abilitare l'instradamento delle chiamate in uscita delle riunioni tramite Routing diretto, è necessario: 

- Configurare i criteri di routing delle audioconferenze
- Configurare il routing nell'apparecchiatura di telefonia dell'organizzazione
- (Facoltativo) Configurare un piano di chiamata

Le chiamate in uscita provenienti Teams riunioni sono provenienti dal numero di servizio predefinito sul bridge di conferenza. Per altre informazioni sul numero di servizio predefinito del bridge di audioconferenza, vedere Modificare i numeri di telefono [nel bridge di audioconferenza.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

### <a name="configure-audio-conferencing-routing-policies"></a>Configurare i criteri di routing delle audioconferenze

Il criterio di routing delle audioconferenze OnlineAudioConferencingRoutingPolicy determina quali chiamate in uscita per le riunioni vengono instradati ai trunk di routing diretto. Se si ha familiarità con il criterio CsOnlineVoiceRoutingPolicy, questo criterio funziona in modo molto simile.

Per configurare i criteri di routing delle audioconferenze, sono necessari i passaggi seguenti:
1.  Creare utilizzi PSTN
2.  Configurare le route vocali
3.  Creare criteri di routing vocale per le audioconferenze
4.  Assegnare un criterio agli utenti


#### <a name="create-pstn-usages"></a>Creare utilizzi PSTN

Gli utilizzi PSTN sono raccolte di route vocali. Quando viene avviata una chiamata in uscita dalla riunione di un determinato organizzatore, le route vocali verranno usate per determinare il percorso di routing della chiamata in base agli utilizzi PSTN associati all'utente tramite i criteri di routing vocale dell'utente.

È possibile creare un utilizzo PSTN usando il cmdlet "Set-CsOnlinePstnUsage". Per esempio:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurare le route vocali

Le route vocali determinano il gateway PSTN che deve essere usato per instradare una chiamata in base al numero di telefono composto da una Teams riunione. Le route vocali determinano il gateway PSTN che deve essere usato per instradare una determinata chiamata abbinando il numero di telefono composto da una riunione Teams con uno schema regex. Quando si crea una route vocale, la route deve essere associata a uno o più utilizzi PSTN.

È possibile creare una route vocale e definire l'espressione regolare e i gateway da associare alla route vocale usando il cmdlet "New-CsOnlineVoiceRoute". Per esempio:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Creare criteri di routing vocale per le audioconferenze

I criteri di routing vocale per i servizi di audioconferenza determinano le possibili route che possono essere usate per instradare una chiamata proveniente dalle riunioni di un organizzatore in base al numero di telefono di destinazione della chiamata in uscita della riunione. I criteri di routing vocale per i servizi di audioconferenza sono associati a uno o più utilizzi PSTN, che a loro volta determinano le possibili route che verranno usate per le chiamate in uscita della riunione degli organizzatori associati al criterio.

È possibile creare un criterio di routing vocale per le audioconferenze usando il cmdlet "New- CsOnlineAudioConferencingRoutingPolicy". Per esempio:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Dopo l'assegnazione del criterio a un utente e l'avvio di una chiamata in uscita da una delle riunioni dell'utente, verranno valutate le route vocali negli utilizzi PSTN associati all'organizzatore tramite i criteri di routing vocale dell'utente. Se la destinazione della chiamata in uscita della riunione corrisponde a un'espressione regolare in una delle route vocali associate all'organizzatore, la chiamata in uscita della riunione verrà instradata al gateway PSTN definito nella route vocale. Se la destinazione della chiamata in uscita della riunione non corrisponde a nessuna delle route vocali associate all'organizzatore, la chiamata in uscita della riunione verrà instradata da Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Assegnare un criterio agli utenti

Dopo aver definito i criteri di routing delle audioconferenze, è ora possibile assegnarli agli utenti. Dopo l'assegnazione dei criteri, le chiamate in uscita della riunione verranno valutate per determinare il percorso di routing. I criteri di routing dei servizi di audioconferenza vengono sempre valutati in base all'organizzatore della riunione, indipendentemente dall'utente nella riunione che avvia una chiamata in uscita della riunione.

È possibile assegnare un criterio di routing vocale delle audioconferenze a un utente usando il cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Ad esempio:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurare il routing nelle apparecchiature di telefonia dell'organizzazione

Nelle apparecchiature di telefonia dell'organizzazione è necessario assicurarsi che le chiamate in uscita della riunione instradati tramite Routing diretto siano indirizzate alla destinazione in rete prevista.


### <a name="optional-configure-a-dial-plan"></a>(Facoltativo) Configurare un piano di chiamata

Un piano di chiamata è un set di regole di normalizzazione che traducono i numeri di telefono digitati da un singolo utente in un formato alternativo (in genere E.164) ai fini dell'autorizzazione delle chiamate e del routing delle chiamate.

Per impostazione predefinita, Teams gli utenti possono effettuare chiamate in uscita verso numeri PSTN in formato E.164, ad esempio + \<country code\> \<number\> . Tuttavia, i piani di chiamata possono essere usati per consentire agli utenti di comporre numeri di telefono in altri formati, ad esempio estensioni a 4 cifre.

Se si vuole abilitare la composizione basata sull'interno tramite servizi di conferenza telefonica in rete, è possibile configurare i piani di chiamata in modo che corrispondano allo schema di composizione dell'interno agli intervalli di numeri di telefono del numero di telefono dell'organizzazione. Per configurare i dial plan, vedere [Creare e gestire i dial plan.](create-and-manage-dial-plans.md)

## <a name="related-topics"></a>Argomenti correlati


