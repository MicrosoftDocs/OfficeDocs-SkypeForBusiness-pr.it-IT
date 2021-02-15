---
title: Introduzione alla registrazione basata su criteri di Teams per le chiamate & riunioni
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Informazioni sulla registrazione basata su criteri di Teams per le chiamate & riunioni
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d8949a4eaa3365857768726a523ae480a94df55
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196770"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introduzione alla registrazione basata su criteri di Teams per le chiamate & riunioni

La registrazione basata su criteri consente alle organizzazioni che adottano Microsoft Teams per le chiamate e le riunioni di stipulare, utilizzando criteri amministrativi, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per l'elaborazione e la conservazione successive, come richiesto dai criteri aziendali o normativi pertinenti.

Teams è stato migliorato per supportare l'integrazione di soluzioni di registrazione di terze parti, tra cui la funzionalità della piattaforma, le esperienze utente e le interfacce amministrative necessarie per fornire una soluzione end-to-end per la configurazione, la gestione, la registrazione, l'archiviazione e l'analisi delle comunicazioni di Teams. I miglioramenti includono API della piattaforma di comunicazione ed eventi per la registrazione, che forniscono:

- Acquisizione multimediale uniforme e di alta qualità su tutti i dispositivi e tutti gli endpoint supportati per audio, video, condivisione dello schermo e chat.

- Supporto per l'acquisizione dell'interazione tra gli utenti di Teams e gli endpoint di chiamata supportati (Teams, Teams Mobile, Skype for Business, PSTN)

- Nuovi criteri amministrativi per la registrazione della conformità, inclusa l'integrazione con i criteri e gli strumenti e gli strumenti di amministrazione di Teams esistenti

La registrazione di conformità può essere abilitata per gli utenti di Microsoft 365 A3/A5/E3/E5/Business Premium e Office 365 A3/A5/E3/E5. 

Le funzionalità di integrazione della soluzione di registrazione di conformità sono state esaminate anche in Ignite 2019 nella registrazione di conformità e nella [<span class="underline">sessione di Microsoft Teams.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Panoramica della registrazione dell'interazione con Teams

I casi d'uso per la registrazione dell'interazione possono essere di fatto suddivisi in quattro categorie principali di funzionalità di registrazione, ad esempio Convenienza, Funzionale, Organizzativo e Intercetta Legale, come illustrato nell'immagine:

![Screenshot che mostra la registrazione dell'interazione su cosa e perché.](media/recording-taxonomy.png "L'immagine mostra le categorie di registrazione.")

Ognuna di queste categorie richiede requisiti diversi per l'avvio delle registrazioni, per cosa vengono registrate, per la posizione di archiviazione, per chi vengono visualizzate le notifiche, per chi controlla l'accesso e per come viene gestita la conservazione.

| Tipo                   | Praticità (normale registrazione di Teams) | Organizzazione - Regolamentata (registrazione conformità) |
| ---------------------- | ------------------ | --------------- |
| Initiator              | Utente               | Amministratore (sistema)  |
| Destinazione                 | Per chiamata/riunione | Per utente        |
| Proprietario dello spazio di archiviazione          | Utente               | Conformità      |
| È necessaria una notifica? | Sì                | Sì             |
| Proprietario dell'accesso           | Utente               | Conformità      |
| Criteri di conservazione?      | Facoltativo           | Sì             |

Teams offre varie funzionalità per [<span class="underline">la registrazione pratica</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) e funzionale per riunioni ed eventi live. La registrazione organizzativa consente alle organizzazioni che adottano Teams per le chiamate e le riunioni di stipulare, tramite criteri amministrativi, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per le successive attività di elaborazione e conservazione, come richiesto dai criteri aziendali o normativi pertinenti. Gli utenti ai sensi di questo criterio saranno consapevoli che le loro interazioni digitali con Teams vengono registrate, ma non saranno in grado di disabilitare la registrazione e non avranno accesso alla registrazione una volta completata l'interazione. La registrazione diventa parte dell'archivio aziendale a disposizione del personale addetto alla conformità e legale per eDiscovery, il blocco a livello legale e altri usi di conservazione aziendale.

## <a name="example-user-needs"></a>Esigenze degli utenti di esempio

<table>
<thead>
<tr class="header">
<th><strong>Utente tipo</strong></th>
<th><strong>Esigenze</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utenti registrati</td>
<td><ul>
<li><p>Ricevere una notifica quando è in corso la registrazione.</p></li>
<li><p>Essere informati quando l'errore del criterio e/o del registratore causa modifiche nel comportamento delle chiamate.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Amministratore per le comunicazioni</td>
<td><ul>
<li><p>Comprendere perché e come applicare/applicare criteri di registrazione agli utenti/endpoint di Teams.</p></li>
<li><p>Configurare e gestire i criteri di registrazione di Teams per l'organizzazione.</p></li>
<li><p>Monitorare e risolvere i problemi relativi alla registrazione delle chiamate e delle riunioni di Teams.</p></li>
<li><p>Supportare il responsabile della conformità interno con analisi operative sull'utilizzo, la qualità e l'affidabilità.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsabile della conformità</td>
<td><ul>
<li><p>Raccogliere tutte le comunicazioni di Teams nel modo necessario per rispettare gli obblighi di conformità nei confini regionali appropriati.</p></li>
<li><p>Cercare le interazioni in base ai metadati correlati alle comunicazioni o al contenuto dell'interazione. Esempi comuni sono:</p>
<ul>
<li><p><strong>Metadati</strong> - Partecipanti, ora, direzione, numero composto, numero di origine, dati aziendali personalizzati</p></li>
<li><p><strong>Contenuto:</strong> trascrizione, valutazione, fonetica, interazioni correlate</p></li>
</ul></li>
<li><p>Analizzare e interagire con le comunicazioni raccolte, inclusa la possibilità di monitorare le interazioni durante la raccolta.</p></li>
<li><p>Garantire la sicurezza delle comunicazioni raccolte e prevenire qualsiasi manomissione.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Panoramica dell'architettura della soluzione

Le soluzioni di registrazione della conformità sono integrate con Teams, come illustrato nel diagramma seguente:

![Screenshot che mostra l'impostazione dell'app personalizzata del team](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Le immagini mostrano il flusso quando viene inviata e ricevuta una chiamata di Teams.")

## <a name="recorder"></a>Registratore

Il componente principale della soluzione di registrazione di conformità è il registratore.
I registratori sono creati come servizi scalabili basati su Azure (bot) che sfruttano la piattaforma di comunicazione [<span class="underline">di Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) e si registrano come applicazioni con Microsoft Graph. Il registratore fornisce l'interazione diretta con le [<span class="underline">API</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) della piattaforma di comunicazione delle chiamate e delle riunioni di Teams e fornisce l'endpoint per l'inserimento dei contenuti multimediali.

È [<span class="underline">disponibile un'applicazione registratore</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) di conformità di esempio che mostra come configurare il bot, creare l'istanza dell'app e assegnare i criteri di conformità. Nell'esempio sono riportati anche esempi sull'utilizzo dell'API per la registrazione di interazioni [<span class="underline">specifiche,</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)ad esempio la gestione del [<span class="underline">routing</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) delle chiamate in arrivo, la modifica degli stati di registrazione e la rimozione dell'utente che [<span class="underline">viene registrato.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)
La documentazione del grafico sulle API specifiche è disponibile qui per [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) e [<span class="underline">incomingContext.</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)

L'implementazione esatta del servizio di registrazione varia in base al partner, ma deve essere progettata per supportare più registratori per raggiungere disponibilità elevata e distribuzione geografica della distribuzione per ridurre la latenza da Teams al registratore. Inoltre, è previsto che i recorder stessi siano progettati in base alla resilienza e alla ridondanza.

I partner devono verificare la versione di rilascio minima richiesta delle API di comunicazione Microsoft Graph e degli SDK con Microsoft prima di inviare la soluzione per la certificazione, in modo da garantire il supporto di tutti i requisiti di integrazione delle registrazioni di conformità.

Due requisiti specifici che sono fondamentali per lo scenario di registrazione di conformità sono:

- Il bot Registratore deve essere distribuito in Azure

- Il bot Registratore deve essere eseguito in una macchina virtuale Windows in Azure

I requisiti di Azure e Windows VM si applicano solo al componente Bot di Teams, il che significa che un partner può implementare il resto della piattaforma a loro scelta, a condizione che soddisfi i requisiti di prestazioni e funzionalità pertinenti per la registrazione della conformità.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Provisioning e assegnazione dei criteri di registrazione della conformità

Gli amministratori IT possono determinare quali utenti devono essere registrati e quale registratore verrà usato per ogni utente, creando e assegnando criteri di registrazione di conformità. I registratori vengono automaticamente invitati a partecipare alle conversazioni in base alla configurazione di questi criteri quando si verifica un'interazione di comunicazione. I criteri di registrazione di conformità vengono gestiti con [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) e possono essere applicati a livello di tenant, utente e gruppo di sicurezza per ogni organizzazione. Ulteriori informazioni su Microsoft Docs for [<span class="underline">Meeting Policies,</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) e group policies sono disponibili in Microsoft Docs for Meeting [<span class="underline">Policies.</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)

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

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Assegnare i criteri di registrazione di conformità a un utente.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Esperienze utente

Il supporto per le notifiche è abilitato utilizzando le esperienze client di Teams. Le esperienze possono essere visive o audio.

**Client di Teams - avviso visivo**
- Desktop/Web
- Dispositivi mobili (iOS/Android)
- Telefoni di Teams
- Sale di Teams

**Altri endpoint - avviso audio**
- Telefoni SIP
- Skype for Business
- Audioconferenza
- Chiamanti PSTN

## <a name="compliance-recording-for-teams-certification-programs"></a>Registrazione della conformità per i programmi di certificazione di Teams

Oltre a pubblicare API disponibili pubblicamente che consentono ai partner di sviluppare e integrare soluzioni CCaaS con Teams, abbiamo sviluppato la registrazione di conformità per il programma di certificazione Microsoft Teams per offrire ai clienti la garanzia che la soluzione di ogni partner partecipante è stata testata e verificata per fornire la qualità, la compatibilità e l'affidabilità che si aspettano dalle soluzioni Microsoft.  

I seguenti partner hanno certificato la loro soluzione per Microsoft Teams.

|Partner|Sito Web della soluzione |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


I partner seguenti stanno certificando la loro soluzione per Microsoft Teams.

|Partner|Sito Web della soluzione |
|:--|:--|
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Innovazione quercia |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Casella rossa |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Questo elenco verrà aggiornato man appena altri partner si uniranno e soddisfino i criteri di certificazione.

## <a name="next-steps"></a>Passaggi successivi

Se si è un fornitore che sta cercando di iscriversi al programma di certificazione, inviare un messaggio di posta <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com.</a>
