---
title: Interoperabilità dei video cloud per Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Usare l'interoperabilità dei video cloud come soluzione intermedia per consentire ai dispositivi delle sale riunioni di terze parti di partecipare alle riunioni di Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a9bf3cade5c17a8d3649a29ca999dec1f909624
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611850"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilità dei video cloud per Microsoft Teams

Cloud Video Interop (CVI) è una soluzione di terze parti qualificata Microsoft che consente a sale riunioni di terze parti (telepresenza) e dispositivi video personali (VTCs) di partecipare alle riunioni di Microsoft Teams.
 
Con Microsoft Teams, si ottiene una collaborazione ricca di contenuti online in riunioni che includono audio, video e condivisione di contenuti. Questo può essere apprezzato attraverso il client desktop e web, oltre che attraverso molti dispositivi partner che si integrano in modo nativo con Microsoft Teams. Tuttavia, molti clienti hanno già investito nelle videoconferenze e nei dispositivi di comunicazione video personali, il che può essere costoso per l'aggiornamento. Cloud Video Interop offre una soluzione semplice, che consente di continuare a usare le soluzioni esistenti finché non si è pronti per l'aggiornamento.

Grazie all'interoperabilità dei video cloud, Microsoft Teams offre un'esperienza di riunione nativa per tutti i partecipanti, nelle sale riunioni o all'interno dei client di Teams.

### <a name="is-cloud-video-interop-for-me"></a>L'interoperabilità dei video nel cloud è per me?

Cloud Video Interoperabilità offre un servizio intermedio durante la transizione a una soluzione Microsoft Teams nativa completa, usando gli endpoint di Teams. Il servizio fornito deve fare parte del percorso di migrazione.

L'interoperabilità dei video cloud è stata progettata per i clienti che soddisfano i criteri seguenti:

- Avere una grande distribuzione di dispositivi sala riunioni e di dispositivi video personali (più di 50 dispositivi) non qualificati per l'integrazione diretta con Microsoft Teams
- Sono supportati da uno dei nostri partner Cloud Video Interoperabilità
- Vogliono mantenere il valore dei loro investimenti nei dispositivi delle sale riunioni correnti e nei dispositivi video personali durante la migrazione a una soluzione Microsoft Teams nativa

Anche se Cloud Video Interoperabilità offre un'ottima soluzione intermedia, consigliamo ai nostri clienti di esaminare le soluzioni native teams per le riunioni, come Teams Room Systems, a lungo termine. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 US Government e servizi di terze parti

Office 365 consente di integrare applicazioni di terze parti nei siti di SharePoint Online, Skype for Business, Teams, applicazioni Office incluse in Microsoft 365 Apps per le aziende (come Word, Excel, PowerPoint e Outlook) e Outlook Web App. Inoltre, Office 365 supporta l'integrazione con provider di servizi di terze parti. Questi servizi e applicazioni di terze parti possono implicare l'archiviazione, la trasmissione e l'elaborazione dei dati dei clienti dell'organizzazione su sistemi di terze parti esterni all'infrastruttura di Office 365 e pertanto non sono coperti dagli impegni in fatto di conformità e protezione dei dati di Office 365. **È consigliabile consultare le informative sulla privacy e la conformità fornite da terze parti durante la valutazione dell'uso appropriato di questi servizi per l'organizzazione.**



### <a name="partners-certified-for-microsoft-teams"></a>Partner certificati per Microsoft Teams

I partner seguenti hanno soluzioni di interoperabilità video per Microsoft Teams. L'azienda può scegliere di collaborare con qualsiasi combinazione di questi partner all'interno dell'azienda. 

|Partner|Soluzione per i partner|
|----|---|
|![Logo che rappresenta Poly RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Servizio Poly RealConnect</a> |
|![Il logo che rappresenta Pexip Infinito](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinito per Microsoft Teams</a> | 
|![Logo che rappresenta Il Gateway BlueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway per Microsoft Teams</a> |
|![Il logo che rappresenta Cisco CVI](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Integrazione video Cisco Webex per Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Panoramica dell'interoperabilità di Cloud Video

Cloud Video Interoperabilità è un servizio di terze parti offerto dai nostri partner per fornire l'interoperabilità tra le attuali soluzioni di videoconferenze e dispositivi video personali in sede e Microsoft Teams.

Le soluzioni offerte dai nostri partner sono costituite da componenti che possono essere distribuiti in locale o parzialmente basati sul cloud. 
     
Il diagramma seguente mostra l'architettura di alto livello delle soluzioni partner.

![Diagramma che descrive una soluzione partner per l'interoperabilità di Cloud Video di Teams](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Distribuzione dell'interoperabilità con i video cloud

Quando si distribuisce una soluzione di interoperabilità di Cloud Video, è importante sapere che si sta distribuendo una soluzione partner. I passaggi generali da seguire per distribuire Cloud Video Interoperabilità sono elencati nel diagramma seguente.

![Diagramma che descrive la distribuzione di CVI nell'organizzazione](media/deploying-cvi.png)

### <a name="plan"></a>Piano

Durante la fase del piano, è consigliabile identificare i dispositivi che non verranno sostituiti con un dispositivo Teams nativo e trovare un partner cloud di interoperabilità video in grado di supportare questi dispositivi.  

È anche importante tenere presente che è necessaria una licenza per ogni utente che pianifica riunioni a cui si vuole che un dispositivo cloud video abilitato per l'interoperabilità si unisca. Si noti che i requisiti di licenza esatti possono essere ottenuti dal partner Cloud Video Interoperabilità. Assicurarsi che questa impostazione sia chiara prima di iniziare la distribuzione.

### <a name="configure"></a>Configura

Il partner scelto per la distribuzione CVI fornirà un documento di distribuzione completo costituito da tutti i passaggi necessari per la corretta distribuzione all'interno dell'organizzazione. Ciò includerà le porte e gli intervalli IP del firewall, le modifiche alla configurazione per i dispositivi e altre impostazioni che devono essere modificate.

### <a name="provision"></a>Provisioning  

Durante la fase di provisioning, le licenze verranno assegnate agli utenti appropriati in base alla guida alla configurazione del partner. Sarà anche necessario eseguire il processo di consenso di Azure per fornire al partner l'accesso all'ambiente di Teams. Per altre informazioni sul processo di consenso di Azure, vedere Autorizzazioni e consenso nell'endpoint della piattaforma di identità [Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)

### <a name="schedule"></a>Pianificazione

Dopo l'abilito dell'utente per Cloud Video Interoperabilità, tutte le riunioni pianificate usando il componente aggiuntivo per le riunioni di Teams per Outlook o il client di Teams avranno automaticamente aggiunto le informazioni aggiuntive appropriate alla riunione di Teams in modo che i dispositivi compatibili con Cloud Video compatibile con l'interoperabilità possano partecipare a queste riunioni.

### <a name="join"></a>Partecipa

A seconda della soluzione partner, esistono diversi modi per partecipare a una riunione abilitata all'interoperabilità di Cloud Video. Gli scenari esatti per partecipare a una riunione verranno forniti dal partner cloud di interoperabilità video. Di seguito sono elencati alcuni esempi:

- IVR (Interactive Voice Response) 
  - È possibile chiamare l'IVR del partner usando il tenantkey@domain.
  - Nel partner IVR, ti verrà chiesto di immettere il valore VTC conferenceId, che ti connetterà alla riunione di Teams.
- Chiamata diretta 
  - È possibile accedere direttamente alla riunione di Teams senza interagire con l'IVR del partner utilizzando la funzione di chiamata diretta, utilizzando la stringa completa di tenantkey. VTC ConferenceId@domain.
- Chiamata con un solo tocco 
  - Se si dispone di una sala di Teams integrata, è possibile usare le funzionalità di chiamata con un solo tocco offerte dal partner (senza dover digitare alcuna stringa di composizione).

## <a name="manage-cloud-video-interop"></a>Gestire l'interoperabilità video nel cloud

Dopo la distribuzione di Cloud Video Interoperabilità, è possibile gestire i dispositivi usando le soluzioni fornite dai nostri partner. Ogni partner fornirà un'interfaccia amministrativa che includerà la gestione delle licenze e dei dispositivi. 

La creazione di report è disponibile anche direttamente dall'interfaccia amministrativa del partner. Per altre informazioni sulle funzionalità di creazione di report, contattare il partner desiderato. 

### <a name="troubleshooting-cloud-video-interop"></a>Risoluzione dei problemi di interoperabilità video nel cloud

Cloud Video Interoperabilità è un servizio fornito da un partner. In caso di problemi, il primo passaggio consiste nel connettere un dispositivo in cui è installato il client di Teams e collegarlo allo stesso segmento del dispositivo Cloud Video Interoperabilità che causa problemi. 

Se Teams funziona correttamente in questo segmento e hai seguito anche tutte le linee guida di rete e configurazione fornite dal partner, dovrai contattare il partner per ulteriori procedure di risoluzione dei problemi. 

## <a name="powershell-for-cloud-video-interop"></a>Interoperabilità di PowerShell per cloud video

I cmdlet di PowerShell seguenti sono disponibili per automatizzare (parzialmente) la distribuzione di Cloud Video Interoperabilità.

- **Get-CsTeamsVideoInteropServicepolicy:** Microsoft fornisce criteri predefiniti per ognuno dei nostri partner supportati che consentono di designare i partner da usare per l'interoperabilità con Cloud Video.<br>Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione. È possibile assegnare questo criterio a uno o più utenti usando il cmdlet Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy:** questo cmdlet consente di assegnare criteri predefiniti da utilizzare nell'organizzazione o di assegnarli a utenti specifici.
- **New-CsVideoInteropServiceProvider:** usare questo cmdlet per specificare informazioni su un partner CVI supportato che l'organizzazione vuole usare.
- **Set-CsVideoInteropServiceProvider:** usare questo cmdlet per aggiornare le informazioni su un partner CVI supportato utilizzato dall'organizzazione.
- **Get-CsVideoInteropServiceProvider:** usare questo cmdlet per ottenere tutti i provider configurati per l'uso all'interno dell'organizzazione.
- **Remove-CsVideoInteropServiceProvider:** usare questo cmdlet per rimuovere tutte le informazioni sul provider che l'organizzazione non usa più.
