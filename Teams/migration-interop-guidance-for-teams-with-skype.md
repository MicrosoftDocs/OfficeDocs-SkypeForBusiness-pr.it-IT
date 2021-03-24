---
title: Migrazione e interoperabilità - Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Comprendere i concetti fondamentali per gestire la transizione dell'organizzazione a Teams da Skype for Business.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3a446213a5c10126b9ae42986fe2fa1986bc9e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098332"
---
# <a name="coexistence-modes---reference"></a>Modalità di coesistenza - Riferimento

Le modalità di coesistenza offrono un'esperienza semplice e prevedibile per gli utenti finali quando le organizzazioni passano da Skype for Business a Teams. Per un'organizzazione che si sposta in Teams, la modalità TeamsOnly è la destinazione finale per ogni utente, anche se non è necessario assegnare a tutti gli utenti TeamsOnly (o qualsiasi modalità) contemporaneamente. Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare qualsiasi modalità di Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) per garantire comunicazioni prevedibili tra gli utenti di TeamsOnly e quelli che non lo sono ancora.

Dal punto di vista tecnico, la modalità di un utente regola diversi aspetti dell'esperienza dell'utente:

- *Routing in arrivo:* in quale client (Teams o Skype for Business) vengono effettuate chat e chiamate in arrivo? 
- *Pubblicazione della* presenza: la presenza dell'utente viene visualizzata ad altri utenti in base all'attività in Teams o Skype for Business? 
- *Pianificazione delle riunioni:* quale servizio viene usato per pianificare nuove riunioni e verificare che il componente aggiuntivo appropriato sia presente in Outlook? TeamsUpgradePolicy non regola l'partecipazione alla riunione. Gli utenti possono *sempre partecipare* a qualsiasi riunione, che si tratta di una riunione Skype for Business o di teams.
- *Esperienza client:* Quali funzionalità sono disponibili in Teams e/o nel client Skype for Business? Gli utenti possono avviare chiamate e chat in Teams, Skype for Business o entrambi? È disponibile l'esperienza & canali di Teams?  

Per altre informazioni sul routing e sul comportamento di presenza in base alla modalità, vedere [Coesistenza con Skype for Business.](./coexistence-chat-calls-presence.md)

Tuttavia, dal punto di vista dell'esperienza, la modalità può essere descritta come definizione dell'esperienza per:
- *Chat e chiamate:* quale client usa un utente?
- *Pianificazione delle riunioni:* gli utenti pianificano nuove riunioni come riunioni di Teams o Skype for Business?
- *Disponibilità delle funzionalità di collaborazione nel client Teams*. Teams & canali e file è disponibile mentre gli utenti hanno ancora Skype for Business?

Le modalità sono elencate di seguito.
</br>
</br>

|Modalità|Chiamate e chat|Pianificazione riunione<sup>1</sup>|Canali & Teams|Use Case|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Richiede la casa in Skype for Business online*|Teams|Teams|Sì|Stato finale dell'aggiornamento. Anche l'impostazione predefinita per i nuovi tenant.|
|Isole|In entrambi i|In entrambi i|Sì|Configurazione predefinita. Consente a un singolo utente di valutare entrambi i client affiancati. Le chat e le chiamate possono essere effettuate in entrambi i client, quindi gli utenti devono sempre eseguire entrambi i client. Per evitare un'esperienza skype for Business confusa o regredita, le comunicazioni esterne (federate), i servizi vocali PSTN e le applicazioni vocali, l'integrazione di Office e molte altre integrazioni continuano a essere gestite da Skype for Business.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|Sì|"Riunioni per prime". Principalmente per le organizzazioni locali che possono trarre vantaggio dalla funzionalità delle riunioni di Teams, se non sono ancora pronte per spostare le chiamate nel cloud.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Sì|Punto di partenza alternativo per organizzazioni complesse che necessitano di un controllo amministrativo più stretto.|
|SfBOnly|Skype for Business|Skype for Business|No<sup>3</sup>|Scenario specializzato per le organizzazioni con requisiti rigorosi per il controllo dei dati. Teams viene usato solo per partecipare a riunioni pianificate da altri.|
||||||

</br>
</br>

**Note:**

<sup>1</sup> La possibilità di partecipare a una riunione esistente (pianificata in Teams o in Skype for Business) non è disciplinata dalla modalità. Per impostazione predefinita, gli utenti possono sempre partecipare a qualsiasi riunione a cui sono stati invitati.

<sup>2</sup> Per impostazione predefinita, quando si assegna TeamsOnly o SfbWithTeamsCollabAndMeetings a un singolo utente, tutte le riunioni Skype for Business pianificate da tale utente per il futuro vengono convertite in riunioni di Teams. Se si desidera, è possibile lasciare queste riunioni come riunioni Skype for Business specificando quando si concede TeamsUpgradePolicy o deselezionando la casella di controllo nel portale di amministrazione  `-MigrateMeetingsToTeams $false` di Teams. La possibilità di convertire le riunioni da Skype for Business a Teams non è disponibile quando si concede TeamsUpgradePolicy a livello di tenant. 

<sup>3</sup> Attualmente Teams non è in grado di disabilitare la funzionalità Teams e Canali, quindi questa funzionalità rimane abilitata per il momento.


## <a name="using-teamsupgradepolicy"></a>Uso di TeamsUpgradePolicy

TeamsUpgradePolicy espone due proprietà chiave: Mode e NotifySfbUsers. 
</br>
</br>

|Parametro|Tipo|Valori consentiti</br>(impostazione predefinita in corsivo)|Descrizione|
|---|---|---|---|
|Modalità|Enum|*Isole*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica la modalità in cui deve essere eseguito il client.|
|NotifySfbUsers|Bool|*False* o true|Indica se mostrare un banner nel client Skype for Business che informa l'utente che Teams sostituirà presto Skype for Business. Questo non può essere vero se Mode=TeamsOnly.|
|||||

Teams fornisce tutte le istanze pertinenti di TeamsUpgradePolicy tramite criteri predefiniti di sola lettura. Di conseguenza, sono disponibili solo i cmdlet Get e Grant. Le istanze predefinite sono elencate di seguito.
</br>
</br>

|Identity|Modalità|NotifySfbUsers|
|---|---|---|
|Isole|Isole|Falso|
|IslandsWithNotify|Isole|Vero|
|SfBOnly|SfBOnly|Falso|
|SfBOnlyWithNotify|SfBOnly|Vero|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Falso|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|Vero|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|Falso|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|Vero|
|UpgradeToTeams|TeamsOnly|Falso|
|Globale</br>*Impostazione predefinita*|Isole|Falso|
||||

Queste istanze dei criteri possono essere concesse a singoli utenti o a livello di tenant. Ad esempio:
- Per aggiornare un utente ($SipAddress) a Teams, concedere l'istanza "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Per aggiornare l'intero tenant, omettere il parametro identity dal comando grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Esperienza utente del client Teams quando si usano le modalità Skype for Business

Quando un utente è in una delle modalità Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), tutte le chat e le chiamate in arrivo vengono instradati al client Skype for Business dell'utente. Per evitare confusione tra gli utenti finali e garantire la corretta funzionalità di routing, chiamate e chat nel client Teams viene disabilitata automaticamente quando un utente è in una delle modalità Skype for Business. Analogamente, la pianificazione delle riunioni in Teams viene disabilitata automaticamente quando gli utenti sono in modalità SfBOnly o SfBWithTeamsCollab e abilitata automaticamente quando un utente è in modalità SfBWithTeamsCollabAndMeetings. Per informazioni dettagliate, vedere [Esperienza client di Teams e conformità alle modalità di coesistenza.](./teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!Note] 
> - Prima dell'applicazione automatica di Teams e Canali, le modalità SfbOnly e SfBWithTeamsCollab si comportano allo stesso modo.


## <a name="detailed-mode-descriptions"></a>Descrizioni dettagliate della modalità
</br>
</br>

|Modalità|Spiegazione|
|---|---|
|**Isole**</br>(impostazione predefinita)|Un utente esegue sia Skype for Business che Teams affiancati. Questo utente:</br><ul><li>Può avviare chat e chiamate VoIP nel client Skype for Business o Teams. Nota: gli utenti con Skype for Business ospitati in locale non possono avviare da Teams per raggiungere un altro utente Skype for Business, indipendentemente dalla modalità del destinatario.<li>Riceve chat & chiamate VoIP avviate in Skype for Business da un altro utente nel client Skype for Business.<li>Riceve le chat & chiamate VoIP avviate in Teams da un altro utente nel client Teams se sono nello *stesso tenant.*<li>Riceve chat & chiamate VoIP avviate in Teams da un altro utente nel client Skype for Business se si tratta di un *tenant federato.* <li>Ha la funzionalità PSTN come indicato di seguito:<ul><li>Quando l'utente è ospitata in Skype for Business locale e ha VoIP aziendale, le chiamate PSTN vengono sempre avviate e ricevute in Skype for Business.<li>Quando l'utente è disponibile su Skype for Business online e ha sistema telefonico Microsoft, l'utente avvia e riceve sempre chiamate PSTN in Skype for Business:<ul><li>Questo accade se l'utente ha un piano per le chiamate Microsoft o si connette alla rete PSTN tramite Skype for Business Cloud Connector Edition o una distribuzione locale di Skype for Business Server (voce ibrida).<li>**Nota: l'instradamento diretto del sistema telefonico non è supportato in modalità Isole.**</ul></ul><li>Riceve le chiamate Microsoft Call Queues e Auto-Attendant in Skype for Business:<ul><li>I numeri di telefono assegnati alle  code di chiamata e agli operatori automatici non possono essere numeri di instradamento diretto del sistema telefonico in modalità Isole.</ul></ul><li>Può pianificare riunioni in Teams o Skype for Business (e per impostazione predefinita visualizza entrambi i plug-in).<li>Può partecipare a qualsiasi riunione Skype for Business o Teams; la riunione si aprirà nel rispettivo cliente.</ul>|
|**SfBOnly**|Un utente esegue solo Skype for Business. Questo utente:</br><ul><li>Può avviare chat e chiamate solo da Skype for Business.<li>Riceve qualsiasi chat/chiamata nel client Skype for Business, indipendentemente da dove è stato avviato, a meno che l'iniziatore non sia un utente di Teams con Skype for Business ospitata in locale. *<li> Può pianificare solo riunioni Skype for Business, ma può </br> \* partecipare a riunioni Skype for Business o Teams.* L'uso della modalità Isole con gli utenti locali non è consigliato in combinazione con altri utenti in modalità SfBOnly. Se un utente di Teams con Skype for Business ospitata in locale avvia una chiamata o una chat con un utente SfBOnly, l'utente SfBOnly non è raggiungibile e riceve una chat o una chiamata e-mail persa.*|
|**SfBWithTeamsCollab**|Un utente esegue sia Skype for Business che Teams affiancati. Questo utente:</br><ul><li>Ha la funzionalità di un utente in modalità SfBOnly.<li>Teams è abilitato solo per la collaborazione di gruppo (canali); la pianificazione di chat/chiamate/riunioni è disabilitata.</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|Un utente esegue sia Skype for Business che Teams affiancati. Questo utente:<ul><li>Ha la funzionalità di chat e chiamate dell'utente in modalità SfBOnly.<li>Ha Teams abilitato per la collaborazione di gruppo (canali - include conversazioni di canale); chat e chiamate sono disabilitate.<li>Può pianificare solo riunioni di Teams, ma può partecipare a riunioni Skype for Business o Teams.</ul>|
|**TeamsOnly**</br>(richiede SfB Online home)|Un utente esegue solo Teams. Questo utente:<ul><li>Riceve eventuali chat e chiamate nel client di Teams, indipendentemente da dove sono stati avviati.<li>Può avviare chat e chiamate solo da Teams.<li>Può pianificare le riunioni solo in Teams, ma può partecipare a riunioni Skype for Business o Teams.<li>Può continuare a usare i telefoni IP Skype for Business.<br><br>*L'uso della modalità TeamsOnly in combinazione con altri utenti in modalità Isole non è consigliato finché l'adozione di Teams non è satura; in altre parti, tutti gli utenti della modalità Isole usano e monitorano attivamente i client Teams e Skype for Business. Se un utente TeamsOnly avvia una chiamata o una chat con un utente delle Isole, la chiamata o la chat verrà avviata nel client Teams dell'utente delle Isole; se l'utente isole non usa o monitora Teams, l'utente apparirà offline e non sarà raggiungibile dall'utente TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Argomenti correlati

[Coesistenza con Skype for Business](./coexistence-chat-calls-presence.md)

[Esperienza del client di Teams e conformità alle modalità di coesistenza](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)