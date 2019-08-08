---
title: Configurare l'interoperabilità cloud video per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: Questo articolo illustra come pianificare e configurare l'interoperabilità cloud video per gli utenti dell'organizzazione.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e91b0e25a7844634577083b26d74a48c788bc45b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237053"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurare l'interoperabilità cloud video per Microsoft Teams

Dopo aver scelto i partner di interoperabilità [cloud video](cloud-video-interop.md), è necessario pianificare la distribuzione, configurare i dettagli di provisioning e la chiave del tenant del partner e acconsentire all'app di interoperabilità video nell'organizzazione. Il diagramma seguente illustra il processo. 

![Distribuzione di CVI nell'organizzazione](media/deploying-cvi.png)

## <a name="plan"></a>Piano

Per informazioni su come identificare un partner o partner da usare nell'organizzazione, vedere interoperabilità [cloud video per Microsoft teams](cloud-video-interop.md) . 

Per pianificare l'abilitazione per l'utente in base/simultanea/wide site: 

- Selezionare un modello di distribuzione/modello ospitato per l'uso
- Selezionare il piano di licenza ideale per l'organizzazione. 
- Pianificare la capacità delle VM è l'hosting dell'infrastruttura video.

## <a name="configure"></a>Configurare 

Per configurare l'interoperabilità con cloud video, eseguire la procedura seguente. 

1. Ottenere le informazioni di configurazione dai partner/partner scelti (chiave del tenant, appId...). È possibile usare uno o più partner di interoperabilità video nell'organizzazione 

2. Verificare che la rete sia configurata correttamente. Configurare il firewall video basato su standard per l'attraversamento della rete perimetrale per il supporto. Ad esempio: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configurare le camere integrate con Exchange e OTD. Nella maggior parte dei casi, è necessario configurare e configurare l'inoltro aggiuntivo nell'ambiente.


## <a name="provision"></a>Disposizione
 
La chiave del tenant sarà la chiamata esterna al servizio partner. Nell'esempio seguente, 813878896@t.plcm.vc è la chiave del tenant. 

![Esempio di chiave tenant](media/tenant-key-example.png) 

Sarà necessario eseguire i cmdlet seguenti per provisionare la chiave del tenant e consentire anche agli utenti selezionati o all'intera organizzazione di creare riunioni con le coordinate di interoperabilità video.

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft fornisce criteri predefiniti per ogni partner supportato che consente di designare i partner da usare per l'interoperabilità video cloud.

    Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione. Puoi assegnare questo criterio a uno o più utenti sfruttando il cmdlet Grant-CsTeamsVideoInteropServicePolicy.
 
- ** [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Il cmdlet Grant-CsTeamsVideoInteropServicePolicy consente di assegnare un criterio precostruito per l'uso nell'organizzazione o di assegnare il criterio a utenti specifici.
 
- ** [New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Usa il nuovo-CsVideoInteropServiceProvider per specificare le informazioni su un partner CVI supportato che l'organizzazione vuole usare.
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Usa il set-CsVideoInteropServiceProvider per aggiornare le informazioni relative a un partner CVI supportato usato dall'organizzazione.
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Ottenere tutti i provider configurati per l'utilizzo all'interno dell'organizzazione.
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Usare Remove-CsVideoInteropServiceProvider per rimuovere tutte le informazioni del provider relative a un provider che l'organizzazione non usa più.  
 
## <a name="consent"></a>Consenso

È necessario fornire il consenso per i dispositivi di teleconferenza video (VTCs) per partecipare alle riunioni delle organizzazioni tramite il servizio partner. Questo collegamento di consenso verrà fornito anche dal partner.  
 
Al termine di questa procedura, gli utenti abilitati individualmente tramite il cmdlet Grant precedente o tutti gli utenti dell'organizzazione, se il tenant è abilitato, avranno Coordinate VTC in tutte le riunioni di team che pianificano. Qualsiasi VTC può partecipare a queste riunioni tramite le coordinate.


|Nome|Descrizione breve dell'autorizzazione dell'applicazione| Descrizione|
|--|--|---|
|Chiamate. JoinGroupCall. All|Partecipare a chiamate di gruppo e riunioni come app (anteprima)|Consente all'app di partecipare alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.  L'app verrà unita ai privilegi di un utente della directory per le riunioni nel tenant.|
|Chiamate. JoinGroupCallasGuest. All|Partecipare a chiamate di gruppo e riunioni come utente Guest (anteprima)|Consente all'app di partecipare in forma anonima alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.  L'app verrà unita come guest alle riunioni nel tenant.|
|Chiamate. AccessMedia. All|Accedere ai flussi multimediali in una chiamata come app (anteprima)|Consente all'app di accedere direttamente ai flussi multimediali in una chiamata, senza un utente connesso.|
|OnlineMeetings. Read. All|Leggere i dettagli delle riunioni online (anteprima)|Consente all'app di leggere i dettagli delle riunioni online nell'organizzazione, senza un utente connesso.|

## <a name="schedule"></a>Pianificare

Pianificare quindi la riunione teams con le coordinate di interoperabilità video. L'utente abilitato può pianificare le riunioni di teams tramite:
- [Componente aggiuntivo riunione teams per Outlook](teams-add-in-for-outlook.md)
- Desktop e dispositivi mobili del client Teams


## <a name="join"></a>Partecipare a

Puoi partecipare alle riunioni di teams con i tuoi dispositivi VTC nei modi seguenti:
 
- IVR (risposta vocale interattiva)
    - Puoi effettuare la chiamata al IVR del partner usando il tenantkey @ Domain. 
    - Una volta entrati nell'IVR del partner, verrà richiesto di immettere il VTC conferenceId, che consentirà quindi di connettersi alla riunione teams.
- Chiamata diretta
    - Puoi effettuare direttamente la chiamata alla riunione teams senza interagire con il IVR del partner usando la funzionalità di chiamata diretta usando la stringa completa di tenantkey. VTC ConferenceId @ Domain.
- Dial-One-Touch
    - Se si dispone di una sala teams integrata, è possibile usare le funzionalità di dial-up con un solo tocco offerte dal partner (senza dover digitare una stringa di chiamata).

Infine, Coinvolgi gli utenti di teams nelle tue riunioni usando audio, video e condivisione di contenuti. 