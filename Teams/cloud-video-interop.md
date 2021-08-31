---
title: Interoperabilità video nel cloud per Microsoft Teams.
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
description: Usare Cloud Video Interop come soluzione intermedia per consentire ai dispositivi delle sale riunioni di terze parti di partecipare Microsoft Teams riunioni.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e48b29ec04d10c899d646f4a28605e40fc2da09
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725505"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilità video nel cloud per Microsoft Teams.

Cloud Video Interop (CVI) è una soluzione di terze parti qualificata Microsoft che consente alle sale riunioni di terze parti (telepresenza) e ai dispositivi video personali (VTC) di partecipare a Microsoft Teams riunioni.
 
Con Microsoft Teams, si ottiene una collaborazione ricca di contenuti online in riunioni che includono audio, video e condivisione di contenuti. Questa funzionalità può essere apprezzata dal desktop e dal client Web, oltre che da molti dispositivi partner che si integrano in modo nativo con Microsoft Teams. Tuttavia, molti clienti hanno già investito in dispositivi di videoconferenza e di comunicazione video personale, che possono essere costosi da aggiornare. Cloud Video Interop offre una soluzione semplice, che consente di continuare a usare le soluzioni esistenti fino a quando non si è pronti per l'aggiornamento.

Con Cloud Video Interop, Microsoft Teams offre un'esperienza di riunione nativa per tutti i partecipanti, nelle sale riunioni o all'interno Teams clienti.

### <a name="is-cloud-video-interop-for-me"></a>Cloud Video Interop è per me?

Cloud Video Interop fornisce un servizio intermedio durante la transizione a una soluzione Microsoft Teams nativa completa, usando Teams endpoint. Il servizio fornito deve far parte del percorso di migrazione.

Cloud Video Interop è destinato ai clienti che soddisfano i criteri seguenti:

- Avere una distribuzione di grandi dimensioni di dispositivi per sale riunioni e dispositivi video personali (oltre 50 dispositivi) non idonei per l'integrazione diretta con Microsoft Teams
- Sono supportati da uno dei nostri partner cloud Video Interop
- Si vuole mantenere il valore dell'investimento nei dispositivi della sala riunioni e nei dispositivi video personali correnti durante la migrazione a una soluzione Microsoft Teams nativa

Anche se Cloud Video Interop offre un'ottima soluzione intermedia, incoraggiamo i clienti a esaminare a lungo termine le soluzioni native per riunioni Teams, ad esempio Teams Room Systems. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 Enti pubblici degli Stati Uniti e servizi di terze parti

Office 365 offre la possibilità di integrare applicazioni di terze parti nei siti di SharePoint Online, nelle applicazioni Skype for Business, Teams e Office incluse in Microsoft 365 Apps for enterprise( ad esempio Word, Excel, PowerPoint e Outlook) e Outlook Web App. Inoltre, Office 365'integrazione con provider di servizi di terze parti. Queste applicazioni e servizi di terze parti possono comportare l'archiviazione, la trasmissione e l'elaborazione dei dati dei clienti dell'organizzazione in sistemi di terze parti esterni all'infrastruttura di Office 365 e quindi non coperti dagli impegni di conformità e protezione dei dati di Office 365. **È consigliabile esaminare le informative sulla privacy e la conformità fornite da terze parti durante la valutazione dell'uso appropriato di questi servizi per l'organizzazione.**



### <a name="partners-certified-for-microsoft-teams"></a>Partner certificati per Microsoft Teams

I partner seguenti hanno soluzioni di interoperabilità video per Microsoft Teams. L'azienda può scegliere di collaborare con qualsiasi combinazione di questi partner all'interno dell'azienda. 

|Partner|Soluzione per i partner|
|----|---|
|![Logo che rappresenta Poly RealConnect.](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Servizio Poly RealConnect</a> |
|![Logo che rappresenta Pexip Infinity.](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity per Microsoft Teams</a> | 
|![Logo che rappresenta bluejeans Gateway.](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Gateway BlueJeans per Microsoft Teams</a> |
|![Logo che rappresenta Cisco CVI.](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Integrazione video Cisco Webex per Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Panoramica sull'interoperabilità di Cloud Video

Cloud Video Interop è un servizio di terze parti offerto dai nostri partner per fornire l'interoperabilità tra le soluzioni di videoconferenza esistenti e le soluzioni di dispositivi video personali locali e Microsoft Teams.

Le soluzioni offerte dai partner sono costituite da componenti che possono essere distribuiti completamente basati sul cloud o parzialmente/completamente in locale. 
     
Il diagramma seguente mostra l'architettura di alto livello delle soluzioni per i partner.

![Diagramma che descrive una soluzione Teams cloud Video Interop.](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Distribuire l'interoperabilità video cloud

Quando si distribuisce una soluzione Cloud Video Interop, è importante comprendere che si sta distribuendo una soluzione per i partner. I passaggi generali da eseguire per distribuire Cloud Video Interop sono elencati nel diagramma seguente.

![Diagramma che descrive la distribuzione di CVI nell'organizzazione.](media/deploying-cvi.png)

### <a name="plan"></a>Piano

Durante la fase del piano, è consigliabile identificare i dispositivi che non verranno sostituiti con un dispositivo Teams nativo e trovare un partner Cloud Video Interop in grado di supportare questi dispositivi.  

È anche importante tenere presente che è necessaria una licenza per ogni utente che pianifica le riunioni a cui si vuole partecipare un dispositivo abilitato per Cloud Video Interop. Tenere presente che i requisiti di licenza esatti possono essere ottenuti dal partner Cloud Video Interop. Assicurarsi che questa opzione sia chiara prima di avviare la distribuzione.

### <a name="configure"></a>Configurare

Il partner scelto per la distribuzione di CVI fornirà un documento di distribuzione completo costituito da tutti i passaggi necessari per la distribuzione corretta all'interno dell'organizzazione. Sono incluse le porte del firewall e gli intervalli IP, le modifiche alla configurazione per i dispositivi e altre impostazioni che devono essere modificate.

### <a name="provision"></a>Provisioning  

Durante la fase di provisioning, le licenze verranno assegnate agli utenti appropriati in base alla guida alla configurazione del partner. Sarà anche necessario eseguire il processo di consenso di Azure per fornire al partner l'accesso all'Teams locale. Vedere [Autorizzazioni e consenso nell'endpoint Microsoft Identity Platform](/azure/active-directory/develop/v2-permissions-and-consent) per altre informazioni sul processo di consenso di Azure.

### <a name="schedule"></a>Pianificazione

Dopo che un utente è stato abilitato per Cloud Video Interop, qualsiasi riunione pianificata con il componente aggiuntivo per riunioni Teams per Outlook o il client di Teams avrà automaticamente le informazioni aggiuntive appropriate aggiunte alla riunione di Teams in modo che i dispositivi compatibili con Cloud Video Interop possano partecipare a queste riunioni.

### <a name="join"></a>Partecipa

A seconda della soluzione per i partner, esistono diversi modi per partecipare a una riunione abilitata per Cloud Video Interop. Gli scenari di partecipazione alla riunione esatti verranno forniti dal partner Cloud Video Interop. Di seguito sono elencati alcuni esempi:

- IVR (Interactive Voice Response) 
  - È possibile accedere all'IVR del partner usando il tenantkey@domain.
  - Quando si è nell'IVR del partner, verrà richiesto di immettere l'ID conferenza VTC, che verrà quindi connesso alla riunione Teams riunione.
- Chiamata diretta 
  - È possibile accedere direttamente alla riunione Teams senza interagire con l'IVR del partner usando la funzionalità di chiamata diretta, usando la stringa completa di tenantkey. VTC ConferenceId@domain.
- Chiamata con un solo tocco 
  - Se si dispone di una sala Teams, è possibile usare le funzionalità di composizione con un solo tocco offerte dal partner (senza bisogno di digitare alcuna stringa di chiamata).

## <a name="manage-cloud-video-interop"></a>Gestire l'interoperabilità di Cloud Video

Dopo la distribuzione di Cloud Video Interop, è possibile gestire i dispositivi usando le soluzioni fornite dai nostri partner. Ogni partner fornirà un'interfaccia amministrativa che includerà sia la gestione delle licenze che quella dei dispositivi. 

La creazione di report è disponibile anche direttamente dall'interfaccia amministrativa dei partner. Per altre informazioni sulle funzionalità di creazione di report, contattare il partner scelto. 

### <a name="troubleshooting-cloud-video-interop"></a>Risoluzione dei problemi di interoperabilità di Cloud Video

Cloud Video Interop è un servizio fornito dai partner. Se si verificano problemi, il primo passaggio consiste nel connettere un dispositivo in cui è installato il client Teams e collegarlo allo stesso segmento del dispositivo Cloud Video Interop che causa problemi. 

Se Teams funzioni correttamente in questo segmento e sono state seguite anche tutte le linee guida di rete e configurazione fornite dal partner, è necessario contattare il partner per ulteriori informazioni sulla risoluzione dei problemi. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell per l'interoperabilità video cloud

I cmdlet di PowerShell seguenti sono disponibili per automatizzare (parzialmente) la distribuzione di Cloud Video Interop.

- **Get-CsTeamsVideoInteropServicepolicy:** Microsoft fornisce criteri predefiniti per ognuno dei partner supportati che consentono di designare i partner da usare per Cloud Video Interop.<br>Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione. È possibile assegnare questo criterio a uno o più utenti usando il cmdlet Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy:** questo cmdlet consente di assegnare criteri predefiniti da usare nell'organizzazione o di assegnarli a utenti specifici.
- **New-CsVideoInteropServiceProvider:** usare questo cmdlet per specificare le informazioni su un partner CVI supportato che l'organizzazione vuole usare.
- **Set-CsVideoInteropServiceProvider:** usare questo cmdlet per aggiornare le informazioni su un partner CVI supportato utilizzato dall'organizzazione.
- **Get-CsVideoInteropServiceProvider:** usare questo cmdlet per ottenere tutti i provider configurati per l'uso all'interno dell'organizzazione.
- **Remove-CsVideoInteropServiceProvider:** usare questo cmdlet per rimuovere tutte le informazioni sul provider relative a un provider non più utilizzato dall'organizzazione.