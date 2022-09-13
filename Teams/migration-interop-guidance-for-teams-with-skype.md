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
ms.localizationpriority: medium
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
ms.openlocfilehash: b6c8e96c1aeb8fabcbe42ba403c51b4a8d6f4836
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657266"
---
# <a name="coexistence-modes---reference"></a>Modalità di coesistenza - Riferimento

> [!Important] 
> - Dopo il ritiro di Skype for Business Online il 31 luglio 2021, non è più possibile assegnare una modalità di coesistenza diversa da TeamsOnly a un utente ospitato nel cloud. Come è stato fatto prima del ritiro, agli utenti ospitati in Skype for Business Server locale può essere assegnata qualsiasi modalità *diversa* da TeamsOnly. 

Le modalità di coesistenza offrono agli utenti finali un'esperienza semplice e prevedibile durante la transizione da Skype for Business a Teams. Per un'organizzazione che passa a Teams, la modalità TeamsOnly è la destinazione finale per ogni utente, anche se non tutti gli utenti devono essere assegnati a TeamsOnly (o a qualsiasi modalità) contemporaneamente. Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare una qualsiasi delle modalità di Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) per garantire comunicazioni prevedibili tra gli utenti che sono TeamsOnly e quelli che non lo sono ancora.

Dal punto di vista tecnico, la modalità di un utente regola diversi aspetti dell'esperienza dell'utente:

- *Routing in ingresso*: in quale client (Teams o Skype for Business) atterrano le chat e le chiamate in arrivo? 
- *Pubblicazione della presenza*: la presenza dell'utente viene mostrata ad altri utenti in base all'attività in Teams o Skype for Business? 
- *Pianificazione delle riunioni*: quale servizio viene usato per pianificare nuove riunioni e garantire che il componente aggiuntivo corretto sia presente in Outlook? TeamsUpgradePolicy non regolamenta l'accesso alle riunioni. Gli utenti possono sempre *partecipare a* qualsiasi riunione, che si tratti di una riunione Skype for Business o di una riunione di Teams.
- *Esperienza client*: quali funzionalità sono disponibili in Teams e/o nel client Skype for Business? Gli utenti possono avviare chiamate e chat in Teams, Skype for Business o entrambi? L'esperienza di Teams & Channels è disponibile?  

Per altre informazioni sul comportamento di routing e presenza in base alla modalità, vedere [Coesistenza con Skype for Business](./coexistence-chat-calls-presence.md).

Tuttavia, dal punto di vista dell'esperienza, la modalità può essere descritta come definizione dell'esperienza per:
- *Chat e chiamate*: quale client usa un utente?
- *Pianificazione delle riunioni*: gli utenti pianificano nuove riunioni come Teams o Skype for Business riunioni?
- *Disponibilità della funzionalità di collaborazione nel client di Teams*. La funzionalità Canali e file di Teams & è disponibile mentre gli utenti hanno ancora Skype for Business?

Le modalità sono elencate di seguito. Gli utenti cloud devono essere TeamsOnly e gli utenti ospitati in locale devono essere una modalità diversa da TeamsOnly. 
</br>
</br>

|Modalità|Chiamate e chat|Pianificazione riunione<sup>1</sup>|Teams & Channels|Use Case|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Possibile solo se l'utente non ha un account locale in Skype for Business Server*|Teams|Teams|Sì|Stato finale dell'aggiornamento. Impostazione predefinita per i nuovi tenant, a meno che non venga rilevata una configurazione ibrida.|
|Isole|Entrambi|Entrambi|Sì|Configurazione predefinita per le organizzazioni ibride. Consente a un singolo utente di valutare entrambi i client affiancati. Chat e chiamate possono atterrare in entrambi i client, quindi gli utenti devono sempre eseguire entrambi i client. Per evitare un'esperienza Skype for Business confusa o regressiva, le comunicazioni esterne (federate), i servizi vocali PSTN e le applicazioni vocali, l'integrazione di Office e molte altre integrazioni continuano a essere gestite da Skype for Business.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|Sì|"Riunioni per prime". Principalmente per le organizzazioni locali che possono trarre vantaggio dalle funzionalità delle riunioni di Teams, se non sono ancora pronte a spostare le chiamate nel cloud.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Sì|Punto di partenza alternativo per le organizzazioni complesse che richiedono un controllo amministrativo più rigoroso.|
|SfBOnly|Skype for Business|Skype for Business|No<sup>3</sup>|Scenario specializzato per le organizzazioni con requisiti rigorosi in relazione al controllo dei dati. Teams viene usato solo per partecipare a riunioni pianificate da altri.|
||||||

</br>
</br>

**Note:**

<sup>1</sup> La possibilità di partecipare a una riunione esistente (pianificata in Teams o in Skype for Business) non è disciplinata dalla modalità. Per impostazione predefinita, gli utenti possono sempre partecipare a qualsiasi riunione a cui sono stati invitati.

<sup>2</sup> Per impostazione predefinita, quando si assegna TeamsOnly o SfbWithTeamsCollabAndMeetings a un singolo utente, tutte le riunioni Skype for Business esistenti pianificate da quell'utente per il futuro vengono convertite in riunioni di Teams. Se lo si desidera, è possibile lasciare queste riunioni come riunioni Skype for Business specificando `-MigrateMeetingsToTeams $false` quando concedere TeamsUpgradePolicy o deselezionando la casella di controllo nel portale di Teams Amministrazione. La possibilità di convertire le riunioni da Skype for Business a Teams non è disponibile quando si concede TeamsUpgradePolicy a livello di tenant. 

<sup>3</sup> Attualmente, Teams non ha la possibilità di disabilitare la funzionalità Teams e canali, quindi questa funzionalità rimane abilitata per il momento.


## <a name="using-teamsupgradepolicy"></a>Uso di TeamsUpgradePolicy

TeamsUpgradePolicy espone due proprietà chiave: Mode e NotifySfbUsers. 
</br>
</br>

|Parametro|Tipo|Valori consentiti</br>(impostazione predefinita in corsivo)|Descrizione|
|---|---|---|---|
|Modalità|Enum|*Isole*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica la modalità di esecuzione del client.|
|NotifySfbUsers|Bool|*Falso* o vero|Indica se visualizzare un banner nel client Skype for Business per informare l'utente che Teams sostituirà presto Skype for Business. Questo non può essere vero se Mode=TeamsOnly.|
|||||

Teams fornisce tutte le istanze rilevanti di TeamsUpgradePolicy tramite criteri predefiniti di sola lettura. Di conseguenza, sono disponibili solo i cmdlet Get e Grant. Le istanze predefinite sono elencate di seguito.
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
|Globale</br>*Predefinito*|Isole|Falso|
||||

Queste istanze dei criteri possono essere concesse a singoli utenti o a livello di tenant. Ad esempio:
- Per aggiornare un utente ($SipAddress) a Teams, concedere l'istanza "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Per aggiornare l'intero tenant, omettere il parametro identity dal comando grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>L'esperienza utente del client di Teams quando si usano le modalità di Skype for Business

Quando un utente usa una delle modalità di Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), tutte le chat e le chiamate in arrivo vengono instradate al client Skype for Business dell'utente. Per evitare confusione per l'utente finale e garantire un corretto routing, chiamate e funzionalità di chat nel client Teams viene automaticamente disabilitato quando un utente si trova in una qualsiasi delle modalità di Skype for Business. Allo stesso modo, la pianificazione delle riunioni in Teams viene disabilitata automaticamente quando gli utenti sono in modalità SfBOnly o SfBWithTeamsCollab e automaticamente abilitata quando un utente è in modalità SfBWithTeamsCollabAndMeetings. Per informazioni dettagliate, vedere [Esperienza client di Teams e conformità alle modalità di coesistenza](./teams-client-experience-and-conformance-to-coexistence-modes.md).

> [!Note] 
> - Prima della distribuzione dell'applicazione automatica di Teams e Canali, le modalità SfbOnly e SfBWithTeamsCollab si comportano allo stesso modo.


## <a name="detailed-mode-descriptions"></a>Descrizioni dettagliate della modalità
</br>
</br>

|Modalità|Spiegazione|
|---|---|
|**Isole**</br>(solo locale)|Un utente esegue sia Skype for Business che Teams affiancati. Questo utente:</br><ul><li>Può avviare chat e chiamate VoIP in Skype for Business o nel client di Teams. Nota: gli utenti con Skype for Business ospitato localmente non possono avviare da Teams per raggiungere un altro utente Skype for Business, indipendentemente dalla modalità del destinatario.<li>Riceve chat & chiamate VoIP avviate in Skype for Business da un altro utente nel client Skype for Business.<li>Riceve chat & chiamate VoIP avviate in Teams da un altro utente nel client di Teams se si trovano nello *stesso tenant*.<li>Riceve chat & chiamate VoIP avviate in Teams da un altro utente nel client Skype for Business se si trovano in un *tenant federato*. <li>Include le funzionalità PSTN come indicato di seguito:<ul><li>Quando l'utente è ospitato in Skype for Business locale e dispone di VoIP aziendale, le chiamate PSTN vengono sempre avviate e ricevute in Skype for Business.<li>Quando l'utente è ospitato su Skype for Business Online e dispone di Sistema telefonico Microsoft, l'utente avvia e riceve sempre chiamate PSTN in Skype for Business:<ul><li>Ciò si verifica se l'utente ha un piano per chiamate Microsoft o si connette alla rete PSTN tramite Skype for Business Cloud Connector Edition o una distribuzione locale di Skype for Business Server (voce ibrida).<li>**Nota: il routing diretto del sistema telefonico non è supportato in modalità Isole.**</ul></ul><li>Riceve code di chiamata Microsoft e chiamate di operatore automatico in Skype for Business:<ul><li>I numeri di telefono assegnati alle code di chiamata e agli operatori automatici **non possono** essere numeri di routing diretto del sistema telefonico in modalità Isole.</ul></ul><li>Può pianificare riunioni in Teams o Skype for Business (e vedrà entrambi i plug-in per impostazione predefinita).<li>Può partecipare a qualsiasi Skype for Business o riunione di Teams; la riunione verrà aperta nel rispettivo client.</ul>|
|**SfBOnly**</br>(solo locale)|Un utente viene eseguito solo Skype for Business. Questo utente:</br><ul><li>Può avviare chat e chiamate solo da Skype for Business.<li>Riceve chat/chiamate nel client Skype for Business, indipendentemente da dove è stato avviato, a meno che l'iniziatore non sia un utente di Teams con Skype for Business ospitato in locale.*<li> Può pianificare solo Skype for Business riunioni, ma può partecipare a Skype for Business o a riunioni di Teams.</br>\** Non è consigliabile usare la modalità Islands con gli utenti locali in combinazione con altri utenti in modalità SfBOnly. Se un utente di Teams con Skype for Business ospitato in locale avvia una chiamata o una chat con un utente SfBOnly, l'utente SfBOnly non è raggiungibile e riceve una chat o un messaggio di chiamata perso.*|
|**SfBWithTeamsCollab**</br>(solo locale)|Un utente esegue sia Skype for Business che Teams affiancati. Questo utente:</br><ul><li>Dispone delle funzionalità di un utente in modalità SfBOnly.<li>Teams è abilitato solo per la collaborazione di gruppo (canali); la pianificazione di chat/chiamate/riunioni è disabilitata.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>(solo locale)|Un utente esegue sia Skype for Business che Teams affiancati. Questo utente:<ul><li>Dispone della funzionalità di chat e chiamata dell'utente in modalità SfBOnly.<li>Teams è abilitato per la collaborazione di gruppo (canali - include conversazioni di canale); la chat e le chiamate sono disabilitate.<li>Può pianificare solo riunioni di Teams, ma può partecipare a Skype for Business o a riunioni di Teams.</ul>|
|**TeamsOnly**</br>(solo utenti cloud)|Un utente esegue solo Teams. Questo utente:<ul><li>Riceve chat e chiamate nel client di Teams, indipendentemente da dove è stata avviata.<li>Può avviare chat e chiamate solo da Teams.<li>Può pianificare riunioni solo in Teams, ma può partecipare a Skype for Business o a riunioni di Teams.<li>Può continuare a usare Skype for Business telefoni IP.<br><br>*Non è consigliabile usare la modalità TeamsOnly in combinazione con altri utenti in modalità Isole finché l'adozione di Teams non è satura; ovvero, tutti gli utenti in modalità Isole usano e monitorano attivamente sia Teams che i client di Skype for Business. Se un utente di TeamsOnly avvia una chiamata o una chat con un utente isole, tale chiamata o chat verrà effettuata nel client Teams dell'utente isole; se l'utente isole non usa o monitora Teams, tale utente apparirà offline e non sarà raggiungibile dall'utente TeamsOnly.* <li>In alcuni casi, i partecipanti in modalità TeamsOnly potranno partecipare alle riunioni Skype for Business solo usando Skype for Business Web App o l'app Riunioni Skype come utente anonimo. Alla fine, questo caso sarà vero per tutti gli utenti in modalità TeamsOnly. Per altre informazioni, vedere [ritiro di Skype for Business Online](skype-for-business-online-retirement.md#what-to-expect-post-retirement).</ul> |
|||




## <a name="related-topics"></a>Argomenti correlati

[Coesistenza con Skype for Business](./coexistence-chat-calls-presence.md)

[Esperienza del client di Teams e conformità alle modalità di coesistenza](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Uso del servizio MMS (Meeting Migration Service)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
