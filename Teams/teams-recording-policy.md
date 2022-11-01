---
title: Introduzione alla registrazione basata sui criteri di Teams per le chiamate & le riunioni
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sulla registrazione basata sui criteri di Teams per le chiamate & le riunioni
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
- tier3
- purview-compliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088515e6d9d4fe9e6dc893d736f7baac1148c731
ms.sourcegitcommit: 86b9503eb0085e23176cb346767f880ea3a73e77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2022
ms.locfileid: "68808285"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introduzione alla registrazione basata sui criteri di Teams per le chiamate & le riunioni

La registrazione basata su criteri consente alle organizzazioni che adottano Microsoft Teams per chiamate e riunioni di stipulare, usando criteri amministrativi, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per successive elaborazioni e conservazione in base a quanto richiesto dai criteri aziendali o normativi pertinenti.

Teams è stato migliorato per supportare l'integrazione di soluzioni di registrazione di terze parti, incluse le funzionalità della piattaforma, le esperienze utente e le interfacce amministrative necessarie per fornire una soluzione end-to-end per la configurazione, la gestione, la registrazione, l'archiviazione e l'analisi delle comunicazioni di Teams. I miglioramenti includono API della piattaforma di comunicazione ed eventi per la registrazione, che forniscono:

- Acquisizione continua e di alta qualità di contenuti multimediali su tutti i dispositivi e tutti gli endpoint supportati per audio, video, condivisione dello schermo e chat.

- Supporto per l'acquisizione di interazioni tra gli utenti di Teams e gli endpoint di chiamata supportati (Teams, Teams Mobile, Skype for Business, PSTN)

- Nuovi criteri amministrativi per la registrazione della conformità, inclusa l'integrazione con gli strumenti e i criteri esistenti per le chiamate amministrative e le riunioni di Teams

La registrazione di conformità può essere abilitata per gli utenti di Microsoft 365 A3/A5/E3/E5/Business Premium e Office 365 A3/A5/E3/E5. 

Le funzionalità di integrazione della soluzione di registrazione della conformità sono state esaminate anche in Ignite 2019 nella [sessione Registrazione conformità e Microsoft Teams](https://myignite.microsoft.com/archives/IG19-VCE40).

## <a name="teams-interaction-recording-overview"></a>Panoramica sulla registrazione delle interazioni di Teams

I casi di utilizzo delle registrazioni di interazione possono essere di fatto separati in quattro categorie principali di funzionalità di registrazione: Comodità, Funzionale, Organizzativa e Intercettazione legale, come illustrato nell'immagine:

> [!div class="mx-imgBorder"]
> ![Screenshot che mostra la registrazione delle interazioni cosa e perché.](media/recording-taxonomy.png "L'immagine mostra le categorie di registrazione.")

Ognuna delle categorie prevede requisiti diversi per la modalità di avvio delle registrazioni, i contenuti registrati, la posizione di archiviazione delle registrazioni, chi riceve una notifica, chi controlla l'accesso e come viene gestita la conservazione.

| Tipo                   | Comodità (registrazione standard di Teams) | Organizzazione - Regolamentata (registrazione di conformità) |
| ---------------------- | ------------------ | --------------- |
| Iniziatore              | Utente               | Amministrazione (sistema)  |
| Target                 | Per chiamata/riunione | Per utente        |
| Proprietario dello spazio di archiviazione          | Utente               | Conformità      |
| È necessaria una notifica? | Sì                | Sì             |
| Proprietario dell'accesso           | Utente               | Conformità      |
| Criteri di conservazione?      | Facoltativo           | Sì             |

Teams offre varie funzionalità per la registrazione [pratica](./cloud-recording.md) e funzionale di riunioni ed eventi live. La registrazione organizzativa significa consentire alle organizzazioni che adottano Teams per chiamate e riunioni di stipulare, tramite criteri amministrativi, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per successive elaborazioni e conservazione come richiesto dai criteri aziendali o normativi pertinenti. Gli utenti in base a questo criterio saranno consapevoli che le loro interazioni digitali con Teams vengono registrate, ma non saranno in grado di disabilitare la registrazione e non avranno accesso alla registrazione al termine dell'interazione. La registrazione diventa parte dell'archivio aziendale disponibile per il personale legale e per la conformità per eDiscovery, il blocco legale e altri usi della conservazione aziendale.

## <a name="example-user-needs"></a>Esigenze utente di esempio

<table>
<thead>
<tr class="header">
<th>Utente tipo</th>
<th>Esigenze</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utenti registrati</td>
<td><ul>
<li><p>Ricevere una notifica quando è in corso la registrazione.</p></li>
<li><p>Essere informati quando l'errore dei criteri e/o del registratore causa modifiche al comportamento delle chiamate.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Amministratore comunicazioni</td>
<td><ul>
<li><p>Comprendere perché e come applicare/applicare criteri di registrazione agli utenti/endpoint di Teams.</p></li>
<li><p>Configurare e gestire i criteri di registrazione di Teams per l'organizzazione.</p></li>
<li><p>Monitorare e risolvere i problemi relativi alla registrazione relativi alle chiamate e alle riunioni di Teams.</p></li>
<li><p>Supporto del responsabile della conformità interno con analisi operative sull'utilizzo, la qualità e l'affidabilità.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsabile conformità</td>
<td><ul>
<li><p>Raccogliere tutte le comunicazioni di Teams nel modo necessario per rispettare gli obblighi di conformità nei confini regionali appropriati.</p></li>
<li><p>Cercare interazioni in base a metadati relativi alle comunicazioni o contenuto di interazione. Ecco alcuni esempi comuni:</p>
<ul>
<li><p><strong>Metadati</strong> - Partecipanti, tempo, direzione, numero di telefono, numero di origine, dati business personalizzati</p></li>
<li><p><strong>Contenuto</strong> : trascrizione, sentiment, fonetica, interazioni correlate</p></li>
</ul></li>
<li><p>Analizzare e interagire con le comunicazioni raccolte, inclusa la possibilità di monitorare le interazioni man mano che vengono raccolte.</p></li>
<li><p>Garantire la sicurezza delle comunicazioni raccolte e impedire manomissioni in tutte le fasi.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Panoramica dell'architettura delle soluzioni

Le soluzioni di registrazione della conformità sono integrate con Teams, come illustrato nel diagramma seguente:

> [!div class="mx-imgBorder"]
> ![Screenshot che mostra le impostazioni app personalizzate del team.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Le immagini mostrano il flusso quando una riunione o una chiamata di Teams viene inviata e ricevuta.")

> [!NOTE]
> Questa soluzione è progettata specificamente per abilitare la registrazione della conformità basata su criteri con Teams. Qualsiasi altro uso di questa soluzione non sarà supportato.

## <a name="recorder"></a>Registratore

Il componente principale della soluzione di registrazione della conformità è il registratore.
I registratori sono creati come servizi scalabili basati su Azure (bot) che [usano la piattaforma di comunicazione di Microsoft](/graph/cloud-communications-concept-overview) e si registrano come applicazioni con Microsoft Graph. Il registratore fornisce l'interazione diretta con le API della [piattaforma di comunicazione](/graph/api/resources/communications-api-overview) per chiamate e riunioni di Teams e fornisce l'endpoint per l'inserimento di contenuti multimediali.

[È disponibile un'applicazione registratore di conformità di esempio](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) che mostra come configurare il bot, creare l'istanza dell'app e assegnare i criteri di conformità. L'esempio contiene anche esempi sull'utilizzo dell'API per la registrazione di interazioni specifiche, ad esempio la gestione del routing [delle chiamate in ingresso](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , [la modifica degli stati di registrazione](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138) e [la rimozione dell'utente registrato](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
La documentazione del grafico sulle API specifiche è disponibile qui per [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) e [incomingContext](/graph/api/resources/incomingcontext).

L'implementazione esatta del servizio registratore varia in base al partner, ma deve essere progettata per supportare più registratori per ottenere disponibilità elevata e distribuzione geografica della distribuzione per ridurre la latenza da Teams a registratore. Inoltre, si prevede che i registratori stessi siano progettati tenendo conto della resilienza e della ridondanza.

I partner devono confermare la versione minima richiesta delle API per le comunicazioni di Microsoft Graph e degli SDK con Microsoft prima di inviare la loro soluzione per la certificazione per assicurarsi che tutti i requisiti di integrazione delle registrazioni di conformità siano supportati.

Due requisiti specifici fondamentali per lo scenario di registrazione della conformità sono:

- Il bot registratore deve essere distribuito in Azure

- Il bot registratore deve essere eseguito in una macchina virtuale Windows in Azure

I requisiti di Azure e Windows VM si applicano solo al componente Bot di Teams, il che significa che un partner può implementare il resto della piattaforma scelta, a condizione che possa soddisfare i requisiti funzionali e le prestazioni pertinenti per la registrazione della conformità.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Assegnazione e provisioning dei criteri di registrazione della conformità

Gli amministratori IT possono determinare quali utenti devono essere registrati e quale registratore verrà usato per ogni utente, creando e assegnando criteri di registrazione di conformità. I registratori vengono automaticamente invitati a partecipare alle conversazioni in base alla configurazione di questi criteri quando si verifica un'interazione di comunicazione. I criteri di registrazione della conformità vengono gestiti con [Microsoft PowerShell](./teams-powershell-overview.md) e possono essere applicati a livello di tenant, per utente e gruppo di sicurezza per ogni organizzazione. Altre informazioni sono disponibili in Microsoft Learn for [Meeting policies](./meeting-policies-overview.md), [calling policies](./teams-calling-policy.md) e  [group policies](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group).

1. Creare un'istanza dell'applicazione nel tenant.

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. Creare criteri di registrazione di conformità.

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   Vedere [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy).

3. Assegnare i criteri registrazione di conformità a un utente.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   Vedere [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Esperienze utente

Il supporto per le notifiche è abilitato tramite le esperienze client di Teams. Le esperienze possono essere visive o audio.

**Client di Teams - avviso visivo**
- Desktop/Web
- Dispositivi mobili (iOS/Android)
- Telefoni di Teams
- Sale di Teams

**Altri endpoint - avviso audio**
- Telefoni SIP
- Skype for Business
- Audioconferenza (avviso audio nella lingua predefinita o selezionata dall'utente)
- Chiamanti PSTN (avviso audio nella lingua predefinita dell'utente di Teams)

> [!NOTE]
> La registrazione di conformità non è supportata con le code di chiamata in modalità conferenza. Utilizza le code di chiamata in modalità trasferimento.
> La registrazione di conformità non funziona se gli utenti hanno subito un'interruzione di Internet e stanno effettuando e ricevendo chiamate PSTN tramite SBA.

## <a name="compliance-recording-for-teams-certification-programs"></a>Registrazione della conformità per i programmi di certificazione Teams

Oltre a pubblicare API disponibili pubblicamente che consentono ai partner di sviluppare e integrare soluzioni CCaaS con Teams, abbiamo sviluppato la registrazione della conformità per il programma di certificazione Microsoft Teams per offrire ai clienti la garanzia che la soluzione di ogni partner partecipante sia stata testata e verificata per fornire la qualità, la compatibilità e l'affidabilità che si aspettano dalle soluzioni Microsoft.  

I partner seguenti hanno certificato la loro soluzione per Microsoft Teams.<br/><br/>

|Partner|Sito Web della soluzione |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Doppiatrice |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Tecnologia approfondita |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|Mida Solutions |[https://www.midasolutions.com/recorder-for-teams/](https://www.midasolutions.com/recorder-for-teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Innovazione rovere |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|Casella rossa |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/red-box-partners/microsoft-integration/compliance-recording-for-microsoft-teams)  |
|Lago Theta |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Innovazione rovere |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
I partner seguenti stanno certificando la loro soluzione per Microsoft Teams.<br/><br/>

|Partner|Sito Web della soluzione |
|:--|:--|
|GuardRec |[https://www.guardrec.com/en/teams-compliance-recording/](https://www.guardrec.com/en/teams-compliance-recording/) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Redwood Technologies |[https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/](https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/) |


Questo elenco verrà aggiornato man mano che altri partner partecipano e soddisfano i criteri di certificazione.


## <a name="next-steps"></a>Passaggi successivi

Se si è un fornitore che desidera partecipare al programma di certificazione, compilare [questo modulo](https://aka.ms/CallingPlatformIntake) come passaggio successivo. Se è necessario fornire ulteriore contesto e dettagli, inviare un messaggio di posta elettronica a [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com).
