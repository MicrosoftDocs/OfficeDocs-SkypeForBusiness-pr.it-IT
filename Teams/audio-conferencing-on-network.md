---
title: Servizi di conferenza in rete per audioconferenze
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
description: Di seguito viene descritta la funzionalità Open Preview per le audioconferenze in rete.
ms.openlocfilehash: 1ae61034ef083c89e14c67cef0effa1c105de758
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031862"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>Anteprima delle conferenze in rete aperte per le audioconferenze

L'anteprima aperta delle conferenze in rete è disponibile per tutti i clienti. Le conferenze in rete consentono alle organizzazioni di inviare chiamate in ingresso e in uscita ai numeri di accesso esterno Microsoft tramite l'instradamento diretto. Questa funzionalità non ha lo scopo di estendere il supporto dei servizi di audioconferenza ai numeri di accesso esterno di terze parti. Le conferenze in rete non sono supportate se vengono utilizzate per instradare le chiamate in ingresso al servizio di audioconferenza attraverso numeri di telefono di accesso esterno di terze parti.

Questo articolo descrive i prerequisiti e i passaggi di configurazione necessari per abilitare le conferenze in rete per l'organizzazione.

> [!IMPORTANT]
> LE conferenze in rete NON devono essere distribuite con dispositivi di telefonia in India.
  
## <a name="prerequisites"></a>Prerequisiti

Prima di configurare le conferenze in rete, verificare che l'organizzazione soddisfi i prerequisiti seguenti: 

- Assicurarsi che tutti gli utenti dell'organizzazione abilitati o abilitati per le audioconferenze utilizzino Teams per tutte le riunioni. Il routing delle chiamate in ingresso e in uscita delle audioconferenze tramite le conferenze in rete è supportato solo per le riunioni di Teams.

- Assegnare licenze per i servizi di audioconferenza a tutti gli utenti che utilizzano le conferenze in rete.

- Configurare il servizio di audioconferenza. Per altre informazioni, vedere [Configurare le audioconferenze per Microsoft Teams.](set-up-audio-conferencing-in-teams.md)

- Configurare il controller dei confini della sessione (SBC) per l'instradamento diretto. Per altre informazioni, vedere [Pianificare l'instradamento diretto](direct-routing-plan.md) [e configurare l'instradamento diretto.](direct-routing-configure.md) 

  Se si sta configurando l'instradamento diretto solo ai fini delle audioconferenze, è necessario completare solo il "Passaggio 1: Connettere il proprio SBC" per le conferenze in rete.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Abilitare l'instradamento delle chiamate con accesso esterno ai servizi di audioconferenza Microsoft tramite l'instradamento diretto 

Per instradare le chiamate con accesso esterno effettuate dagli utenti locali al servizio di audioconferenza tramite l'instradamento diretto, è necessario configurare le regole di routing appropriate per i provider di servizi di audioconferenza e IBC (Private Branch Exchange).

È necessario configurare le apparecchiature di telefonia dei siti per instradare le chiamate a qualsiasi numero di servizio del bridge di conferenza dell'organizzazione tramite un trunk di routing diretto.

Puoi trovare i numeri di servizio nell'interfaccia di amministrazione di Teams in Riunioni **-> Conferencing Bridges** o utilizzando il cmdlet PowerShell di Skype for Business Online Get-CsOnlineDialInConferencingBridge. Per ulteriori informazioni, consulta un elenco di numeri per [i servizi di audioconferenza in Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

> [!NOTE]
> Questa funzionalità non è disponibile per gli utenti con licenza di audioconferenza con pagamento al minuto.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Abilitare l'instradamento delle chiamate in uscita delle riunioni di Teams tramite l'instradamento diretto

Le chiamate in uscita delle riunioni di Teams vengono avviate dall'interno di una riunione dell'organizzazione a numeri PSTN, tra cui chiamate con accesso esterno e chiamate per portare i nuovi partecipanti a una riunione. 

Per abilitare il routing in uscita delle riunioni di Teams tramite l'instradamento diretto agli utenti di rete, è necessario creare e assegnare un criterio di routing dei servizi di audioconferenza denominato "OnlineAudioConferencingRoutingPolicy". 

Il criterio OnlineAudioConferencingRoutingPolicy è equivalente al criterio CsOnlineVoiceRoutingPolicy per le chiamate PSTN 1:1 tramite routing diretto. Il criterio OnlineAudioConferencingRoutingPolicy può essere gestito usando i cmdlet seguenti:

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Per altre informazioni sul routing per il routing diretto, vedere [Configurare il routing vocale per l'instradamento diretto.](direct-routing-voice-routing.md)


Per abilitare l'instradamento delle chiamate in uscita tramite l'instradamento diretto, è necessario: 

- Configurare i criteri di routing delle audioconferenze
- Configurare il routing sui dispositivi di telefonia dell'organizzazione
- (Facoltativo) Configurare un piano di chiamata

Le chiamate in uscita dalle riunioni di Teams sono provenienti dal numero di servizio predefinito nel bridge di conferenza. Per ulteriori informazioni sul numero di servizio predefinito del bridge di audioconferenza, consulta Modificare i numeri di [telefono nel bridge di audioconferenza.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

### <a name="configure-audio-conferencing-routing-policies"></a>Configurare i criteri di routing delle audioconferenze

Il criterio di routing onlineAudioConferencingRoutingPolicy per le audioconferenze determina quali chiamate in uscita vengono instradati ai trunk di routing diretto. Se si ha familiarità con il criterio CsOnlineVoiceRoutingPolicy, il funzionamento di questo criterio è molto simile.

Per configurare i criteri di routing delle audioconferenze, sono necessari i passaggi seguenti:
1.  Creare utilizzi PSTN
2.  Configurare i percorsi vocali
3.  Creare criteri di routing vocale per le audioconferenze
4.  Assegnare criteri agli utenti


#### <a name="create-pstn-usages"></a>Creare utilizzi PSTN

L'utilizzo di PSTN è una raccolta di route vocali. Quando viene avviata una chiamata in uscita dalla riunione di un determinato organizzatore, i percorsi vocali vengono utilizzati per determinare il percorso di instradamento della chiamata in base agli utilizzi PSTN associati all'utente tramite il criterio di instradamento vocale dell'utente.

Puoi creare un utilizzo PSTN utilizzando il cmdlet "Set-CsOnlinePstnUsage". Per esempio:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurare i percorsi vocali

I percorsi vocali determinano il gateway PSTN da usare per instradare una chiamata in base al numero di telefono composto da una riunione di Teams. I percorsi vocali determinano il gateway PSTN che deve essere usato per instradare una determinata chiamata abbinando il numero di telefono composto da una riunione di Teams a un modello di regex. Quando si crea un percorso vocale, la route deve essere associata a uno o più utilizzi di PSTN.

Puoi creare un percorso vocale e definire il regex e i gateway da associare al percorso vocale usando il cmdlet "New-CsOnlineVoiceRoute". Per esempio:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Creare criteri di routing vocale per le audioconferenze

I criteri di routing vocale delle audioconferenze determinano i possibili percorsi che possono essere utilizzati per instradare una chiamata proveniente dalle riunioni di un organizzatore in base al numero di telefono di destinazione della chiamata in uscita della riunione. I criteri di routing vocale delle audioconferenze sono associati a uno o più utilizzi di PSTN, che a loro volta determinano i possibili percorsi che verranno tentati di utilizzare per le chiamate in uscita della riunione degli organizzatori associati al criterio.

Puoi creare un criterio di routing vocale per i servizi di audioconferenza utilizzando il cmdlet "New- CsOnlineAudioConferencingRoutingPolicy". Per esempio:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Dopo l'assegnazione del criterio a un utente e l'avvio di una chiamata in uscita da una delle riunioni dell'utente, vengono valutati i percorsi vocali negli utilizzi PSTN associati all'organizzatore attraverso il criterio di instradamento vocale dell'utente. Se la destinazione della chiamata in uscita della riunione corrisponde a un regex in uno dei percorsi vocali associati all'organizzatore, la chiamata in uscita della riunione verrà instradata al gateway PSTN definito nel percorso vocale. Se la destinazione della chiamata in uscita della riunione non corrisponde a nessuno dei percorsi vocali associati all'organizzatore, la chiamata in uscita della riunione verrà instradata da Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Assegnare criteri agli utenti

Dopo aver definito i criteri di routing delle audioconferenze, è possibile assegnarli agli utenti. Dopo l'assegnazione dei criteri, le chiamate in uscita della riunione verranno valutate per determinare il percorso di routing. I criteri di routing delle audioconferenze vengono sempre valutati in base all'organizzatore della riunione, indipendentemente dall'utente che avvia una chiamata in uscita per una riunione.

Puoi assegnare criteri di routing vocale per i servizi di audioconferenza a un utente utilizzando il cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Ad esempio:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurare il routing sui dispositivi di telefonia dell'organizzazione

Sui dispositivi di telefonia dell'organizzazione, è necessario assicurarsi che le chiamate in uscita della riunione instradati attraverso l'instradamento diretto siano indirizzate alla destinazione prevista in rete.


### <a name="optional-configure-a-dial-plan"></a>(Facoltativo) Configurare un piano di chiamata

Un piano di chiamata è un insieme di regole di normalizzazione che traducono i numeri di telefono composto da un singolo utente in un formato alternativo (in genere E.164) ai fini dell'autorizzazione delle chiamate e dell'instradamento delle chiamate.

Per impostazione predefinita, gli utenti di Teams possono effettuare chiamate in uscita ai numeri PSTN in formato E.164, cioò + \<country code\> \<number\> . Tuttavia, i piani di chiamata possono essere utilizzati per consentire agli utenti di comporre numeri di telefono in altri formati, ad esempio estensioni a 4 cifre.

Per abilitare la composizione basata su interno tramite conferenza telefonica in rete, è possibile configurare piani di chiamata in modo che corrispondano al modello di composizione dell'interno agli intervalli di numeri di telefono del numero di telefono dell'organizzazione. Per configurare piani di chiamata, vedere [Creare e gestire piani di chiamata.](create-and-manage-dial-plans.md)


## <a name="known-issues-in-open-preview"></a>Problemi noti in Open Preview

Di seguito è riportato un elenco dei problemi noti attualmente presenti nella versione Open Preview delle conferenze in rete. Microsoft sta lavorando alla risoluzione di questi problemi.

| Problema | Soluzione alternativa |
| :--- | :--- |
| Le chiamate con accesso esterno con ID chiamante anonimi/nascosti che vengono instradati tramite conferenze in rete non possono essere connesse alla riunione. | Se possibile, imposta una configurazione nel sistema PBX o SBC in modo da inviare sempre un ID chiamante per le chiamate instradati tramite conferenze in rete.|
| In alcuni casi, il messaggio di benvenuto che viene riprodotto agli utenti quando accondono al servizio ("Benvenuto nel servizio di audioconferenza...") viene troncato e gli utenti non sentono la parola "Benvenuto".| Al momento non ci sono soluzioni alternative per questo problema. |




## <a name="related-topics"></a>Argomenti correlati


