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
ms.openlocfilehash: 7b03a31865504507db1c1b0da0fb9c30eb3e1444
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955923"
---
# <a name="coexistence-modes---reference"></a>Modalità di coesistenza - Riferimento

Le modalità di coesistenza offrono agli utenti finali un'esperienza semplice e prevedibile durante il passaggio da Skype for Business a Teams per le organizzazioni. Per un'organizzazione che sta passando a Teams, la modalità TeamsOnly è la destinazione finale per ogni utente, anche se non è necessario assegnare TeamsOnly a tutti gli utenti (o qualsiasi modalità) contemporaneamente. Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare qualsiasi modalità di Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) per garantire una comunicazione prevedibile tra gli utenti che sono TeamsOnly e quelli che non lo sono ancora.

Dal punto di vista tecnico, la modalità di un utente regola diversi aspetti dell'esperienza utente:

- *Instradamento* in arrivo: in quale client (Teams o Skype for Business) vengono effettuate le chat e le chiamate in arrivo? 
- *Pubblicazione della* presenza: la presenza dell'utente viene mostrata agli altri utenti in base alla sua attività in Teams o Skype for Business? 
- *Pianificazione delle* riunioni: quale servizio viene usato per pianificare nuove riunioni e verificare che il componente aggiuntivo corretto sia presente in Outlook? TeamsUpgradePolicy non regola la partecipazione alla riunione. Gli utenti possono *sempre partecipare* a qualsiasi riunione, che si tratta di una riunione Skype for Business o di una riunione di Teams.
- *Esperienza client:* Quali funzionalità sono disponibili nel client Teams e/o Skype for Business? Gli utenti possono avviare chiamate e chat in Teams, Skype for Business o entrambi? Teams e & sono disponibili?  

Per ulteriori informazioni sul routing e sul comportamento di presenza in base alla modalità, consulta [Coesistenza con Skype for Business.](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence)

Tuttavia, dal punto di vista dell'esperienza, la modalità può essere descritta come definizione dell'esperienza per:
- *Chat e chiamate:* quale client usa un utente?
- *Pianificazione delle riunioni:* gli utenti pianificano nuove riunioni come riunioni di Teams o Skype for Business?
- *Disponibilità delle funzionalità di collaborazione nel client Teams.* La funzionalità & canali e file di Teams è disponibile mentre gli utenti hanno ancora Skype for Business?

Le modalità sono elencate di seguito.
</br>
</br>

|Modalità|Chiamate e chat|Pianificazione riunioni<sup>1</sup>|Canali & Teams|Use Case|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Richiede casa in Skype for Business online*|Teams|Teams|Sì|Stato finale dell'aggiornamento. Anche l'impostazione predefinita per i nuovi tenant.|
|Isole|In entrambi i|In entrambi i|Sì|Configurazione predefinita. Consente a un singolo utente di valutare entrambi i client affiancati. Le chat e le chiamate possono essere effettuate in entrambi i client, quindi gli utenti devono sempre eseguire entrambi i client. Per evitare un'esperienza Skype for Business confusa o con una regressione, le comunicazioni esterne (federate), i servizi vocali PSTN e le applicazioni vocali, l'integrazione con Office e diverse altre integrazioni, Skype for Business continua a essere gestito.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|Sì|"Prima riunione". Principalmente per le organizzazioni locali che beneficiano della funzionalità di riunione di Teams, se non sono ancora pronte a trasferire le chiamate al cloud.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Sì|Punto di partenza alternativo per le organizzazioni complesse che necessitano di un controllo amministrativo più stretto.|
|SfBOnly|Skype for Business|Skype for Business|No<sup>3</sup>|Scenario specializzato per le organizzazioni con requisiti rigorosi in fatto di controllo dei dati. Teams viene usato solo per partecipare alle riunioni pianificate da altri.|
||||||

</br>
</br>

**Note:**

<sup>1</sup> La possibilità di partecipare a una riunione esistente (pianificata in Teams o in Skype for Business) non è disciplinata dalla modalità. Per impostazione predefinita, gli utenti possono sempre partecipare a qualsiasi riunione a cui sono stati invitati.

<sup>2</sup> Per impostazione predefinita, quando si assegna TeamsOnly o SfbWithTeamsCollabAndMeetings a un singolo utente, le riunioni esistenti pianificate da quell'utente per il futuro vengono convertite in riunioni di Teams. Se si desidera, è possibile lasciare queste riunioni come riunioni Skype for Business specificando quando si concede TeamsUpgradePolicy o deselezionando la casella di controllo nel portale di amministrazione  `-MigrateMeetingsToTeams $false` di Teams. La possibilità di convertire le riunioni da Skype for Business a Teams non è disponibile quando si concede TeamsUpgradePolicy a livello di tenant. 

<sup>3</sup> Attualmente, Teams non è in grado di disabilitare la funzionalità team e canali, quindi questa funzionalità rimane abilitata per il momento.


## <a name="using-teamsupgradepolicy"></a>Uso di TeamsUpgradePolicy

TeamsUpgradePolicy espone due proprietà chiave: Mode e NotifySfbUsers. 
</br>
</br>

|Parametro|Tipo|Valori consentiti</br>(impostazione predefinita in corsivo)|Descrizione|
|---|---|---|---|
|Modalità|Enum|*Isole*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica la modalità in cui deve essere eseguito il client.|
|NotifySfbUsers|Bool|*False* o true|Indica se mostrare un banner nel client Skype for Business che informa l'utente che Teams sostituirà presto Skype for Business. Questo non può essere vero se Mode=TeamsOnly.|
|||||

Teams fornisce tutte le istanze rilevanti di TeamsUpgradePolicy tramite criteri di sola lettura incorporati. Di conseguenza, sono disponibili solo i cmdlet Get e Grant. Le istanze predefinite sono elencate di seguito.
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

Quando un utente è in una delle modalità di Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), tutte le chat e le chiamate in arrivo vengono indirizzate al client Skype for Business dell'utente. Per evitare confusione con l'utente finale e garantire una corretta funzionalità di routing, chiamata e chat nel client Teams viene automaticamente disabilitata quando un utente è in una delle modalità di Skype for Business. Analogamente, la pianificazione delle riunioni in Teams viene automaticamente disabilitata quando gli utenti sono in modalità SfBOnly o SfBWithTeamsCollab e automaticamente abilitata quando un utente è in modalità SfBWithTeamsCollabAndMeetings. Per informazioni dettagliate, vedere [l'esperienza client di Teams e la conformità alle modalità di coesistenza.](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

> [!Note] 
> - Prima dell'applicazione automatica di Teams e canali, le modalità SfbOnly e SfBWithTeamsCollab funzionano allo stesso modo.


## <a name="detailed-mode-descriptions"></a>Descrizioni dettagliate della modalità
</br>
</br>

|Modalità|Spiegazione|
|---|---|
|**Isole**</br>(impostazione predefinita)|Un utente gestisce sia Skype for Business che Teams affiancati. Questo utente:</br><ul><li>Può avviare chat e chiamate VoIP sia nel client Skype for Business che in Teams. Nota: gli utenti con Skype for Business ospitati in locale non possono iniziare da Teams per raggiungere un altro utente Skype for Business, indipendentemente dalla modalità del destinatario.<li>Riceve chat e & Chiamate VoIP avviate in Skype for Business da un altro utente nel client Skype for Business.<li>Riceve chat e & chiamate VoIP avviate in Teams da un altro utente nel client Teams se sono nello *stesso tenant.*<li>Riceve chat e & chiamate VoIP avviate in Teams da un altro utente nel client Skype for Business se fanno parte di *un tenant federato.* <li>Include funzionalità PSTN come indicato di seguito:<ul><li>Quando l'utente è ospitata in Skype for Business locale e dispone di VoIP aziendale, le chiamate PSTN vengono sempre avviate e ricevute in Skype for Business.<li>Quando l'utente è su Skype for Business online e dispone del Sistema telefonico Microsoft, avvia e riceve sempre chiamate PSTN in Skype for Business:<ul><li>Ciò avviene indipendentemente dal fatto che l'utente abbia un piano per le chiamate Microsoft o si connetta alla rete PSTN attraverso Skype for Business Cloud Connector Edition o una distribuzione locale di Skype for Business Server (voce ibrida).<li>**Nota: l'instradamento diretto del sistema telefonico non è supportato nella modalità Isole.**</ul></ul><li>Riceve le code di chiamata Microsoft e le chiamate operatore automatico in Skype for Business:<ul><li>I numeri di telefono assegnati a  code di chiamata e operatori automatici non possono essere numeri di instradamento diretto del sistema telefonico in modalità Isole.</ul></ul><li>È possibile pianificare riunioni in Teams o Skype for Business (e visualizzare entrambi i plug-in per impostazione predefinita).<li>Può partecipare a qualsiasi riunione Skype for Business o Teams; La riunione si aprirà nel rispettivo client.</ul>|
|**SfBOnly**|Un utente esegue solo Skype for Business. Questo utente:</br><ul><li>Può avviare chat e chiamate solo da Skype for Business.<li>Riceve chat/chiamate nel client Skype for Business, indipendentemente da dove è stato avviato, a meno che l'iniziatore non sia un utente di Teams con Skype for Business ospitata in locale. *<li> Può pianificare solo riunioni Skype for Business, ma può </br> \* partecipare a riunioni Skype for Business o Teams.* Non è consigliabile usare la modalità Isole con gli utenti locali in combinazione con altri utenti in modalità SfBOnly. Se un utente di Teams con Skype for Business ospitata in locale avvia una chiamata o una chat a un utente SfBOnly, l'utente SfBOnly non è raggiungibile e riceve una chat o un messaggio di posta elettronica di chiamata perso.*|
|**SfBWithTeamsCollab**|Un utente gestisce sia Skype for Business che Teams affiancati. Questo utente:</br><ul><li>Ha la funzionalità di un utente in modalità SfBOnly.<li>Teams è abilitato solo per la collaborazione di gruppo (canali); la pianificazione delle chat, delle chiamate o delle riunioni viene disabilitata.</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|Un utente gestisce sia Skype for Business che Teams affiancati. Questo utente:<ul><li>Include la funzionalità di chat e chiamate dell'utente in modalità SfBOnly.<li>Ha abilitato Teams per la collaborazione di gruppo (canali - include le conversazioni di canale); chat e chiamate sono disabilitate.<li>Può pianificare solo le riunioni di Teams, ma può partecipare alle riunioni di Skype for Business o Teams.</ul>|
|**TeamsOnly**</br>(richiede l'home page di SfB Online)|Un utente esegue solo Teams. Questo utente:<ul><li>Riceve chat e chiamate nel client Teams, indipendentemente da dove è stato avviato.<li>Può avviare chat e chiamate solo da Teams.<li>Può pianificare riunioni solo in Teams, ma può partecipare alle riunioni di Skype for Business o Teams.<li>Può continuare a usare i telefoni IP di Skype for Business.<br><br>*Non è consigliabile usare la modalità TeamsOnly in combinazione con altri utenti in modalità Isole finché l'adozione di Teams non è saturi; che significa che tutti gli utenti della modalità Isole usano e monitorano attivamente sia i client Teams che Skype for Business. Se un utente TeamsOnly avvia una chiamata o una chat per un utente delle Isole, tale chiamata o chat verrà avviata nel client Teams dell'utente delle Isole; se l'utente delle Isole non usa o monitora Teams, tale utente apparirà offline e non sarà raggiungibile dall'utente TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Argomenti correlati

[Coesistenza con Skype for Business](https://docs.microsoft.com/microsoftteams/coexistence-chat-calls-presence)

[Esperienza del client di Teams e conformità alle modalità di coesistenza](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Uso del servizio MMS (Meeting Migration Service)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
