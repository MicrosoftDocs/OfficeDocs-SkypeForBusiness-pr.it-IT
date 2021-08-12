---
title: Migrazione e interoperabilità - Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Comprendere i concetti fondamentali per la gestione della transizione dell'organizzazione a Teams da Skype for Business.
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
ms.openlocfilehash: 909c7ca03a2c998e785763b4e1beb09f1f5d0993a286b94d34e2e4d38f6e9b68
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350668"
---
# <a name="coexistence-modes---reference"></a>Modalità di coesistenza - Riferimento

Le modalità di coesistenza offrono agli utenti finali un'esperienza semplice e prevedibile quando le organizzazioni passano da Skype for Business a Teams. Per un'organizzazione che si sposta in Teams, la modalità TeamsOnly è la destinazione finale per ogni utente, anche se non tutti gli utenti devono essere assegnati a TeamsOnly (o a qualsiasi modalità) contemporaneamente. Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare una delle modalità Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) per garantire una comunicazione prevedibile tra gli utenti di TeamsOnly e quelli che non lo sono ancora.

Dal punto di vista tecnico, la modalità di un utente regola diversi aspetti dell'esperienza dell'utente:

- *Routing in arrivo:* in quale client (Teams o Skype for Business) vengono effettuate le chat e le chiamate in arrivo? 
- *Pubblicazione della* presenza: la presenza dell'utente viene visualizzata ad altri utenti in base all'attività Teams o Skype for Business? 
- *Pianificazione delle riunioni:* quale servizio viene usato per pianificare nuove riunioni e verificare che il componente aggiuntivo appropriato sia presente in Outlook? TeamsUpgradePolicy non regola l'partecipazione alla riunione. Gli utenti possono *sempre partecipare* a qualsiasi riunione, sia che si Skype for Business una riunione Teams riunione.
- *Esperienza client:* quali funzionalità sono disponibili in Teams e/o Skype for Business client? Gli utenti possono avviare chiamate e chat in Teams, Skype for Business o entrambe? L'Teams & canali è disponibile?  

Per altre informazioni sul routing e sul comportamento di presenza in base alla modalità, vedere [Coesistenza con](./coexistence-chat-calls-presence.md)Skype for Business .

Tuttavia, dal punto di vista dell'esperienza, la modalità può essere descritta come definizione dell'esperienza per:
- *Chat e chiamate:* quale client usa un utente?
- *Pianificazione riunione:* gli utenti pianificano nuove riunioni Teams o Skype for Business riunioni?
- *Disponibilità delle funzionalità di collaborazione nel Teams client*. La Teams & Canali e file è disponibile mentre gli utenti hanno ancora Skype for Business?

Le modalità sono elencate di seguito.
</br>
</br>

|Modalità|Chiamate e chat|Pianificazione riunione<sup>1</sup>|Teams & canali|Use Case|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Possibile solo se l'utente non ha un account locale in Skype for Business Server*|Teams|Teams|Sì|Stato finale dell'aggiornamento. Anche l'impostazione predefinita per i nuovi tenant.|
|Isole|In entrambi i|In entrambi i|Sì|Configurazione predefinita. Consente a un singolo utente di valutare entrambi i client affiancati. Le chat e le chiamate possono essere effettuate in entrambi i client, quindi gli utenti devono sempre eseguire entrambi i client. Per evitare un'esperienza di Skype for Business confusa o regressa, le comunicazioni esterne (federate), i servizi vocali PSTN e le applicazioni vocali, l'integrazione di Office e molte altre integrazioni continuano a essere gestite da Skype for Business.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|Sì|"Riunioni per prime". Principalmente per le organizzazioni locali che possono trarre vantaggio dalla funzionalità Teams riunione, se non sono ancora pronte per spostare le chiamate nel cloud.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Sì|Punto di partenza alternativo per organizzazioni complesse che necessitano di un controllo amministrativo più stretto.|
|SfBOnly|Skype for Business|Skype for Business|No<sup>3</sup>|Scenario specializzato per le organizzazioni con requisiti rigorosi per il controllo dei dati. Teams viene usato solo per partecipare alle riunioni pianificate da altri.|
||||||

</br>
</br>

**Note:**

<sup>1</sup> La possibilità di partecipare a una riunione esistente (pianificata in Teams o in Skype for Business) non è regolata dalla modalità. Per impostazione predefinita, gli utenti possono sempre partecipare a qualsiasi riunione a cui sono stati invitati.

<sup>2</sup> Per impostazione predefinita, quando si assegna TeamsOnly o SfbWithTeamsCollabAndMeetings a un singolo utente, tutte le riunioni Skype for Business pianificate da tale utente per il futuro vengono convertite Teams riunioni. Se si desidera, è possibile lasciare queste riunioni come riunioni Skype for Business specificando quando si concede TeamsUpgradePolicy o deselezionando la casella di controllo nel portale di amministrazione di `-MigrateMeetingsToTeams $false` Teams. La possibilità di convertire le riunioni da Skype for Business a Teams non è disponibile quando si concede TeamsUpgradePolicy a livello di tenant. 

<sup>3</sup> Attualmente, Teams non è possibile disabilitare la funzionalità Teams e canali, quindi questa funzionalità rimane abilitata per il momento.


## <a name="using-teamsupgradepolicy"></a>Uso di TeamsUpgradePolicy

TeamsUpgradePolicy espone due proprietà chiave: Mode e NotifySfbUsers. 
</br>
</br>

|Parametro|Tipo|Valori consentiti</br>(impostazione predefinita in corsivo)|Descrizione|
|---|---|---|---|
|Modalità|Enum|*Isole*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica la modalità in cui deve essere eseguito il client.|
|NotifySfbUsers|Bool|*False* o true|Indica se visualizzare un banner nel client Skype for Business informare l'utente che Teams presto sostituirà Skype for Business. Questo non può essere vero se Mode=TeamsOnly.|
|||||

Teams tutte le istanze pertinenti di TeamsUpgradePolicy tramite criteri predefiniti di sola lettura. Di conseguenza, sono disponibili solo i cmdlet Get e Grant. Le istanze predefinite sono elencate di seguito.
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

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Esperienza Teams client quando si usano le modalità Skype for Business client

Quando un utente è in una delle modalità Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), tutte le chat e le chiamate in arrivo vengono instradati al client Skype for Business dell'utente. Per evitare confusione tra gli utenti finali e garantire la corretta funzionalità di routing, chiamate e chat nel client di Teams viene disabilitata automaticamente quando un utente è in una delle modalità Skype for Business messaggi. Analogamente, la pianificazione delle riunioni in Teams viene disabilitata automaticamente quando gli utenti sono in modalità SfBOnly o SfBWithTeamsCollab e abilitata automaticamente quando un utente è in modalità SfBWithTeamsCollabAndMeetings. Per informazioni dettagliate, [vedere Teams client e conformità alle modalità di coesistenza.](./teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!Note] 
> - Prima del recapito dell'applicazione automatica di Teams e canali, le modalità SfbOnly e SfBWithTeamsCollab si comportano allo stesso modo.


## <a name="detailed-mode-descriptions"></a>Descrizioni dettagliate della modalità
</br>
</br>

|Modalità|Spiegazione|
|---|---|
|**Isole**</br>(impostazione predefinita)|Un utente esegue sia Skype for Business che Teams affiancati. Questo utente:</br><ul><li>Può avviare chat e chiamate VoIP in Skype for Business o Teams client. Nota: gli utenti con Skype for Business ospitati in locale non possono avviare da Teams per raggiungere un altro utente Skype for Business, indipendentemente dalla modalità del destinatario.<li>Riceve le chat & chiamate VoIP avviate in Skype for Business da un altro utente nel Skype for Business client.<li>Riceve chat & chiamate VoIP avviate in Teams da un altro utente nel client di Teams se sono nello *stesso tenant.*<li>Riceve chat & chiamate VoIP avviate in Teams da un altro utente nel client Skype for Business se si tratta di un *tenant federato.* <li>Ha la funzionalità PSTN come indicato di seguito:<ul><li>Quando l'utente si trova in Skype for Business locale e ha VoIP aziendale, le chiamate PSTN vengono sempre avviate e ricevute in Skype for Business.<li>Quando l'utente è ospitata in Skype for Business Online e ha Telefono Microsoft System, l'utente avvia e riceve sempre chiamate PSTN in Skype for Business:<ul><li>Questo accade se l'utente ha un piano per chiamate Microsoft o si connette alla rete PSTN tramite Skype for Business Cloud Connector Edition o una distribuzione locale di Skype for Business Server (voce ibrida).<li>**Nota: Sistema telefonico routing diretto non è supportato in modalità Isole.**</ul></ul><li>Riceve le chiamate Microsoft Call Queues e Auto-Attendant in Skype for Business:<ul><li>Telefono i numeri assegnati alle code di chiamata  e agli operatori automatici non possono essere Sistema telefonico instradamento diretto in modalità Isole.</ul></ul><li>È possibile pianificare riunioni in Teams o Skype for Business (e per impostazione predefinita verranno visualizzati entrambi i plug-in).<li>Può partecipare a qualsiasi Skype for Business o Teams riunione; la riunione si aprirà nel rispettivo cliente.</ul>|
|**SfBOnly**|Un utente esegue solo Skype for Business. Questo utente:</br><ul><li>Può avviare chat e chiamate Skype for Business solo.<li>Riceve qualsiasi chat/chiamata nel client Skype for Business, indipendentemente da dove è stato avviato, a meno che l'iniziatore non sia un utente di Teams con Skype for Business ospitata in locale. *<li> Può pianificare solo Skype for Business riunioni, ma </br> \* può partecipare* a Skype for Business o Teams riunioni. L'uso della modalità Isole con gli utenti locali non è consigliato in combinazione con altri utenti in modalità SfBOnly. Se un utente di Teams con Skype for Business ospitata in locale avvia una chiamata o una chat con un utente SfBOnly, l'utente SfBOnly non è raggiungibile e riceve una chat o un messaggio di posta elettronica persa.*|
|**SfBWithTeamsCollab**|Un utente esegue sia Skype for Business che Teams affiancati. Questo utente:</br><ul><li>Ha la funzionalità di un utente in modalità SfBOnly.<li>Ha Teams abilitata solo per la collaborazione di gruppo (Canali); la pianificazione di chat/chiamate/riunioni è disabilitata.</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|Un utente esegue sia Skype for Business che Teams affiancati. Questo utente:<ul><li>Ha la funzionalità di chat e chiamate dell'utente in modalità SfBOnly.<li>Ha Teams per la collaborazione di gruppo (canali, incluse le conversazioni dei canali); chat e chiamate sono disabilitate.<li>Può pianificare solo Teams riunioni, ma può partecipare a Skype for Business o Teams riunioni.</ul>|
|**TeamsOnly**</br>(richiede SfB Online home)|Un utente esegue solo Teams. Questo utente:<ul><li>Riceve le chat e le chiamate nel client Teams, indipendentemente da dove è stato avviato.<li>Può avviare chat e chiamate Teams solo.<li>Può pianificare le riunioni solo in Teams, ma può partecipare a Skype for Business o Teams riunioni.<li>Può continuare a usare i Skype for Business IP.<br><br>*L'uso della modalità TeamsOnly in combinazione con altri utenti in modalità Isole non è consigliato finché Teams'adozione non è satura; in altre parti, tutti gli utenti della modalità Isole usano e monitorano attivamente i client Teams e Skype for Business isole. Se un utente TeamsOnly avvia una chiamata o una chat con un utente delle Isole, la chiamata o la chat verrà attivata nel client di Teams isole; se l'utente isole non usa o monitora Teams, l'utente apparirà offline e non sarà raggiungibile dall'utente TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Argomenti correlati

[Coesistenza con Skype for Business](./coexistence-chat-calls-presence.md)

[Esperienza del client di Teams e conformità alle modalità di coesistenza](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
