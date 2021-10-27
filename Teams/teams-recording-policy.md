---
title: Introduzione alla registrazione Teams basata su criteri per le chiamate & riunioni
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
description: Informazioni su Teams registrazione basata su criteri per le chiamate & riunioni
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
ms.openlocfilehash: 92b80bd9a96cd95b34bd7646902cfdbff1d83447
ms.sourcegitcommit: c7a6079c9592c28d8b082ff92004ae4706cea76e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2021
ms.locfileid: "60600250"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introduzione alla registrazione Teams basata su criteri per le chiamate & riunioni

La registrazione basata su criteri consente alle organizzazioni che adottano il Microsoft Teams per le chiamate e le riunioni di stabilire, usando un criterio amministrativo, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per l'elaborazione e la conservazione successive, come richiesto dai criteri aziendali o normativi pertinenti.

Teams è stato migliorato per supportare l'integrazione di soluzioni di registrazione di terze parti, incluse le funzionalità della piattaforma, le esperienze utente e le interfacce amministrative necessarie per fornire una soluzione end-to-end per la configurazione, la gestione, la registrazione, l'archiviazione e l'analisi delle comunicazioni Teams. I miglioramenti includono API ed eventi della piattaforma di comunicazione per la registrazione, che offre:

- Acquisizione multimediale fluida e di alta qualità su tutti i dispositivi e tutti gli endpoint supportati per audio, video, condivisione dello schermo e chat.

- Supporto per l'acquisizione di interazioni tra Teams utenti ed endpoint di chiamata supportati (Teams, Teams Mobile, Skype for Business, PSTN)

- Nuovi criteri amministrativi per la registrazione della conformità, inclusa l'integrazione con le chiamate amministrative Teams e gli strumenti e i criteri per le riunioni

La registrazione della conformità può essere abilitata per gli utenti Microsoft 365 A3/A5/E3/E5/Business Premium e Office 365 A3/A5/E3/E5. 

Le funzionalità di integrazione della soluzione di registrazione della conformità sono state esaminate anche in Ignite 2019 nella sessione registrazione e Microsoft Teams [conformità.](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Teams di registrazione delle interazioni

I casi di utilizzo della registrazione delle interazioni possono essere suddivisi in quattro categorie principali di funzionalità di registrazione: Convenienza, Funzionalità, Organizzazione e Intercetta legale, come illustrato nell'immagine:

> [!div class="mx-imgBorder"]
> ![Screenshot che mostra l'interazione che registra cosa e perché.](media/recording-taxonomy.png "L'immagine mostra le categorie di registrazione.")

Ognuna di queste categorie richiede requisiti diversi per l'avvio delle registrazioni, gli elementi registrati, la posizione in cui vengono archiviate le registrazioni, chi viene avvisato, chi controlla l'accesso e come viene gestita la conservazione.

| Tipo                   | Convenienza (Registrazione Teams) | Organizzazione - Regolamentata (Registrazione conformità) |
| ---------------------- | ------------------ | --------------- |
| Iniziatore              | Utente               | Amministratore (sistema)  |
| Target                 | Per chiamata/riunione | Per utente        |
| Archiviazione proprietario          | Utente               | Conformità      |
| È necessaria una notifica? | Sì                | Sì             |
| Proprietario dell'accesso           | Utente               | Conformità      |
| Criteri di conservazione?      | Facoltativo           | Sì             |

Teams offre varie funzionalità per la [registrazione pratica](./cloud-recording.md) e funzionale di riunioni ed eventi live. Registrazione dell'organizzazione significa consentire alle organizzazioni che adottano il Teams per le chiamate e le riunioni di stabilire, tramite criteri amministrativi, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per l'elaborazione e la conservazione successive, come richiesto dai criteri aziendali o normativi pertinenti. Gli utenti ai sensi di questo criterio saranno consapevoli che le interazioni digitali con Teams vengono registrate, ma non saranno in grado di disabilitare la registrazione e non avranno accesso alla registrazione una volta completata l'interazione. La registrazione diventa parte dell'archivio aziendale disponibile per il personale legale e di conformità per eDiscovery, il blocco legale e altri usi di conservazione aziendale.

## <a name="example-user-needs"></a>Esigenze degli utenti di esempio

<table>
<thead>
<tr class="header">
<th>Persona</th>
<th>Esigenze</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utenti registrati</td>
<td><ul>
<li><p>Ricevere una notifica quando è in corso la registrazione.</p></li>
<li><p>Essere informati quando l'errore del criterio e/o del registratore causa modifiche al comportamento delle chiamate.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Amministratore delle comunicazioni</td>
<td><ul>
<li><p>Comprendere perché e come applicare/applicare criteri di registrazione Teams utenti/endpoint.</p></li>
<li><p>Configurare e gestire i Teams di registrazione per l'organizzazione.</p></li>
<li><p>Monitorare e risolvere i problemi relativi alla registrazione con Teams chiamate e riunioni.</p></li>
<li><p>Supportare il responsabile della conformità interna con analisi operative sull'utilizzo, la qualità e l'affidabilità.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsabile della conformità</td>
<td><ul>
<li><p>Raccogliere tutte Teams comunicazioni nel modo richiesto per rispettare gli obblighi di conformità nei confini regionali appropriati.</p></li>
<li><p>Cercare le interazioni in base ai metadati correlati alla comunicazione o al contenuto dell'interazione. Di seguito sono riportati alcuni esempi comuni:</p>
<ul>
<li><p><strong>Metadati</strong> - Partecipanti, orario, direzione, numero composto, numero di origine, dati aziendali personalizzati</p></li>
<li><p><strong>Contenuto:</strong> trascrizione, valutazione, fonetica, interazioni correlate</p></li>
</ul></li>
<li><p>Analizzare e interagire con le comunicazioni raccolte, inclusa la possibilità di monitorare le interazioni durante la raccolta.</p></li>
<li><p>Garantire la sicurezza delle comunicazioni raccolte ed evitare manomissioni in tutte le fasi.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Panoramica dell'architettura della soluzione

Le soluzioni di registrazione della conformità sono integrate con Teams, come illustrato nel diagramma seguente:

> [!div class="mx-imgBorder"]
> ![Screenshot che mostra l'impostazione dell'app personalizzata del team.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Le immagini mostrano il flusso quando una Teams riunione o una chiamata viene inviata e ricevuta.")

> [!NOTE]
> Questa soluzione è progettata specificamente per abilitare la registrazione della conformità basata su criteri con Teams. Qualsiasi altro utilizzo di questa soluzione non sarà supportato.


## <a name="recorder"></a>Registratore

Il componente principale della soluzione di registrazione della conformità è il registratore.
I registratori sono creati come servizi scalabili basati su Azure (bot) che usano la piattaforma di comunicazione [Microsoft](/graph/cloud-communications-concept-overview) e si registrano come applicazioni con Microsoft Graph. Il registratore fornisce l'interazione diretta con [](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) le API della piattaforma di comunicazione Teams chiamate e riunioni e fornisce l'endpoint per l'inserimento di elementi multimediali.

È [disponibile un'applicazione di registrazione conformità](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) di esempio che mostra come configurare il bot, creare l'istanza dell'app e assegnare i criteri di conformità. L'esempio include anche esempi sull'utilizzo dell'API per la registrazione di interazioni [specifiche,](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)ad esempio la gestione del [routing](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) delle chiamate in arrivo, la modifica degli stati di registrazione e la rimozione dell'utente che [viene registrato.](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)
Graph documentazione sulle API specifiche è disponibile qui per [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) e [incomingContext.](/graph/api/resources/incomingcontext?view=graph-rest-1.0)

L'implementazione esatta del servizio di registrazione varia in base al partner, ma deve essere progettata per supportare più registratori per ottenere un'elevata disponibilità e distribuzione geografica della distribuzione per ridurre la latenza Teams al registratore. Inoltre, è previsto che i registratori stessi siano progettati in base alla resilienza e alla ridondanza.

I partner devono confermare la versione minima richiesta delle API di comunicazione di Microsoft Graph e degli SDK con Microsoft prima di inviare la soluzione per la certificazione per assicurarsi che tutti i requisiti di integrazione della registrazione della conformità siano supportati.

Due requisiti specifici fondamentali per lo scenario di registrazione della conformità sono:

- Il bot registratore deve essere distribuito in Azure

- Il bot del registratore deve essere eseguito in una Windows vm in Azure

I requisiti di Azure e della macchina virtuale di Windows si applicano solo al componente bot di Teams, il che significa che un partner può implementare il resto della piattaforma scelta, a condizione che soddisfi i requisiti di prestazioni e funzionalità pertinenti per la registrazione della conformità.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Assegnazione e provisioning dei criteri di registrazione della conformità

Gli amministratori IT possono determinare quali utenti devono essere registrati e quale registratore verrà usato per ogni utente, creando e assegnando criteri di registrazione di conformità. I registratori vengono invitati automaticamente a partecipare alle conversazioni in base alla configurazione di questi criteri quando si verifica un'interazione di comunicazione. I criteri di registrazione della conformità vengono gestiti [con Microsoft PowerShell](./teams-powershell-overview.md) e possono essere applicati a livello di tenant, per utente e di gruppo di sicurezza per ogni organizzazione. Per altre informazioni, vedere Microsoft Docs for [Meeting policies,](./meeting-policies-in-teams.md) [calling policies](./teams-calling-policy.md) e [group policies.](./assign-policies.md#assign-a-policy-to-a-group)

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

2. Creare criteri di registrazione conformità.

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

   Vedere [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps).

3. Assegnare i criteri registrazione conformità a un utente.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   Vedere [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Esperienze utente

Il supporto per le notifiche è abilitato usando le Teams client. Le esperienze possono essere visive o audio.

**Teams clienti - avviso visivo**
- Desktop/Web
- Mobile (iOS/Android)
- Teams telefoni
- Teams locali

**Altri endpoint - avviso audio**
- Telefoni SIP
- Skype for Business
- Audioconferenza
- Chiamanti PSTN

> [!NOTE]
> Registrazione conformità non è supportata con le code di chiamata in modalità conferenza. Usare le code di chiamata in modalità di trasferimento.

## <a name="compliance-recording-for-teams-certification-programs"></a>Registrazione della conformità per i Teams di certificazione

Oltre a pubblicare API disponibili pubblicamente che consentono ai partner di sviluppare e integrare soluzioni CCaaS con Teams, abbiamo sviluppato la registrazione della conformità per il programma di certificazione Microsoft Teams per fornire ai clienti la certezza che la soluzione di ogni partner partecipante sia stata testata e verificata per fornire la qualità, la compatibilità e l'affidabilità che si aspettano dalle soluzioni Microsoft.  

I partner seguenti hanno certificato la propria soluzione per Microsoft Teams.<br/><br/>

|Partner|Sito Web della soluzione |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Tecnologia di approfondimento |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|NIZZA |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Casella rossa |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Lago Theta |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<br/>
I partner seguenti stanno certificando la soluzione per Microsoft Teams.<br/><br/>

|Partner|Sito Web della soluzione |
|:--|:--|
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Innovazione quercia |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |

Questo elenco verrà aggiornato man appena altri partner si uniranno e soddisfino i criteri di certificazione.

## <a name="next-steps"></a>Passaggi successivi

Se si è un fornitore che cerca di partecipare al programma di certificazione, inviare posta [a Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com).
