---
title: Interoperabilità cloud video per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: L'interoperabilità cloud video consente ai dispositivi della sala riunioni di terze parti di partecipare a riunioni Microsoft teams.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c44f945304bd6e21e0c572ad17afe165fe6eedcd
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516684"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilità cloud video per Microsoft Teams

La cloud video Interop (CVI) è una soluzione di terze parti Microsoft qualificata che consente a sale riunioni di terze parti (telepresenza) e dispositivi video personali (VTCs) di partecipare alle riunioni di Microsoft teams.
 
Con Microsoft teams, è possibile ottenere una ricca collaborazione di contenuti online in riunioni che includono la condivisione di audio, video e contenuti. Questo può essere apprezzato tramite il client desktop e Web, oltre che tramite molti dispositivi partner che si integrano in modo nativo con Microsoft teams. Tuttavia, molti clienti hanno già investito in videoconferenze video e dispositivi di comunicazione video personali, che possono essere costosi da aggiornare. L'interoperabilità cloud video offre una soluzione semplice, che consente di usare le soluzioni esistenti fino a quando non si è pronti per l'aggiornamento.

Con l'interoperabilità cloud video, Microsoft teams offre un'esperienza di riunione nativa per tutti i partecipanti, in sale riunioni o all'interno dei client di teams.

### <a name="is-cloud-video-interop-for-me"></a>L'interoperabilità cloud video è per me?

L'interoperabilità cloud video fornisce un servizio intermedio durante la transizione a una soluzione completa nativa di Microsoft teams, usando endpoint teams. Il servizio fornito deve essere incluso nel percorso di migrazione.

L'interoperabilità cloud video è destinata ai clienti che soddisfano i criteri seguenti:

- Avere un'ampia distribuzione dei dispositivi della sala riunioni e della distribuzione di dispositivi video personali (50 + dispositivi) che non sono qualificati per l'integrazione diretta con Microsoft Teams
- Sono supportate da uno dei nostri partner di interoperabilità cloud video
- Si vuole mantenere il valore del loro investimento nei dispositivi della sala riunioni correnti e nei dispositivi video personali durante la migrazione a una soluzione Microsoft teams nativa

Mentre l'interoperabilità cloud video offre una soluzione intermedia ottimale, invitiamo i clienti a esaminare le soluzioni di riunione di Team nativi, ad esempio i sistemi di sala teams, per il lungo periodo. 

### <a name="partners-certified-for-microsoft-teams"></a>Partner certificati per Microsoft Teams

I partner seguenti hanno soluzioni di interoperabilità video per Microsoft teams. La tua azienda può scegliere di collaborare con qualsiasi combinazione di questi partner all'interno dell'azienda. 

|Partner|Soluzione partner|
|----|---|
|![Il logo che rappresenta Polycom RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Servizio RealConnect Polycom</a> |
|![Il logo che rappresenta Pexip Infinity](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity per Microsoft Teams</a> | 
|![Logo che rappresenta il gateway BlueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Gateway BlueJeans per Microsoft Teams</a> |

### <a name="cloud-video-interop-overview"></a>Panoramica sull'interoperabilità cloud video

L'interoperabilità cloud video è un servizio di terze parti offerto dai nostri partner per offrire l'interoperabilità tra le soluzioni per videoconferenze e dispositivi video personali esistenti in locale e Microsoft teams.

Le soluzioni offerte dai nostri partner sono costituite da componenti che possono essere distribuiti completamente cloud based o parzialmente/completamente in locale. 
     
Il diagramma seguente mostra l'architettura di alto livello delle soluzioni partner.

![Diagramma che descrive una soluzione di interoperabilità partner cloud video](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Distribuire l'interoperabilità video cloud

Quando si distribuisce una soluzione di interoperabilità cloud video, è importante capire che si sta distribuendo una soluzione partner. I passaggi generali da eseguire per distribuire l'interoperabilità video cloud sono elencati nel diagramma seguente.

![Diagramma che descrive la distribuzione di CVI nell'organizzazione](media/deploying-cvi.png)

### <a name="plan"></a>Piano

Durante la fase di pianificazione, dovresti identificare i dispositivi che non Sostituisci con un dispositivo native teams e trovare un partner di interoperabilità cloud video in grado di supportare questi dispositivi.  

È anche importante comprendere che è necessaria una licenza per ogni utente che pianifica le riunioni in cui si vuole che un dispositivo abilitato per l'interoperabilità con il cloud video venga Unito. Tieni presente che i requisiti di licenza esatti possono essere ottenuti dal partner per l'interoperabilità cloud video. Verificare che questa operazione sia chiara prima di iniziare la distribuzione.

### <a name="configure"></a>Configurare

Il partner scelto per la distribuzione CVI fornirà un documento di distribuzione completo costituito da tutti i passaggi necessari per eseguire la distribuzione con successo all'interno dell'organizzazione. Questo includerà le porte del firewall e gli intervalli di indirizzi IP, le modifiche alla configurazione per i dispositivi e altre impostazioni che devono essere modificate.

### <a name="provision"></a>Disposizione  

Durante la fase di fornitura, le licenze verranno assegnate agli utenti appropriati in base alla guida alla configurazione dei partner. Dovrai anche passare attraverso il processo di consenso di Azure per fornire al partner l'accesso all'ambiente teams. Per altre informazioni sul processo di consenso di Azure è possibile trovare qui:https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent 

### <a name="schedule"></a>Pianificare

Dopo l'abilitazione di un utente per l'interoperabilità del cloud video, qualsiasi riunione pianificata con il componente aggiuntivo riunione teams per Outlook o il client teams avrà le informazioni aggiuntive appropriate aggiunte automaticamente alla riunione teams in modo che cloud video I dispositivi compatibili con l'interoperabilità possono partecipare a queste riunioni.

### <a name="join"></a>Partecipare a

A seconda della soluzione partner, esistono diversi modi per partecipare a una riunione abilitata per l'interoperabilità cloud video. Gli scenari di partecipazione esatta alle riunioni verranno forniti dal partner di interoperabilità cloud video. Di seguito sono elencati alcuni esempi:

- IVR (risposta vocale interattiva) 
  - Puoi effettuare la chiamata al IVR del partner usando il tenantkey @ Domain.
  - Quando ci si trova nell'IVR del partner, verrà richiesto di immettere il VTC conferenceId, che verrà quindi collegato alla riunione teams.
- Chiamata diretta 
  - Puoi effettuare direttamente la chiamata alla riunione teams senza interagire con il IVR del partner usando la caratteristica Direct Dial, usando la stringa completa di tenantkey. VTC ConferenceId @ Domain.
- Dial-One-Touch 
  - Se si dispone di una sala teams integrata, è possibile usare le funzionalità di dial-up con un solo tocco offerte dal partner (senza dover digitare una stringa di chiamata).

## <a name="manage-cloud-video-interop"></a>Gestire l'interoperabilità cloud video

Dopo la distribuzione di interoperabilità cloud video, è possibile gestire i dispositivi usando le soluzioni fornite dai partner. Ogni partner fornirà un'interfaccia amministrativa che includerà la gestione di licenze e dispositivi. 

La creazione di report è disponibile anche direttamente dall'interfaccia di amministrazione dei partner. Per altre informazioni sulle funzionalità di creazione di report, contattare il partner scelto. 

### <a name="troubleshooting-cloud-video-interop"></a>Risoluzione dei problemi di interoperabilità cloud video

L'interoperabilità cloud video è un servizio fornito dal partner. Se si verificano problemi, il primo passaggio consiste nel connettere un dispositivo con il client teams installato e connetterlo allo stesso segmento del dispositivo di interoperabilità cloud video che causa problemi. 

Se teams funziona correttamente su questo segmento e sono state seguite anche tutte le linee guida per la configurazione e la rete che il partner ha fornito, sarà necessario contattare il partner per ulteriori informazioni sulla risoluzione dei problemi. 

## <a name="powershell-for-cloud-video-interop"></a>Interoperabilità di PowerShell per cloud video

I cmdlet di PowerShell seguenti sono disponibili per automatizzare parzialmente la distribuzione di interoperabilità cloud video.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft offre criteri predefiniti per ogni partner supportato che consente di designare i partner da usare per l'interoperabilità per il video cloud.<br>Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione. Puoi assegnare questo criterio a uno o più utenti sfruttando il cmdlet Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy**: questo cmdlet consente di assegnare un criterio precostruito per l'uso nell'organizzazione o di assegnare i criteri a utenti specifici.
- **New-CsVideoInteropServiceProvider**: usare questo cmdlet per specificare informazioni su un partner CVI supportato che l'organizzazione vuole usare.
- **Set-CsVideoInteropServiceProvider**: usare questo cmdlet per aggiornare le informazioni relative a un partner CVI supportato usato dall'organizzazione.
- **Get-CsVideoInteropServiceProvider**: usare questo cmdlet per ottenere tutti i provider configurati per l'utilizzo all'interno dell'organizzazione.
- **Remove-CsVideoInteropServiceProvider**: usare questo cmdlet per rimuovere tutte le informazioni del provider relative a un provider che l'organizzazione non usa più.
