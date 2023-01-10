---
title: Interoperabilità video nel cloud per Microsoft Teams.
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Usare l'interoperabilità video cloud come soluzione intermedia per consentire ai dispositivi delle sale riunioni di terze parti di partecipare alle riunioni di Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37201c788618da1544d4f00b743907dc22ff6366
ms.sourcegitcommit: 1398c778e46b0d81c9710cd70d3818a2b7af995a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2023
ms.locfileid: "69749012"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilità video nel cloud per Microsoft Teams.

Cloud Video Interop (CVI) è una soluzione di terze parti qualificata Microsoft che consente alle sale riunioni di terze parti (telepresenza) e ai dispositivi video personali (VTC) di partecipare alle riunioni di Microsoft Teams.
 
Con Microsoft Teams si ottiene una collaborazione di contenuti online avanzata in riunioni che includono audio, video e condivisione di contenuti. Ciò può essere apprezzato tramite il client desktop e Web, nonché attraverso molti dispositivi partner che si integrano in modo nativo con Microsoft Teams. Tuttavia, molti clienti hanno già investito in teleconferenze video e dispositivi di comunicazione video personale, che possono essere costosi da aggiornare. Cloud Video Interop offre una soluzione semplice, che consente di continuare a usare le soluzioni esistenti fino a quando non si è pronti per l'aggiornamento.

Con Cloud Video Interop, Microsoft Teams offre un'esperienza di riunione nativa per tutti i partecipanti, nelle sale riunioni o all'interno dei client di Teams.

### <a name="is-cloud-video-interop-for-me"></a>Cloud Video Interop è per me?

Cloud Video Interop offre un servizio intermedio durante la transizione a una soluzione nativa completa di Microsoft Teams, utilizzando gli endpoint di Teams. Il servizio fornito deve far parte del percorso di migrazione.

Cloud Video Interop è destinato ai clienti che soddisfano i seguenti criteri:

- Disporre di una distribuzione di grandi dimensioni di dispositivi delle sale riunioni e di dispositivi video personali (oltre 50 dispositivi) non qualificati per l'integrazione diretta con Microsoft Teams
- Sono supportati da uno dei nostri partner Cloud Video Interop
- Mantenere il valore del loro investimento nei dispositivi delle sale riunioni correnti e nei dispositivi video personali durante la migrazione a una soluzione nativa di Microsoft Teams

Anche se Cloud Video Interop offre un'ottima soluzione intermedia, invitiamo i nostri clienti a esaminare le soluzioni native per le riunioni di Teams, come Teams Room Systems, a lungo termine. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 il governo degli Stati Uniti e i servizi di terze parti

Office 365 offre la possibilità di integrare applicazioni di terze parti in siti di SharePoint Online, Skype for Business, Teams, applicazioni Office incluse in Microsoft 365 Apps for enterprise (come Word, Excel, PowerPoint e Outlook) e Outlook Web App. Inoltre, Office 365 supporta l'integrazione con provider di servizi di terze parti. Queste applicazioni e servizi di terze parti potrebbero implicare l'archiviazione, la trasmissione e l'elaborazione dei dati dei clienti dell'organizzazione su sistemi di terze parti esterni all'infrastruttura di Office 365 e quindi non coperti dagli impegni in materia di conformità e protezione dei dati Office 365. **È consigliabile esaminare le informative sulla privacy e la conformità fornite dalle terze parti durante la valutazione dell'uso appropriato di questi servizi per l'organizzazione.**

> [!NOTE]
> Pexip Teams Connector deve essere ospitato nelle aree geografiche Arizona o Texas Azure per GCC High. L'area geografica di Virginia Azure non supporta l'hosting di Pexip Teams Connector per GCC High.

### <a name="partners-certified-for-microsoft-teams"></a>Partner certificati per Microsoft Teams

I partner seguenti hanno soluzioni di interoperabilità video per Microsoft Teams. L'azienda può scegliere di collaborare con qualsiasi combinazione di questi partner all'interno dell'azienda. 

|Partner|Soluzione per i partner|
|----|---|
|![Logo che rappresenta Poly RealConnect.](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Servizio Poly RealConnect</a> |
|![Logo che rappresenta Pexip Infinity.](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity per Microsoft Teams</a> | 
|![Logo che rappresenta BlueJeans Gateway.](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway per Microsoft Teams</a> |
|![Logo che rappresenta Cisco CVI.](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Integrazione video di Cisco Webex per Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Panoramica sull'interoperabilità dei video cloud

Cloud Video Interop è un servizio di terze parti offerto dai nostri partner per fornire l'interoperabilità tra le videoconferenze esistenti e le soluzioni di dispositivi video personali in locale e Microsoft Teams.

Le soluzioni offerte dai nostri partner sono costituite da componenti che possono essere distribuiti completamente sul cloud o parzialmente/completamente in locale. 
     
Il diagramma seguente illustra l'architettura generale delle soluzioni dei partner.

![Diagramma che descrive una soluzione partner teams Cloud Video Interop.](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Distribuire interoperabilità video cloud

Quando si distribuisce una soluzione di interoperabilità video cloud, è importante tenere presente che si sta distribuendo una soluzione partner. I passaggi generali da eseguire per distribuire Cloud Video Interop sono elencati nel diagramma seguente.

![Diagramma che descrive la distribuzione di CVI nell'organizzazione.](media/deploying-cvi.png)

### <a name="plan"></a>Piano

Durante la fase del piano, è necessario identificare i dispositivi che non si sostituiranno con un dispositivo Teams nativo e trovare un partner di interoperabilità video cloud in grado di supportare questi dispositivi.  

È anche importante tenere presente che è necessaria una licenza per ogni utente che pianificherà le riunioni a cui si vuole partecipare a un dispositivo abilitato all'interoperabilità dei video cloud. Si noti che i requisiti di licenza esatti possono essere ottenuti dal partner Cloud Video Interop. Assicurarsi che sia chiaro prima di avviare la distribuzione.

### <a name="configure"></a>Configurare

Il partner scelto per la distribuzione di CVI fornirà un documento di distribuzione completo costituito da tutti i passaggi necessari per distribuire correttamente all'interno dell'organizzazione. Saranno incluse le porte e gli intervalli IP del firewall, le modifiche di configurazione per i dispositivi e altre impostazioni che è necessario modificare.

### <a name="provision"></a>Provvigione  

Durante la fase di provisioning, le licenze verranno assegnate agli utenti appropriati in base alla guida alla configurazione del partner. Sarà anche necessario completare il processo di consenso di Azure per fornire al partner l'accesso all'ambiente Teams. Per altre informazioni sul processo di consenso di Azure, vedere [Autorizzazioni e consenso nell'endpoint di Microsoft Identity Platform](/azure/active-directory/develop/v2-permissions-and-consent).

### <a name="schedule"></a>Programma

Dopo che un utente è abilitato per l'interoperabilità video cloud, tutte le riunioni pianificate utilizzando il componente aggiuntivo Riunione di Teams per Outlook o il client di Teams avranno automaticamente aggiunto le informazioni aggiuntive appropriate alla riunione di Teams in modo che i dispositivi compatibili con Cloud Video Interop possano partecipare a queste riunioni.

### <a name="join"></a>Unirsi

A seconda della soluzione partner, esistono diversi modi per partecipare a una riunione abilitata per l'interoperabilità dei video cloud. Scenari di partecipazione alle riunioni esatti verranno forniti dal partner di interoperabilità video cloud. Di seguito sono elencati alcuni esempi:

- IVR (Risposta vocale interattiva) 
  - Puoi accedere all'IVR del partner tramite l'tenantkey@domain.
  - Quando sei nell'IVR partner, ti verrà chiesto di immettere il VTC conferenceId, che ti connetterà alla riunione di Teams.
- Telefono diretto 
  - È possibile accedere direttamente alla riunione di Teams senza interagire con l'IVR del partner usando la funzione di composizione diretta, usando la stringa completa di chiave tenant. ConferenceId@domain VTC.
- Comando radiale con un tocco 
  - Se hai una sala riunioni di Teams integrata, puoi usare le funzionalità di chiamata one-touch offerte dal tuo partner (senza dover digitare alcuna stringa di chiamata).

## <a name="manage-cloud-video-interop"></a>Gestire l'interoperabilità dei video cloud

Dopo la distribuzione di Cloud Video Interop, è possibile gestire i dispositivi utilizzando le soluzioni fornite dai nostri partner. Ogni partner fornirà all'utente un'interfaccia amministrativa che includerà sia la gestione delle licenze che quella dei dispositivi. 

La creazione di report è disponibile anche direttamente dall'interfaccia di amministrazione del partner. Per altre informazioni sulle funzionalità di creazione di report, contattare il partner di propria scelta. 

### <a name="troubleshooting-cloud-video-interop"></a>Risoluzione dei problemi relativi all'interoperabilità dei video cloud

Cloud Video Interop è un servizio fornito dal partner. Se si verificano problemi, il primo passaggio consiste nel connettere un dispositivo in cui è installato il client teams e collegarlo allo stesso segmento del dispositivo Cloud Video Interop che causa problemi. 

Se Teams funziona correttamente su questo segmento e hai seguito anche tutte le linee guida per la rete e la configurazione fornite dal partner, dovrai contattare il partner per ulteriori soluzioni. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell per l'interoperabilità dei video cloud

I cmdlet di PowerShell seguenti sono disponibili per automatizzare (parzialmente) la distribuzione di Cloud Video Interop.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft fornisce criteri predefiniti per ognuno dei partner supportati che consentono di designare i partner da utilizzare per l'interoperabilità video cloud.<br>Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione. È possibile assegnare questo criterio a uno o più utenti sfruttando il cmdlet Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy**: questo cmdlet consente di assegnare un criterio precostruito per l'uso nell'organizzazione o di assegnarlo a utenti specifici.
- **New-CsVideoInteropServiceProvider**: utilizzare questo cmdlet per specificare le informazioni su un partner CVI supportato che l'organizzazione desidera utilizzare.
- **Set-CsVideoInteropServiceProvider**: usare questo cmdlet per aggiornare le informazioni su un partner CVI supportato utilizzato dall'organizzazione.
- **Get-CsVideoInteropServiceProvider**: utilizzare questo cmdlet per ottenere tutti i provider configurati per l'uso all'interno dell'organizzazione.
- **Remove-CsVideoInteropServiceProvider**: utilizzare questo cmdlet per rimuovere tutte le informazioni del provider relative a un provider che l'organizzazione non usa più.
