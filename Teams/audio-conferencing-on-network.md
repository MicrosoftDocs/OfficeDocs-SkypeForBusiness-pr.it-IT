---
title: Servizi di conferenza telefonica in rete per audioconferenze
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Di seguito viene descritta la connessione in rete per i servizi di audioconferenza.
ms.openlocfilehash: 222a89df39f1fe6b2decb21431f3475a148a1a6c
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267591"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>Servizi di conferenza telefonica in rete per audioconferenze

Le conferenze in rete consentono alle organizzazioni di inviare chiamate audioconferenze in ingresso e in uscita a numeri di accesso esterno Microsoft tramite routing diretto. Questa funzionalità non è stata progettata per estendere il supporto delle audioconferenze ai numeri di accesso esterno di terze parti. I servizi di conferenza in rete non sono supportati se usati per instradare le chiamate in ingresso al servizio Audioconferenza tramite numeri di telefono di accesso esterno di terze parti o chiamate in uscita al servizio PSTN dal Bridge di audioconferenza Microsoft.

Questo articolo descrive i prerequisiti e i passaggi di configurazione necessari per abilitare le conferenze in rete per l'organizzazione.

> [!IMPORTANT]
> Le conferenze in rete NON devono essere distribuite con alcun dispositivo di telefonia in India.

## <a name="prerequisites"></a>Prerequisiti

Prima di configurare le conferenze in rete, assicurati che l'organizzazione soddisfi i prerequisiti seguenti:

- Assicurarsi che tutti gli utenti dell'organizzazione abilitati, o che saranno abilitati, per le audioconferenze useranno Teams per tutte le riunioni. Il routing delle chiamate audioconferenze in ingresso e in uscita tramite le conferenze in rete è supportato solo per le riunioni di Teams.

- Assegnare licenze per i servizi di audioconferenza a tutti gli utenti che utilizzano i servizi di conferenza on-network.

- Configura il servizio Di audioconferenza. Per altre informazioni, vedere [Configurare le audioconferenze per Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Configurare SBC (Session Border Controller) per il routing diretto. Per ulteriori informazioni, vedere [Pianificare il routing diretto](direct-routing-plan.md) e [Configurare il routing diretto](direct-routing-configure.md).

  Se stai configurando l'instradamento diretto solo ai fini delle audioconferenze, devi completare solo il "Passaggio 1: Connetti SBC" per i servizi di conferenza on-network.

## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Abilitare il routing delle chiamate telefoniche con accesso esterno a Microsoft Audioconferenze tramite direct Routing

Per instradare le chiamate telefoniche con accesso esterno effettuate dagli utenti locali al servizio Audioconferenza tramite routing diretto, è necessario configurare le regole di routing appropriate per gli SBC e i PBX (Private Branch Exchange).

È necessario configurare l'apparecchiatura di telefonia dei siti per instradare le chiamate a qualsiasi numero di servizio del bridge di conferenza dell'organizzazione tramite un trunk routing diretto.

Puoi trovare i numeri di servizio nell'interfaccia di amministrazione di Teams in **Riunioni -> Conferencing Bridge** o usando il cmdlet PowerShell di Skype for Business Online Get-CsOnlineDialInConferencingBridge. Per ulteriori informazioni, consulta un elenco dei [numeri di audioconferenza in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Questa funzionalità non è disponibile per gli utenti con licenza di audioconferenza con tariffa al minuto.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Abilitare il routing delle chiamate in uscita delle riunioni di Teams tramite routing diretto

Le chiamate in uscita per le riunioni di Teams vengono avviate dall'interno di una riunione dell'organizzazione ai numeri PSTN, incluse chiamate e chiamate per portare nuovi partecipanti a una riunione.

Per abilitare il routing della chiamata in uscita delle riunioni di Teams tramite routing diretto agli utenti di rete, è necessario creare e assegnare un criterio di routing delle audioconferenze denominato "OnlineAudioConferencingRoutingPolicy".

Il criterio OnlineAudioConferencingRoutingPolicy equivale a CsOnlineVoiceRoutingPolicy per le chiamate PSTN 1:1 tramite routing diretto. Il criterio OnlineAudioConferencingRoutingPolicy può essere gestito usando i cmdlet seguenti:

- New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Per altre informazioni sul routing per il routing diretto, vedere [Configurare il routing vocale per il routing diretto](direct-routing-voice-routing.md).

Per abilitare il routing delle chiamate in uscita tramite routing diretto, è necessario:

- Configurare i criteri di routing delle audioconferenze
- Configurare il routing sulle apparecchiature di telefonia dell'organizzazione
- (Facoltativo) Configurare un piano di chiamata

Le chiamate in uscita dalle riunioni di Teams provengono dal numero di servizio predefinito sul bridge di conferenza. Per ulteriori informazioni sul numero di servizio predefinito del bridge di audioconferenza, consulta [Modificare i numeri di telefono del bridge di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Configurare i criteri di routing delle audioconferenze

Il criterio di routing delle audioconferenze OnlineAudioConferencingRoutingPolicy determina quali chiamate di chiamata in uscita per le riunioni vengono instradate ai trunk di routing diretto. Se si ha familiarità con il criterio CsOnlineVoiceRoutingPolicy, questo criterio funziona in modo molto simile.

Per configurare i criteri di routing delle audioconferenze sono necessari i passaggi seguenti:

1. Creare utilizzi PSTN
1. Configurare le route vocali
1. Creare criteri di routing vocale per i servizi di audioconferenza
1. Assegnare criteri agli utenti

#### <a name="create-pstn-usages"></a>Creare utilizzi PSTN

Gli utilizzi PSTN sono raccolte di route vocali. Quando viene avviata una chiamata in uscita dalla riunione di un determinato organizzatore, le route vocali vengono utilizzate per determinare il percorso di routing della chiamata in base agli utilizzi PSTN associati all'utente tramite i criteri di routing vocale dell'utente.

Puoi creare un utilizzo PSTN utilizzando il cmdlet "Set-CsOnlinePstnUsage". Per esempio:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurare le route vocali

Le route vocali determinano il gateway PSTN che deve essere usato per instradare una chiamata in base al numero di telefono che viene chiamato da una riunione di Teams. Le route vocali determinano il gateway PSTN che deve essere usato per instradare una determinata chiamata collegando il numero di telefono comporre da una riunione di Teams con un modello regex. Quando si crea un percorso vocale, il percorso deve essere associato a uno o più utilizzi PSTN.

Puoi creare una route vocale e definire il regex e i gateway da associare alla route vocale utilizzando il cmdlet "New-CsOnlineVoiceRoute". Per esempio:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Creare criteri di routing vocale per i servizi di audioconferenza

I criteri di routing vocale per i servizi di audioconferenza determinano le possibili route che possono essere usate per instradare una chiamata proveniente dalle riunioni di un organizzatore in base al numero di telefono di destinazione della chiamata in uscita della riunione. I criteri di routing vocale per i servizi di audioconferenza sono associati a uno o più utilizzi PSTN che, a loro volta, determinano le possibili route che verranno tentate per le chiamate in uscita degli organizzatori associati al criterio.

Puoi creare un criterio di routing vocale per le audioconferenze utilizzando il cmdlet "New- CsOnlineAudioConferencingRoutingPolicy". Per esempio:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Dopo l'assegnazione del criterio a un utente e l'avvio di una chiamata in uscita da una delle riunioni dell'utente, verranno valutate le route vocali negli utilizzi PSTN associati all'organizzatore tramite il criterio di routing vocale dell'utente. Se la destinazione della chiamata in uscita della riunione corrisponde a un regex in una delle route vocali associate all'organizzatore, la chiamata in uscita della riunione verrà instradata al gateway PSTN definito nel percorso vocale. Se la destinazione della chiamata in uscita della riunione non corrisponde a nessuna delle route vocali associate all'organizzatore, la chiamata in uscita della riunione verrà instradata da Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Assegnare criteri agli utenti

Dopo aver definito i criteri di routing delle audioconferenze, è ora possibile assegnarli agli utenti. Dopo l'assegnazione dei criteri, le chiamate in uscita della riunione verranno valutate per determinare il percorso di routing. I criteri di routing delle audioconferenze vengono sempre valutati in base all'organizzatore della riunione, indipendentemente dall'utente nella riunione che avvia una chiamata in uscita della riunione.

Puoi assegnare un criterio di routing vocale delle audioconferenze a un utente utilizzando il cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Ad esempio:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1"
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurare il routing sulle apparecchiature di telefonia dell'organizzazione

Nell'apparecchiatura telefonica dell'organizzazione, è necessario assicurarsi che le chiamate in uscita della riunione instradate tramite routing diretto siano indirizzate alla destinazione di rete prevista.

### <a name="optional-configure-a-dial-plan"></a>(Facoltativo) Configurare un piano di chiamata

Un piano di chiamata è un insieme di regole di normalizzazione che traducono i numeri di telefono composto da un singolo utente in un formato alternativo (in genere E.164) ai fini dell'autorizzazione alla chiamata e del routing delle chiamate.

Per impostazione predefinita, gli utenti di Teams possono effettuare chiamate in uscita verso numeri PSTN in formato E.164, ovvero +\<country code\>\<number\>. Tuttavia, i piani di chiamata possono essere usati per consentire agli utenti di comporre numeri di telefono in altri formati, ad esempio le estensioni di 4 cifre.

Se desideri abilitare la composizione basata sull'estensione tramite i servizi di conferenza telefonica su rete, puoi configurare piani di chiamata in modo che corrispondano allo schema di composizione dell'interno agli intervalli di numeri di telefono del numero di telefono dell'organizzazione. Per configurare piani di chiamata, vedere [Creare e gestire piani di chiamata](create-and-manage-dial-plans.md).

## <a name="related-topics"></a>Argomenti correlati
