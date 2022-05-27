---
title: Servizi di conferenza on-network per Audioconferenza
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
- m365initiative-meetings
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Di seguito viene descritto on-network for Audioconferenza.
ms.openlocfilehash: 9b986bb8cd4d432c563e60f03e2dcdf496749f36
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675958"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>Servizi di conferenza on-network per Audioconferenza

Le conferenze in rete consentono alle organizzazioni di inviare chiamate Audioconferenza in ingresso e in uscita a numeri di accesso esterno Microsoft tramite routing diretto. Questa funzionalità non è stata progettata per estendere il supporto di Audioconferenza ai numeri di accesso esterno di terze parti. Le conferenze in rete non sono supportate se utilizzate per instradare le chiamate in ingresso al servizio Audioconferenza tramite numeri di telefono di accesso esterno di terze parti o chiamate in uscita al pstN da Microsoft Audioconferenza Bridge.

Questo articolo descrive i prerequisiti e i passaggi di configurazione necessari per abilitare le conferenze in rete per l'organizzazione.

> [!IMPORTANT]
> Le conferenze in rete NON devono essere distribuite con alcun dispositivo di telefonia in India.

## <a name="prerequisites"></a>Prerequisiti

Prima di configurare le conferenze in rete, assicurati che l'organizzazione soddisfi i prerequisiti seguenti:

- Verificare che tutti gli utenti dell'organizzazione abilitati, o che saranno abilitati, per Audioconferenza useranno Teams per tutte le riunioni. Il routing delle chiamate Audioconferenza in ingresso e in uscita tramite le conferenze in rete è supportato solo per le riunioni Teams.

- Assegnare licenze di Audioconferenza a tutti gli utenti che usano le conferenze in rete.

- Configurare il servizio Audioconferenza. Per altre informazioni, vedere [Configurare Audioconferenza per Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Configurare SBC (Session Border Controller) per il routing diretto. Per ulteriori informazioni, vedere [Pianificare il routing diretto](direct-routing-plan.md) e [Configurare il routing diretto](direct-routing-configure.md).

  Se stai configurando il routing diretto solo ai fini di Audioconferenza, devi completare solo il "Passaggio 1: Connessione la tua SBC" per i servizi di conferenza on-network.

## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Abilitare il routing delle chiamate telefoniche con accesso diretto a Microsoft Audioconferenza tramite routing diretto

Per instradare le chiamate telefoniche con accesso esterno effettuate dagli utenti locali al servizio Audioconferenza tramite routing diretto, è necessario configurare le regole di routing appropriate per gli SBC e i PBX (Private Branch Exchange).

È necessario configurare l'apparecchiatura di telefonia dei siti per instradare le chiamate a qualsiasi numero di servizio del bridge di conferenza dell'organizzazione tramite un trunk routing diretto.

I numeri di servizio sono disponibili nell'interfaccia di amministrazione di Teams in **Riunioni -> Conferencing Bridge** o usando il cmdlet Skype for Business Online PowerShell Get-CsOnlineDialInConferencingBridge. Per altre informazioni, vedere un elenco di [numeri di Audioconferenza in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Questa funzionalità non è disponibile per gli utenti con licenza di pagamento al minuto Audioconferenza.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Abilitare il routing delle chiamate in uscita Teams riunione tramite routing diretto

Teams chiamate in uscita della riunione vengono avviate dall'interno di una riunione dell'organizzazione a numeri PSTN, incluse chiamate e chiamate per portare nuovi partecipanti a una riunione.

Per abilitare Teams routing della chiamata in uscita tramite routing diretto agli utenti di rete, è necessario creare e assegnare un criterio di routing Audioconferenza denominato "OnlineAudioConferencingRoutingPolicy".

Il criterio OnlineAudioConferencingRoutingPolicy equivale a CsOnlineVoiceRoutingPolicy per le chiamate PSTN 1:1 tramite routing diretto. Il criterio OnlineAudioConferencingRoutingPolicy può essere gestito usando i cmdlet seguenti:

- New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Per altre informazioni sul routing per il routing diretto, vedere [Configurare il routing vocale per il routing diretto](direct-routing-voice-routing.md).

Per abilitare il routing delle chiamate in uscita tramite routing diretto, è necessario:

- Configurare criteri di routing Audioconferenza
- Configurare il routing sulle apparecchiature di telefonia dell'organizzazione
- (Facoltativo) Configurare un piano di chiamata

Le chiamate in uscita da Teams riunioni provengono dal numero di servizio predefinito sul bridge di conferenza. Per ulteriori informazioni sul numero di servizio predefinito del bridge di Audioconferenza, vedi [Modificare i numeri di telefono del bridge di Audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Configurare criteri di routing Audioconferenza

Il criterio di routing Audioconferenza OnlineAudioConferencingRoutingPolicy determina quali chiamate di chiamata in uscita delle riunioni vengono instradate ai trunk di routing diretto. Se si ha familiarità con il criterio CsOnlineVoiceRoutingPolicy, questo criterio funziona in modo molto simile.

Per configurare Audioconferenza criteri di routing sono necessari i passaggi seguenti:

1. Creare utilizzi PSTN
1. Configurare le route vocali
1. Creare criteri di routing vocale Audioconferenza
1. Assegnare criteri agli utenti

#### <a name="create-pstn-usages"></a>Creare utilizzi PSTN

Gli utilizzi PSTN sono raccolte di route vocali. Quando viene avviata una chiamata in uscita dalla riunione di un determinato organizzatore, le route vocali vengono utilizzate per determinare il percorso di routing della chiamata in base agli utilizzi PSTN associati all'utente tramite i criteri di routing vocale dell'utente.

Puoi creare un utilizzo PSTN utilizzando il cmdlet "Set-CsOnlinePstnUsage". Per esempio:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurare le route vocali

Le route vocali determinano il gateway PSTN che deve essere usato per instradare una chiamata in base al numero di telefono comporre da una riunione Teams. Le route vocali determinano il gateway PSTN che deve essere usato per instradare una determinata chiamata collegando il numero di telefono comporre da una riunione Teams con un modello regex. Quando si crea un percorso vocale, il percorso deve essere associato a uno o più utilizzi PSTN.

Puoi creare una route vocale e definire il regex e i gateway da associare alla route vocale utilizzando il cmdlet "New-CsOnlineVoiceRoute". Per esempio:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Creare criteri di routing vocale Audioconferenza

Audioconferenza criteri di routing vocale determinano i possibili percorsi che possono essere usati per instradare una chiamata proveniente dalle riunioni di un organizzatore in base al numero di telefono di destinazione della chiamata in uscita della riunione. Audioconferenza criteri di routing vocale sono associati a uno o più utilizzi PSTN che, a loro volta, determinano le possibili route che verranno tentate di utilizzare per le chiamate in uscita della riunione degli organizzatori associati al criterio.

Puoi creare un criterio di routing vocale Audioconferenza utilizzando il cmdlet "New- CsOnlineAudioConferencingRoutingPolicy". Per esempio:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Dopo l'assegnazione del criterio a un utente e l'avvio di una chiamata in uscita da una delle riunioni dell'utente, verranno valutate le route vocali negli utilizzi PSTN associati all'organizzatore tramite il criterio di routing vocale dell'utente. Se la destinazione della chiamata in uscita della riunione corrisponde a un regex in una delle route vocali associate all'organizzatore, la chiamata in uscita della riunione verrà instradata al gateway PSTN definito nel percorso vocale. Se la destinazione della chiamata in uscita della riunione non corrisponde a nessuna delle route vocali associate all'organizzatore, la chiamata in uscita della riunione verrà instradata da Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Assegnare criteri agli utenti

Dopo aver definito i criteri di routing Audioconferenza, è ora possibile assegnarli agli utenti. Dopo l'assegnazione dei criteri, le chiamate in uscita della riunione verranno valutate per determinare il percorso di routing. Audioconferenza criteri di routing vengono sempre valutati in base all'organizzatore della riunione, indipendentemente dall'utente nella riunione che avvia una chiamata in uscita della riunione.

Puoi assegnare un criterio di routing vocale Audioconferenza a un utente utilizzando il cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Ad esempio:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1"
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurare il routing sulle apparecchiature di telefonia dell'organizzazione

Nell'apparecchiatura telefonica dell'organizzazione, è necessario assicurarsi che le chiamate in uscita della riunione instradate tramite routing diretto siano indirizzate alla destinazione di rete prevista.

### <a name="optional-configure-a-dial-plan"></a>(Facoltativo) Configurare un piano di chiamata

Un piano di chiamata è un insieme di regole di normalizzazione che traducono i numeri di telefono composto da un singolo utente in un formato alternativo (in genere E.164) ai fini dell'autorizzazione alla chiamata e del routing delle chiamate.

Per impostazione predefinita, Teams utenti possono effettuare chiamate in uscita verso numeri PSTN in formato E.164, ovvero +\<country code\>\<number\>. Tuttavia, i piani di chiamata possono essere usati per consentire agli utenti di comporre numeri di telefono in altri formati, ad esempio le estensioni di 4 cifre.

Se desideri abilitare la composizione basata sull'estensione tramite i servizi di conferenza telefonica su rete, puoi configurare piani di chiamata in modo che corrispondano allo schema di composizione dell'interno agli intervalli di numeri di telefono del numero di telefono dell'organizzazione. Per configurare piani di chiamata, vedere [Creare e gestire piani di chiamata](create-and-manage-dial-plans.md).

## <a name="related-topics"></a>Argomenti correlati
