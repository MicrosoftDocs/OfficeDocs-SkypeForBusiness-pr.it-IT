---
title: Configurare Cloud Video Interop per Microsoft Teams
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
description: Questo articolo spiega come pianificare e configurare Cloud Video Interop per gli utenti dell'organizzazione.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64d790e775ac0d76de48a71de8d165656f2e6927
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102602"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurare Cloud Video Interop per Microsoft Teams

Dopo aver scelto i partner cloud [Video Interop,](cloud-video-interop.md)è necessario pianificare la distribuzione, configurare i dettagli del provisioning e la chiave del tenant del partner e acconsentire all'app di interoperabilità video nell'organizzazione. Il diagramma seguente illustra il processo. 

![Distribuzione di CVI nell'organizzazione](media/deploying-cvi.png)

## <a name="plan"></a>Piano

Vedere [Cloud Video Interop per Microsoft Teams](cloud-video-interop.md) informazioni sull'identificazione di un partner o di un partner da usare nell'organizzazione. 

Per pianificare l'abilitazione basata su utenti/simultanei/a livello di sito: 

- Scegliere un modello di distribuzione/modello ospitato per l'uso
- Selezionare il piano di licenza ideale per l'organizzazione. 
- Pianificare la capacità delle macchine virtuali è ospitare l'infrastruttura video.

## <a name="configure"></a>Configurare 

Per configurare Cloud Video Interop, seguire questa procedura. 

1. Ottenere informazioni di configurazione dal partner/partner scelto (chiave tenant, appIds...). È possibile usare uno o più partner di interoperabilità video nell'organizzazione 

2. Verificare che la rete sia configurata correttamente. Configurare il firewall video basato su standard per il supporto dell'attraversamento della rete perimetrale. Ad esempio: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configurare le chat room integrate con Exchange e OTD. Nella maggior parte dei casi, l'inoltro aggiuntivo deve essere configurato e configurato nell'ambiente.


## <a name="provision"></a>Provisioning
 
La chiave del tenant sarà la connessione remota al servizio partner. Nell'esempio seguente, 813878896@t.plcm.vc è la chiave del tenant. 

![Esempio di chiave tenant](media/tenant-key-example.png) 

Per eseguire il provisioning della chiave del tenant, è necessario eseguire i cmdlet seguenti e consentire anche a utenti selezionati o all'intera organizzazione di creare riunioni con coordinate di interoperabilità video.

 
- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft fornisce criteri predefiniti per ognuno dei partner supportati che consentono di designare i partner da usare per l'interoperabilità video nel cloud.

    Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione. È possibile assegnare questo criterio a uno o più utenti sfruttando il cmdlet Grant-CsTeamsVideoInteropServicePolicy.
 
- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Il cmdlet Grant-CsTeamsVideoInteropServicePolicy consente di assegnare criteri predefiniti da usare nell'organizzazione o di assegnarli a utenti specifici.
 
- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Usare il New-CsVideoInteropServiceProvider per specificare le informazioni su un partner CVI supportato che l'organizzazione vuole usare.
 
- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Usare il Set-CsVideoInteropServiceProvider per aggiornare le informazioni su un partner CVI supportato utilizzato dall'organizzazione.
 
- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Ottenere tutti i provider configurati per l'uso all'interno dell'organizzazione.
 
- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Usare Remove-CsVideoInteropServiceProvider per rimuovere tutte le informazioni del provider relative a un provider che l'organizzazione non usa più.  
 
## <a name="consent"></a>Consenso

Sarà necessario fornire il consenso per l'autorizzazione per i dispositivi di teleconferenza video (VTC) per partecipare alle riunioni delle organizzazioni tramite il servizio partner. Questo collegamento di consenso verrà fornito anche dal partner.  
 
Al termine di questi passaggi, gli utenti abilitati singolarmente tramite il cmdlet Grant precedente o tutti gli utenti dell'organizzazione, se il tenant è abilitato, avranno le coordinate VTC in tutte le riunioni Teams pianificate. Qualsiasi VTC può partecipare a queste riunioni tramite queste coordinate.


|Nome|Descrizione breve dell'autorizzazione dell'applicazione| Descrizione|
|--|--|---|
|Calls.JoinGroupCall.All|Partecipare a chiamate e riunioni di gruppo come app (anteprima)|Consente all'app di partecipare alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.  L'app verrà unita con i privilegi di un utente della directory alle riunioni nel tenant.|
|Calls.JoinGroupCallasGuest.All|Partecipare a chiamate e riunioni di gruppo come utente guest (anteprima)|Consente all'app di partecipare in forma anonima alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.  L'app verrà unita come guest alle riunioni nel tenant.|
|Calls.AccessMedia.All|Accedere ai flussi multimediali in una chiamata come app (anteprima)|Consente all'app di ottenere l'accesso diretto ai flussi multimediali in una chiamata, senza un utente connesso.|
|OnlineMeetings.Read.All|Leggere i dettagli della riunione online (anteprima)|Consente all'app di leggere i dettagli della riunione online nell'organizzazione, senza un utente connesso.|

## <a name="schedule"></a>Pianificazione

Pianificare quindi una Teams riunione con coordinate di interoperabilità video. L'utente abilitato può pianificare le riunioni dei team tramite:
- [Teams Componente aggiuntivo Riunione per Outlook](teams-add-in-for-outlook.md)
- Teams client desktop e mobile


## <a name="join"></a>Partecipa

È possibile partecipare Teams riunioni con i dispositivi VTC nei modi seguenti:
 
- IVR (Risposta vocale interattiva)
    - È possibile accedere all'IVR del partner usando il tenantkey@domain. 
    - Una volta che sei nell'IVR del partner, ti verrà chiesto di immettere l'ID conferenza VTC, che ti connetterà alla riunione Teams riunione.
- Chiamata diretta
    - È possibile accedere direttamente alla riunione Teams senza interagire con l'IVR del partner usando la funzione di chiamata diretta usando la stringa completa di tenantkey. VTC ConferenceId@domain.
- Chiamata con un solo tocco
    - Se si ha una sala Teams integrata, è possibile usare le funzionalità di composizione con un solo tocco offerte dal partner (senza bisogno di digitare alcuna stringa di chiamata).

Infine, è possibile coinvolgere Teams utenti nelle riunioni usando audio, video e condivisione di contenuti.