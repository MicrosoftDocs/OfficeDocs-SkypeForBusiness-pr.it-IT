---
title: Configurare l'interoperabilità dei video cloud per Microsoft Teams
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
description: Questo articolo spiega come pianificare e configurare Cloud Video Interoperabilità per gli utenti dell'organizzazione.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1f45967b3e2737f6e2df74c505932ea69afe37f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582633"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurare l'interoperabilità dei video cloud per Microsoft Teams

Dopo aver scelto i partner di interoperabilità di [Cloud Video,](cloud-video-interop.md)sarà necessario pianificare la distribuzione, configurare i dettagli di provisioning e la chiave del tenant del partner e acconsentire all'app di interoperabilità video nella propria organizzazione. Il diagramma seguente illustra il processo. 

![Distribuzione di CVI nell'organizzazione](media/deploying-cvi.png)

## <a name="plan"></a>Piano

Vedere [l'interoperabilità dei video cloud](cloud-video-interop.md) per Microsoft Teams per informazioni su come identificare un partner o partner da usare nell'organizzazione. 

Per pianificare l'abilitazione basata su utente/simultaneo/a livello di sito: 

- Scegliere un modello di distribuzione/modello ospitato per l'uso
- Selezionare il piano di licenza ideale per l'organizzazione. 
- Pianificare la capacità delle macchine virtuali è ospitare l'infrastruttura video.

## <a name="configure"></a>Configura 

Per configurare l'interoperabilità dei video nel cloud, seguire questa procedura. 

1. Ottenere informazioni di configurazione dal partner/partner scelto (chiave tenant, id app...). È possibile usare uno o più partner di interoperabilità video nell'organizzazione 

2. Verificare che la rete sia configurata correttamente. Configurare il firewall video basato su standard per il supporto della rete perimetrale. Ad esempio: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configurare sale integrate con Exchange e OTD. Nella maggior parte dei casi, è necessario configurare e configurare l'inoltro aggiuntivo nell'ambiente.


## <a name="provision"></a>Provisioning
 
Il codice tenant sarà la chiamata esterna al servizio partner. Nell'esempio seguente 813878896@t.plcm.vc chiave del tenant. 

![Esempio di chiave tenant](media/tenant-key-example.png) 

Per effettuare il provisioning della chiave del tenant, è necessario eseguire i cmdlet seguenti e anche consentire a utenti selezionati o all'intera organizzazione di creare riunioni con coordinate di interoperabilità video.

 
- **[Get-CsTeamsVideoInteropServicepolicy:](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy)** Microsoft fornisce criteri predefiniti per ognuno dei nostri partner supportati, che consentono di designare i partner da usare per l'interoperabilità dei video nel cloud.

    Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione. È possibile assegnare questo criterio a uno o più utenti sfruttando il cmdlet Grant-CsTeamsVideoInteropServicePolicy locale.
 
- **[Grant-CsTeamsVideoInteropServicePolicy:](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy)** Il cmdlet Grant-CsTeamsVideoInteropServicePolicy consente di assegnare criteri predefiniti da usare nell'organizzazione o di assegnarli a utenti specifici.
 
- **[New-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider)** Usare le New-CsVideoInteropServiceProvider per specificare informazioni su un partner CVI supportato che l'organizzazione vuole usare.
 
- **[Set-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider)** Usare le Set-CsVideoInteropServiceProvider per aggiornare le informazioni su un partner CVI supportato utilizzato dall'organizzazione.
 
- **[Get-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider)** Ottenere tutti i provider configurati per l'uso all'interno dell'organizzazione.
 
- **[Remove-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider)** Usare Remove-CsVideoInteropServiceProvider per rimuovere tutte le informazioni sul provider relative a un provider che l'organizzazione non usa più.  
 
## <a name="consent"></a>Consenso

Devi fornire il consenso per i dispositivi di teleconferenza video (VCS) per partecipare alle riunioni della tua organizzazione tramite il servizio partner. Questo collegamento per il consenso verrà fornito anche dal tuo partner.  
 
Una volta completata questa procedura, gli utenti abilitati singolarmente tramite il cmdlet Grant precedente o tutti gli utenti dell'organizzazione, se il tenant è abilitato, avranno le coordinate VTC in tutte le riunioni di Teams che pianificano. Qualsiasi VTC può partecipare a queste riunioni tramite queste coordinate.


|Nome|Descrizione breve delle autorizzazioni per le applicazioni| Descrizione|
|--|--|---|
|Calls.JoinGroupCall.All|Partecipare a chiamate e riunioni di gruppo come app (anteprima)|Consente all'app di partecipare alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.  L'app verrà unita alle riunioni del tenant con i privilegi di un utente della directory.|
|Calls.JoinGroupCallasGuest.All|Partecipare a chiamate e riunioni di gruppo come utente guest (anteprima)|Consente all'app di partecipare in forma anonima alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.  L'app verrà unita come guest alle riunioni nel tenant.|
|Calls.AccessMedia.All|Accedere ai flussi multimediali in una chiamata come app (anteprima)|Consente all'app di ottenere l'accesso diretto ai flussi multimediali in una chiamata, senza un utente connesso.|
|OnlineMeetings.Read.All|Leggere i dettagli della riunione online (anteprima)|Consente all'app di leggere i dettagli della riunione online nell'organizzazione, senza che sia stato effettuato l'accesso.|

## <a name="schedule"></a>Pianificazione

Pianificare quindi la riunione di Teams con le coordinate di interoperabilità video. L'utente abilitato può pianificare le riunioni dei team tramite:
- [Componente aggiuntivo Riunione di Teams per Outlook](teams-add-in-for-outlook.md)
- Client Teams per desktop e dispositivi mobili


## <a name="join"></a>Partecipa

È possibile partecipare alle riunioni di Teams con i dispositivi VTC nei modi seguenti:
 
- IVR (Risposta vocale interattiva)
    - È possibile chiamare l'IVR del partner usando il tenantkey@domain. 
    - Nel partner IVR verrà richiesto di immettere il valore VTC conferenceId, che consente di connettersi alla riunione di Teams.
- Chiamata diretta
    - Puoi accedere direttamente alla riunione di Teams senza interagire con l'IVR del partner utilizzando la funzione di chiamata diretta utilizzando la stringa completa di tenantkey. VTC ConferenceId@domain.
- Chiamata con un solo tocco
    - Se si dispone di una sala di Teams integrata, è possibile usare le funzionalità di chiamata con un solo tocco offerte dal partner (senza dover digitare alcuna stringa di composizione).

Infine, interagire con gli utenti di Teams nelle riunioni con audio, video e condivisione di contenuti. 
