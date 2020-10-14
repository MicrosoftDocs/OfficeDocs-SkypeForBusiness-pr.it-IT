---
title: Conferenze in rete per servizi di audioconferenza
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Di seguito vengono illustrate le funzionalità di anteprima aperta per la rete per i servizi di audioconferenza.
ms.openlocfilehash: 18bd33281379efe7dd2e64019e20a66a2dbec920
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444212"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>Aprire l'anteprima dei servizi di conferenza in rete per l'audioconferenza

L'anteprima aperta dei servizi di conferenza in rete è disponibile per tutti i clienti. I servizi di conferenza in rete consentono alle organizzazioni di inviare chiamate di audioconferenza in ingresso e in uscita ai numeri di accesso esterno Microsoft tramite routing diretto. Questa funzionalità non è destinata a estendere il supporto dei servizi di audioconferenza ai numeri di accesso esterno di terze parti. I servizi di conferenza in rete non sono supportati se vengono usati per instradare le chiamate in ingresso al servizio di audioconferenza tramite i numeri di telefono di accesso esterno di terze parti.

In questo articolo vengono illustrati i prerequisiti e i passaggi di configurazione necessari per abilitare i servizi di conferenza in rete per l'organizzazione.

> [!IMPORTANT]
> I servizi di conferenza in rete non devono essere distribuiti con qualsiasi dispositivo di telefonia in India.
  
## <a name="prerequisites"></a>Prerequisiti

Prima di configurare i servizi di conferenza in rete, verificare che l'organizzazione soddisfi i prerequisiti seguenti: 

- Assicurarsi che tutti gli utenti dell'organizzazione abilitati o abilitati per i servizi di audioconferenza utilizzino team per tutte le riunioni. Il routing delle chiamate di conferenza audio in ingresso e in uscita tramite servizi di conferenza in rete è supportato solo per le riunioni di team.

- Assegnare licenze di audioconferenza a tutti gli utenti che utilizzeranno i servizi di conferenza in rete.

- Configurare il servizio di audioconferenza. Per altre informazioni, vedere [configurare le conferenze audio per Microsoft teams](set-up-audio-conferencing-in-teams.md).

- Configurare il session border controller (SBC) per il routing diretto. Per altre informazioni, vedere [pianificare il routing diretto](direct-routing-plan.md) e [configurare il routing diretto](direct-routing-configure.md). 

  Se si sta configurando un routing diretto solo per i servizi di audioconferenza, è necessario completare solo il passaggio 1: connettere il SBC per i servizi di conferenza in rete.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Abilitare il routing delle chiamate con accesso esterno a Microsoft Audio Conferencing tramite routing diretto 

Per instradare le chiamate con accesso esterno effettuate dagli utenti locali al servizio di audioconferenza tramite routing diretto, è necessario configurare le regole di routing appropriate per i sistemi PBX (SBCs e Private Branch Exchange).

È necessario configurare l'equipaggiamento per la telefonia dei siti per instradare le chiamate a qualsiasi numero di servizio del Bridge di conferenza della propria organizzazione tramite un trunk di routing diretto.

Puoi trovare i numeri di servizio nell'interfaccia di amministrazione di teams in **riunioni-> Bridge per conferenze** o usando il cmdlet di PowerShell per Skype for business online Get-CsOnlineDialInConferencingBridge. Per altre informazioni, vedere un elenco di numeri di servizi di [audioconferenza in Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Questa caratteristica non è disponibile per gli utenti con la licenza per i servizi di audioconferenza pay-per-minute.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Abilitare il routing delle chiamate di chiamata in uscita dei team tramite routing diretto

Le chiamate di chiamata in uscita per le riunioni di team vengono avviate dall'interno di una riunione dell'organizzazione a numeri PSTN, tra cui chiamate e chiamate per trasferire i nuovi partecipanti a una riunione. 

Per abilitare il routing delle chiamate in uscita del team tramite routing diretto, è necessario creare e assegnare un criterio di routing per i servizi di audioconferenza denominato "OnlineAudioConferencingRoutingPolicy". 

Il criterio OnlineAudioConferencingRoutingPolicy equivale alle chiamate PSTN di CsOnlineVoiceRoutingPolicy per 1:1 tramite routing diretto. I criteri di OnlineAudioConferencingRoutingPolicy possono essere gestiti usando i cmdlet seguenti:

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Per altre informazioni sul routing per il routing diretto, vedere [configurare il routing vocale per il routing diretto](direct-routing-voice-routing.md).


Per abilitare il routing delle chiamate di chiamata in uscita tramite routing diretto, è necessario: 

- Configurare i criteri di routing per i servizi di audioconferenza
- Configurare il routing nell'attrezzatura per la telefonia dell'organizzazione
- Opzionale Configurare un dial plan

Le chiamate in uscita dalle riunioni di team vengono dal numero di servizio predefinito sul Bridge di conferenza. Per altre informazioni sul numero di servizio predefinito del Bridge per i servizi di audioconferenza, vedere [modificare i numeri di telefono nel Bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)per audioconferenza.

### <a name="configure-audio-conferencing-routing-policies"></a>Configurare i criteri di routing per i servizi di audioconferenza

Il criterio di routing per i servizi di audioconferenza OnlineAudioConferencingRoutingPolicy determina quali chiamate di chiamata in uscita vengono instradate ai trunk di routing diretto. Se si ha familiarità con i criteri di CsOnlineVoiceRoutingPolicy, questo criterio funziona in modo molto simile.

I passaggi seguenti sono necessari per configurare i criteri di routing per i servizi di audioconferenza:
1.  Creare usi PSTN
2.  Configurare le route vocali
3.  Creare criteri di routing vocale per i servizi di audioconferenza
4.  Assegnare un criterio agli utenti


#### <a name="create-pstn-usages"></a>Creare usi PSTN

Gli usi PSTN sono insiemi di route vocali. Quando una chiamata in uscita viene avviata dalla riunione di un organizzatore specifico, verranno usate le route vocali per determinare il percorso di routing della chiamata in base agli usi PSTN associati all'utente tramite i criteri di routing vocale dell'utente.

Puoi creare un uso PSTN usando il cmdlet "set-CsOnlinePstnUsage". Per esempio:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurare le route vocali

Le route vocali determinano il gateway PSTN che deve essere usato per instradare una chiamata in base al numero di telefono composto da una riunione teams. Le route vocali determinano il gateway PSTN che deve essere usato per instradare una determinata chiamata abbinando il numero di telefono composto da una riunione di teams con uno schema Regex. Quando si crea una route vocale, la route deve essere associata a uno o più usi PSTN.

È possibile creare una route vocale e definire le espressioni regolari e i gateway da associare alla route vocale usando il cmdlet "New-CsOnlineVoiceRoute". Per esempio:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Creare criteri di routing vocale per i servizi di audioconferenza

I criteri di routing vocale per i servizi di audioconferenza determinano le possibili route che possono essere usate per instradare una chiamata proveniente dalle riunioni di un organizzatore in base al numero di telefono di destinazione della chiamata in uscita della riunione. I criteri di routing vocale per i servizi di audioconferenza sono associati a uno o più usi PSTN, che a loro volta determinano le possibili rotte che verranno usate per le chiamate di chiamata in uscita degli organizzatori associati al criterio.

Puoi creare un criterio di routing vocale per i servizi di audioconferenza usando il cmdlet "New-CsOnlineAudioConferencingRoutingPolicy". Per esempio:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Dopo che i criteri sono stati assegnati a un utente e quando viene avviata una chiamata esterna a una riunione da una delle riunioni dell'utente, vengono valutate le route vocali negli usi PSTN associati all'organizzatore tramite i criteri di routing vocale dell'utente. Se la destinazione di chiamata in uscita della riunione corrisponde a una Regex in una delle route vocali associate all'organizzatore, la chiamata di accesso esterno alla riunione verrà instradata al gateway PSTN definito nella route vocale. Se la destinazione delle chiamate di chiamata in uscita della riunione non corrisponde a nessuna delle route vocali associate all'organizzatore, la chiamata esterna della riunione verrà instradata da Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Assegnare un criterio agli utenti

Dopo aver definito i criteri di routing per i servizi di audioconferenza, è ora possibile assegnarli agli utenti. Dopo aver assegnato i criteri, le chiamate di chiamata in uscita verranno valutate per determinare il percorso di routing. I criteri di routing per i servizi di audioconferenza vengono sempre valutati in base all'organizzatore della riunione, indipendentemente dall'utente nella riunione che avvia una chiamata esterna alla riunione.

Puoi assegnare un criterio di routing vocale per i servizi di audioconferenza a un utente usando il cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Ad esempio:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurare il routing nell'attrezzatura per la telefonia dell'organizzazione

Nell'attrezzatura per la telefonia dell'organizzazione devi assicurarti che le chiamate di chiamata in uscita della riunione instradate tramite il routing diretto vengano instradate alla destinazione in rete prevista.


### <a name="optional-configure-a-dial-plan"></a>Opzionale Configurare un dial plan

Un dial plan è un set di regole di normalizzazione che traducono i numeri di telefono composti da un singolo utente in un formato alternativo (in genere E. 164) ai fini dell'autorizzazione alle chiamate e del routing delle chiamate.

Per impostazione predefinita, gli utenti del team possono effettuare la chiamata in uscita per i numeri PSTN nel formato E. 164, ovvero + \<country code\> \<number\> . Tuttavia, i dial plan possono essere usati per consentire agli utenti di chiamare numeri di telefono in altri formati, ad esempio estensioni a 4 cifre.

Se si vuole abilitare le chiamate basate su estensioni tramite i servizi di conferenza in rete, è possibile configurare i piani di chiamata in modo che corrispondano al modello di chiamata dell'estensione agli intervalli di numeri di telefono del numero di telefono dell'organizzazione. Per configurare i dial plan, vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md).


## <a name="known-issues-in-open-preview"></a>Problemi noti nell'anteprima aperta

Di seguito è riportato un elenco dei problemi noti attualmente presenti nella versione Open Preview dei servizi di conferenza in rete. Microsoft sta lavorando per risolvere questi problemi.

| Problema | Soluzione |
| :--- | :--- |
| Le chiamate con accesso esterno con ID chiamante anonimo/nascosto instradati attraverso i servizi di conferenza di rete non possono essere connessi alla riunione. | Se possibile, imposta una configurazione in PBX o SBC per inviare sempre un ID chiamante per le chiamate instradate tramite servizi di conferenza in rete.|
| In alcuni casi, il messaggio di benvenuto che viene riprodotto agli utenti quando effettua l'accesso al servizio ("Benvenuto nel servizio di audioconferenza...") viene troncato e gli utenti non sentono la parola "benvenuto".| Al momento non esistono soluzioni alternative per questo problema. |




## <a name="related-topics"></a>Argomenti correlati


