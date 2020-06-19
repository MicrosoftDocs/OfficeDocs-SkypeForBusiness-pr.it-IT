---
title: Introduzione alla registrazione basata sui criteri per i team per chiamare & riunioni
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Informazioni sulla registrazione basata su criteri team per la chiamata di & riunioni
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
ms.openlocfilehash: 00727602aed5eee205a01b01e1ab01218c5b2352
ms.sourcegitcommit: 8acc2ed4cb807f941a6526ec8aad562536f45aa6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44804680"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introduzione alla registrazione basata sui criteri per i team per le chiamate & riunioni

La registrazione basata su criteri consente alle organizzazioni che adottano Microsoft teams per la chiamata e le riunioni di stabilire, usando un criterio amministrativo, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per l'elaborazione e la conservazione successive, come richiesto dai pertinenti criteri aziendali o normativi.

Teams è stato migliorato per supportare l'integrazione di soluzioni di registrazione di terze parti, incluse le funzionalità della piattaforma, le esperienze degli utenti e le interfacce amministrative necessarie per creare una soluzione completa per la configurazione, la gestione, la registrazione, l'archiviazione e l'analisi delle comunicazioni di teams. Sono incluse le API della piattaforma di comunicazione e gli eventi per la registrazione, che offrono:

- Acquisizione multimediale senza soluzione di continuità e di alta qualità tra dispositivi e tutti gli endpoint supportati per audio, video, condivisione dello schermo e chat.

- Supporto per l'acquisizione dell'interazione tra utenti di team e endpoint di chiamata supportati (teams, teams mobile, Skype for business, PSTN)

- Nuovi criteri amministrativi per la registrazione della conformità, inclusa l'integrazione con i team e i criteri di gestione delle chiamate e delle riunioni esistenti

- Abilitato per gli utenti di team con una licenza separata

Le funzionalità di integrazione della soluzione per la registrazione della conformità sono state esaminate anche in Ignite 2019 nella [<span class="underline">sessione di registrazione conformità e Microsoft teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).

## <a name="teams-interaction-recording-overview"></a>Panoramica della registrazione delle interazioni tra Teams

I casi di utilizzo della registrazione delle interazioni possono essere effettivamente separati in quattro categorie principali di funzionalità di registrazione: convenienza, funzionalità, organizzazione e intercettazione lecite, come illustrato nell'immagine.

![Screenshot che mostra la registrazione delle interazioni che cosa e perché.](media/recording-taxonomy.png "L'immagine mostra le categorie di registrazione.")

Ognuna delle categorie comporta requisiti diversi per il modo in cui vengono avviate le registrazioni, cosa viene registrato, in cui vengono archiviate le registrazioni, chi viene avvisato, chi controlla l'accesso e come viene gestito il mantenimento.

|                        | Convenienza        | Funzionale         | Org-generale      | Org-regolato | Intercettazione legale   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| Iniziatore              | Utente               | App/soluzione       | Amministratore (sistema)     | Amministratore (sistema)  | LEA                |
| Destinazione                 | Per chiamata/riunione | Per chiamata/riunione | Per chiamata/riunione | Per utente        | Per-endpoint/DID |
| Proprietario dello spazio di archiviazione          | Utente               | App                | Admin              | Conformità      | LEA                |
| Notifica obbligatoria? | Sì                | Sì                | Sì                | Sì             | No                 |
| Proprietario di Access           | Utente               | App                | Admin              | Conformità      | LEA                |
| Criteri di conservazione      | Facoltativo           | Sì                | Sì                | Sì             | Sì                |

Teams offre varie funzionalità per [<span class="underline">una registrazione comoda</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) e funzionale per riunioni e eventi live. La registrazione organizzativa consente alle organizzazioni che adottano team per la chiamata e le riunioni di stipulare, tramite criteri amministrativi, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per l'elaborazione e la conservazione successive, come richiesto dai pertinenti criteri aziendali o normativi. Gli utenti in questo criterio sapranno che le loro interazioni digitali con i team vengono registrate ma non saranno in grado di disabilitare la registrazione e non avranno accesso alla registrazione dopo il completamento dell'interazione. La registrazione diventa parte dell'archivio organizzativo disponibile per la conformità e il personale legale per eDiscovery, blocco legale e altri usi di conservazione aziendale.

## <a name="example-user-needs"></a>Esempio di esigenze degli utenti

<table>
<thead>
<tr class="header">
<th><strong>Utente tipo</strong></th>
<th><strong>Deve</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utenti registrati</td>
<td><ul>
<li><p>Ricevere una notifica quando la registrazione è in corso.</p></li>
<li><p>Essere informati quando i criteri e/o l'errore del registratore causano modifiche al comportamento delle chiamate.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Amministratore delle comunicazioni</td>
<td><ul>
<li><p>Capire perché e come applicare/applicare i criteri di registrazione agli utenti/endpoint di teams.</p></li>
<li><p>Configurare e gestire i criteri di registrazione dei team per l'organizzazione.</p></li>
<li><p>Monitorare e risolvere i problemi relativi alla registrazione con le chiamate e le riunioni del team.</p></li>
<li><p>Supportare Internal Compliance Officer con analisi operativa sull'uso, la qualità e l'affidabilità.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsabile della conformità</td>
<td><ul>
<li><p>Raccogliere tutte le comunicazioni di Teams nel modo necessario per rispettare gli obblighi di conformità nei limiti regionali appropriati.</p></li>
<li><p>Cercare interazioni basate su metadati correlati alla comunicazione o sul contenuto di interazione. Gli esempi comuni includono:</p>
<ul>
<li><p><strong>Metadati</strong> - Partecipanti, ora, direzione, numero di telefono, numero di origine, dati aziendali personalizzati</p></li>
<li><p><strong>Contenuto</strong> : trascrizione, sentimento, fonetica, interazioni correlate</p></li>
</ul></li>
<li><p>Analizzare e interagire con le comunicazioni raccolte, inclusa la possibilità di monitorare le interazioni Man mano che vengono raccolte.</p></li>
<li><p>Garantire la sicurezza delle comunicazioni raccolte e impedire manomissioni in tutte le fasi.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Panoramica dell'architettura della soluzione

Le soluzioni di registrazione conformità sono integrate con i team, come illustrato nel diagramma seguente:

![Schermata che mostra l'impostazione dell'app personalizzata del team](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Le immagini mostrano il flusso quando viene inviata e ricevuta una riunione o una chiamata di teams.")

## <a name="recorder"></a>Registratore

Il componente principale della soluzione di registrazione della conformità è il registratore.
I registratori vengono creati come servizi basati su Azure scalabili (bot) che [<span class="underline">sfruttano la piattaforma di comunicazioni Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) e si iscrivono come applicazioni con Microsoft Graph. Il registratore fornisce l'interazione diretta con le [<span class="underline">API della piattaforma di comunicazione</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) per le chiamate e le riunioni di teams e fornisce l'endpoint per l'ingestione media.

[<span class="underline">È disponibile un'applicazione di registrazione di conformità di esempio</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) che Mostra come configurare il bot, creare l'istanza dell'app e assegnare i criteri di conformità. L'esempio contiene anche esempi sull'uso delle API per la registrazione di interazioni specifiche, ad esempio la gestione del routing delle [<span class="underline">chiamate in arrivo</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   , la [<span class="underline">modifica degli Stati di registrazione</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)e [<span class="underline">la rimozione dell'utente che viene registrato</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
La documentazione del grafico sulle API specifiche può essere trovata qui per [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) e [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).

L'implementazione esatta del servizio registratore varia in base al partner, ma deve essere progettata per supportare più Recorder per ottenere elevata disponibilità e distribuzione geografica della distribuzione per ridurre la latenza dei team al registratore. Si prevede inoltre che i registratori siano progettati con flessibilità e ridondanza.

I partner devono confermare la versione minima richiesta di Microsoft Graph Communications API e SDK con Microsoft prima di inviare la soluzione per la certificazione per assicurarsi che siano supportati tutti i requisiti di integrazione della registrazione di conformità.

Due requisiti specifici fondamentali per lo scenario di registrazione della conformità sono i seguenti:

- Recorder bot deve essere distribuito in Azure

- Recorder bot deve essere eseguito in una VM di Windows in Azure

I requisiti di Azure e Windows VM si applicano solo al componente teams bot, il che significa che un partner può implementare il resto della piattaforma di propria scelta purché soddisfi i requisiti di prestazioni e funzionalità necessari per la registrazione della conformità.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Assegnazione e provisioning dei criteri di registrazione conformità

Gli amministratori IT possono determinare gli utenti da registrare e il registratore che verrà usato per ogni utente, creando e assegnando criteri di registrazione della conformità. I registratori vengono automaticamente invitati a partecipare alle conversazioni in base alla configurazione di questi criteri quando si verifica un'interazione di comunicazione. I criteri di registrazione della conformità vengono gestiti con [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) e possono essere applicati a livello di tenant, per utente e gruppo di sicurezza per ogni organizzazione. Per altre informazioni, vedere documenti Microsoft per [<span class="underline">criteri di riunione</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), criteri di [<span class="underline">chiamata</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) e [<span class="underline">criteri di gruppo</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).

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

2. Creare un criterio di registrazione conformità.

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

3. Assegnare i criteri di registrazione conformità a un utente.

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

Il supporto per le notifiche viene abilitato tramite le esperienze del client teams. Le esperienze possono essere visive o audio.

**Client teams-avviso visivo**
- Desktop/Web
- Dispositivi mobili (iOS/Android)
- Telefoni di Teams
- Sale Teams

**Altri endpoint-avviso audio**
- Telefoni SIP
- Skype for Business
- Audioconferenza
- Chiamanti PSTN

## <a name="compliance-recording-for-teams-certification-programs"></a>Registrazione della conformità per i programmi di certificazione Teams

Oltre a pubblicare le API pubblicamente disponibili per consentire ai partner di sviluppare e integrare soluzioni CCaaS con teams, abbiamo sviluppato la registrazione di conformità per il programma di certificazione Microsoft teams per garantire ai clienti la garanzia che la soluzione di ogni partner sia stata testata e verificata per garantire la qualità, la compatibilità e l'affidabilità che si aspettano da soluzioni Microsoft.  

I partner seguenti sono in procinto di certificare la loro soluzione per Microsoft teams.  

|Partner|Sito Web della soluzione |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|PIACEVOLE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Casella rossa |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verit |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Questo elenco verrà aggiornato man mano che altri partner partecipano e soddisfano i criteri di certificazione.

## <a name="next-steps"></a>Passaggi successivi

Se si è un fornitore che cerca di partecipare al programma di certificazione, inviare la posta <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.
