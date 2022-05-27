---
title: Configurare l'interoperabilità video cloud per Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: Questo articolo spiega come pianificare e configurare l'interoperabilità video cloud per gli utenti dell'organizzazione.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b76e7c5e79b3928c7fb19ad9c5f5fb8f241b29a
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674738"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurare l'interoperabilità video cloud per Microsoft Teams

Dopo aver [scelto i partner Cloud Video Interop](cloud-video-interop.md), sarà necessario pianificare la distribuzione, configurare i dettagli di provisioning e la chiave del tenant del partner e acconsentire all'app di interoperabilità video nell'organizzazione. Il diagramma seguente illustra il processo.

![Distribuzione di CVI nell'organizzazione.](media/deploying-cvi.png)

## <a name="plan"></a>Piano

Per informazioni sull'identificazione di un partner o partner da usare nell'organizzazione, vedere [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md).

Per pianificare l'abilitazione a livello di sito basata su utenti,simultanei/siti:

- Selezionare un modello di distribuzione/modello ospitato per l'uso
- Selezionare il piano di licenza ideale per l'organizzazione.
- Pianificare la capacità delle macchine virtuali è l'hosting dell'infrastruttura video.

## <a name="configure"></a>Configurare

Per configurare Cloud Video Interop, seguire questa procedura.

1. Ottenere informazioni di configurazione dal partner/partner scelto (chiave tenant, appIds...). È possibile usare uno o più partner di interoperabilità video nell'organizzazione

2. Assicurati che la rete sia configurata correttamente. Configurare il firewall video basato su standard per l'attraversamento di rete perimetrale per il supporto. Ad esempio:
    - Cisco VCS-e
    - Polycom RPAD

3. Configurare sale integrate con exchange e OTD. Nella maggior parte dei casi, è necessario configurare e configurare un inoltro aggiuntivo nell'ambiente.

## <a name="provision"></a>Provvigione

La chiave tenant sarà la chiamata in uscita al servizio partner. Nell'esempio seguente 813878896@t.plcm.vc è la chiave tenant.

![Esempio di chiave tenant.](media/tenant-key-example.png)

Sarà necessario eseguire i cmdlet seguenti per eseguire il provisioning della chiave tenant e anche abilitare determinati utenti o l'intera organizzazione per creare riunioni con coordinate di interoperabilità video.

- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft fornisce criteri predefiniti per ognuno dei partner supportati che consentono di designare i partner da usare per l'interoperabilità video cloud.

    Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione. È possibile assegnare questo criterio a uno o più utenti sfruttando il cmdlet Grant-CsTeamsVideoInteropServicePolicy.

- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Il cmdlet Grant-CsTeamsVideoInteropServicePolicy consente di assegnare criteri predefiniti da usare nell'organizzazione o assegnare i criteri a utenti specifici.

- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Usare la New-CsVideoInteropServiceProvider per specificare le informazioni su un partner CVI supportato che l'organizzazione vuole usare.

- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Usare il Set-CsVideoInteropServiceProvider per aggiornare le informazioni su un partner CVI supportato usato dall'organizzazione.

- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Ottenere tutti i provider configurati per l'uso all'interno dell'organizzazione.

- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Usare Remove-CsVideoInteropServiceProvider per rimuovere tutte le informazioni del provider relative a un provider che l'organizzazione non usa più.

## <a name="consent"></a>Consenso

Sarà necessario fornire il consenso di autorizzazione per i dispositivi di teleconferenza video (VTC) per partecipare alle riunioni dell'organizzazione tramite il servizio partner. Questo collegamento per il consenso verrà fornito anche dal partner.

Una volta completata questa procedura, gli utenti abilitati singolarmente tramite il cmdlet Grant precedente o tutti gli utenti dell'organizzazione, se il tenant è abilitato, avranno le coordinate VTC in tutte le riunioni Teams che pianificare. Qualsiasi VTC può partecipare a queste riunioni tramite tali coordinate.

|Nome|Descrizione breve dell'autorizzazione per l'applicazione| Descrizione|
|---|---|---|
|Calls.JoinGroupCall.All|Partecipare a riunioni e chiamate di gruppo come app (anteprima)|Consente all'app di partecipare a chiamate di gruppo e riunioni pianificate nell'organizzazione, senza un utente connesso.  L'app verrà aggiunta con i privilegi di un utente della directory alle riunioni nel tenant.|
|Calls.JoinGroupCallasGuest.All|Partecipare a chiamate e riunioni di gruppo come utente guest (anteprima)|Consente all'app di partecipare in forma anonima alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.  L'app verrà aggiunta come guest alle riunioni nel tenant.|
|Calls.AccessMedia.All|Accedere a flussi multimediali in una chiamata come app (anteprima)|Consente all'app di ottenere l'accesso diretto a flussi multimediali in una chiamata, senza un utente connesso.|
|OnlineMeetings.Read.All|Leggere i dettagli della riunione online (anteprima)|Consente all'app di leggere i dettagli della riunione online nell'organizzazione, senza un utente connesso.|

## <a name="schedule"></a>Programma

Successivamente, pianificare Teams riunione con le coordinate di interoperabilità video. L'utente abilitato può pianificare le riunioni dei team tramite:

- [Teams componente aggiuntivo Riunione per Outlook](teams-add-in-for-outlook.md)
- Teams desktop client e dispositivi mobili

## <a name="join"></a>Unirsi

È possibile partecipare a riunioni Teams con i dispositivi VTC nei modi seguenti:

- IVR (Risposta vocale interattiva)
  - Puoi accedere all'IVR del partner tramite l'tenantkey@domain.
  - Una volta entrato nell'IVR partner, ti verrà chiesto di immettere il VTC conferenceId, che ti connetterà alla riunione Teams.
- Telefono diretto
  - È possibile accedere direttamente alla riunione Teams senza interagire con l'IVR del partner usando la funzionalità di composizione diretta usando la stringa completa di chiave tenant. ConferenceId@domain VTC.
- Comando radiale con un tocco
  - Se disponi di una sala di Teams integrata, puoi usare le funzionalità di chiamata con un tocco offerte dal tuo partner (senza dover digitare alcuna stringa di chiamata).

Infine, collaborare con Teams utenti alle riunioni usando l'audio, il video e la condivisione di contenuti.
