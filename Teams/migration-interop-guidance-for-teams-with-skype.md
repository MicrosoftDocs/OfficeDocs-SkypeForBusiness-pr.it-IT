---
title: Migrazione e interoperabilità-Skype for business
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Informazioni sui concetti fondamentali per la gestione della transizione dell'organizzazione ai team da Skype for business.
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
ms.openlocfilehash: fd4c733aece4bc75c0bce16c77aebae4806fecd7
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904391"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business

> [!Tip] 
> Vedere la sessione seguente per informazioni sulla [coesistenza e l'interoperabilità](https://aka.ms/teams-upgrade-coexistence-interop)

Come organizzazione con Skype for business che inizia ad adottare teams, gli amministratori possono gestire l'esperienza utente nella propria organizzazione usando il concetto di coesistenza "Mode" che è una proprietà di TeamsUpgradePolicy. Usando la modalità, gli amministratori gestiscono l'interoperabilità e la migrazione mentre gestiscono la transizione da Skype for business a teams.  La modalità di un utente determina il modo in cui vengono pianificate le chat in arrivo e le chiamate in entrata del client, nonché in quali servizi (team o Skype for business) sono programmate nuove riunioni. Regola anche le funzionalità disponibili nel client teams. 


## <a name="fundamental-concepts"></a>Concetti fondamentali

1.  *Interoperabilità* : 1-1 comunicazione tra un utente di Lync/Skype for business e un utente di teams.

2.  *Federazione* : comunicazione tra utenti di tenant diversi.

3.  Tutti gli utenti di teams hanno un account Skype for business sottostante che è "homed" online o locale:
    - Gli utenti che usano già Skype for business online utilizzano il proprio account online esistente.
    - Gli utenti che usano già Skype for business/Lync locale usano il proprio account locale esistente.
    - Gli utenti per i quali non è possibile rilevare un account Skype for business esistente avranno un account Skype for business online automaticamente provisioning quando l'utente teams viene creato.

4.  Se si dispone di una distribuzione locale di Skype for business o Lync e si vuole che gli utenti siano utenti di teams, è necessario assicurarsi almeno che Azure AD Connect stia sincronizzando l'attributo msRTCSIP-DeploymentLocator in AAD, in modo che teams/Skype for business online rilevi correttamente l'ambiente locale. Inoltre, per trasferire tutti gli utenti in modalità solo Teams (ad esempio, aggiornare un utente), *devi prima configurare la modalità ibrida di Skype for business*. Per altre informazioni, vedere [configurare Azure ad Connect per Skype for business e teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  L'interoperabilità tra teams e gli utenti di Skype for business è possibile solo *se l'utente di teams è ospitato online in Skype for business*. L'utente destinatario di Skype for business può essere ospitato in locale (e richiede la configurazione di Skype for business Hybrid) o online. Gli utenti ospitati in Skype for business locale possono usare i team in modalità isole (definiti più avanti in questo documento), ma non possono usare team per l'interoperabilità o la Federazione con altri utenti che usano Skype for business.  

6.    Il comportamento di aggiornamento e di interoperabilità viene determinato in base alla modalità di coesistenza di un utente, descritto più avanti. La modalità è gestita da TeamsUpgradePolicy. 

7.  L'aggiornamento di un utente alla modalità TeamsOnly garantisce che tutte le chat in arrivo e le chiamate saranno sempre atterrate nel client Teams dell'utente, indipendentemente dal client da cui ha avuto origine. Questi utenti pianificano anche tutte le nuove riunioni in teams. Per essere in modalità TeamsOnly, un utente deve essere ospitato online in Skype for business. Questa operazione è necessaria per garantire l'interoperabilità, la Federazione e l'amministrazione completa dell'utente teams. Per aggiornare un utente a TeamsOnly:
    - Se l'utente è ospitato in Skype for business online (o non ha mai avuto un account Skype), concedere loro TeamsUpgradePolicy con Mode = TeamsOnly usando l'istanza "UpgradeToTeams" usando PowerShell oppure usare l'interfaccia di amministrazione di teams per selezionare la modalità di TeamsOnly.
    - Se l'utente è ospitato in locale, USA `Move-CsUser` gli strumenti di amministrazione locali per trasferire prima l'utente in Skype for business online.  Se si ha Skype for Business Server 2019 o CU8 per Skype for Business Server 2015, è possibile specificare l' `-MoveToTeams` opzione `Move-CsUser` per spostare l'utente direttamente in teams come parte dello sposta online. Questa opzione eseguirà anche la migrazione delle riunioni dell'utente in teams. Se `-MoveToTeams` non è specificato o non è disponibile, dopo `Move-CsUser` il completamento assegnare la modalità TeamsOnly a tale utente usando PowerShell o l'interfaccia di amministrazione teams. Per altri dettagli [, vedere trasferire utenti tra locale e cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Per altre informazioni sulla migrazione delle riunioni, vedere [uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

8.    Per usare Microsoft Phone System con teams, gli utenti devono essere in modalità TeamsOnly (ad esempio, ospitati in Skype for business online e aggiornati a teams) e devono essere configurati per il [routing diretto](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) di Microsoft Phone System (che consente di usare il sistema telefonico con i propri trunk e SBC) o di avere un piano di chiamata di Office 365. Il routing diretto di Microsoft Phone System non è supportato in modalità isole.    

9.  La pianificazione delle riunioni di teams con i servizi di audioconferenza (accesso esterno o chiamata in uscita tramite PSTN) è disponibile indipendentemente dal fatto che l'utente sia ospitato in Skype for business online o Skype for business locale. 


## <a name="coexistence-modes"></a>Modalità di coesistenza

L'interoperabilità e la migrazione vengono gestite in base alla modalità di coesistenza con TeamsUpgradePolicy. Le modalità di coesistenza garantiscono un'esperienza semplice e prevedibile per gli utenti finali come transizione delle organizzazioni da Skype for business a teams. Per un'organizzazione che si sposta in teams, la modalità TeamsOnly è la destinazione finale per ogni utente, anche se non tutti gli utenti devono essere assegnati TeamsOnly (o qualsiasi modalità) allo stesso tempo. Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare qualsiasi modalità Skype for business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) per garantire una comunicazione prevedibile tra gli utenti TeamsOnly e quelli che non sono ancora stati.


Da un punto di vista tecnico, la modalità di un utente regola diversi aspetti dell'esperienza dell'utente:

- *Routing in arrivo*: in quale client (teams o Skype for business) vengono effettuate le chat in arrivo e le chiamate terrestri? 
- *Pubblicazione presenza*: la presenza dell'utente viene visualizzata ad altri utenti in base alle proprie attività in teams o Skype for business? 
- *Pianificazione delle riunioni*: quale servizio viene usato per pianificare nuove riunioni e verificare che il componente aggiuntivo appropriato sia presente in Outlook? Tieni presente che TeamsUpgradePolicy non regola la partecipazione alla riunione. Gli utenti possono sempre *partecipare* a una riunione, sia che si tratti di una riunione Skype for business o di una riunione di teams.
- *Esperienza client*: quali funzionalità sono disponibili in teams e/o client Skype for business? Gli utenti possono avviare chiamate e chat in team, Skype for business o entrambi? L'esperienza di teams & Channels è disponibile?  

Per altri dettagli sul comportamento di routing e presenza in base alla modalità, Vedi [coesistenza con Skype for business](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence).

Tuttavia, da un punto di vista dell'esperienza, la modalità può essere descritta più semplicemente definendo l'esperienza per:
- *Chat e chiamate*: quale client usa un utente?
- *Pianificazione delle riunioni*: gli utenti possono pianificare nuove riunioni come team o riunioni Skype for business?
- *Disponibilità della funzionalità di collaborazione in teams client*. La funzionalità teams & canali e file è disponibile mentre gli utenti hanno ancora Skype for business?

Le modalità sono elencate di seguito.
</br>
</br>

|Modalità|Chiamata e chat|Pianificazione delle riunioni<sup>1</sup>|Canali & Teams|Caso di utilizzo|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Richiede Home in Skype for business online*|Teams|Teams|Sì|Stato finale dell'aggiornamento. Anche l'impostazione predefinita per i nuovi tenant.|
|Isole|Sia|Sia|Sì|Configurazione predefinita. Consente a un singolo utente di valutare entrambi i client affiancati. Le chat e le chiamate possono atterrare in entrambi i client, quindi gli utenti devono sempre eseguire entrambi i client. Per evitare un'esperienza di Skype for business confusa o regressione, le comunicazioni esterne (federate), i servizi vocali PSTN e le applicazioni vocali, l'integrazione di Office e molte altre integrazioni continuano a essere gestite da Skype for business.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|Sì|"First meetings". Principalmente per le organizzazioni locali per trarre vantaggio dalle funzionalità di riunione dei team, se non sono ancora pronte per la migrazione delle chiamate al cloud.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Sì|Punto di partenza alternativo per organizzazioni complesse che necessitano di un controllo amministrativo più rigoroso.|
|SfBOnly|Skype for Business|Skype for Business|No<sup>3</sup>|Scenario specializzato per le organizzazioni con requisiti severi intorno al controllo dati. Teams viene usato solo per partecipare alle riunioni pianificate da altri utenti.|
||||||

</br>
</br>

**Note:**

<sup>1</sup> la possibilità di partecipare a una riunione esistente (pianificata in teams o in Skype for business) non è regolata dalla modalità. Per impostazione predefinita, gli utenti possono sempre partecipare a una riunione a cui sono stati invitati.

<sup>2</sup> per impostazione predefinita, quando si assegna TeamsOnly o SfbWithTeamsCollabAndMeetings a un singolo utente, le riunioni Skype for business esistenti pianificate dall'utente per il futuro vengono convertite in riunioni teams. Se si vuole, è possibile uscire da queste riunioni come riunioni Skype for business specificando `-MigrateMeetingsToTeams $false` quando si concede TeamsUpgradePolicy oppure deselezionando la casella di controllo nel portale di amministrazione di teams.   Tieni presente che la possibilità di convertire le riunioni da Skype for business a teams non è disponibile quando concedi a TeamsUpgradePolicy una base a livello di tenant. 

<sup>3</sup> attualmente, teams non ha la possibilità di disabilitare la funzionalità Teams and Channels, quindi questo rimane abilitato per ora.



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: gestire la migrazione e la coesistenza

TeamsUpgradePolicy espone due proprietà chiave: mode e NotifySfbUsers. 
</br>
</br>

|Parametro|Tipo|Valori consentiti</br>(impostazione predefinita in corsivo)|Descrizione|
|---|---|---|---|
|Modalità|Enum|*Isole*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica la modalità in cui deve essere eseguito il client.|
|NotifySfbUsers|Bool|*Falso* o vero|Indica se mostrare un banner nel client Skype for business per informare l'utente che i team rimpiazzeranno presto Skype for business. Questo non può essere vero se Mode = TeamsOnly.|
|||||

Teams fornisce tutte le istanze rilevanti di TeamsUpgradePolicy tramite criteri predefiniti di sola lettura. Sono quindi disponibili solo i cmdlet Get e Grant. Le istanze predefinite sono elencate di seguito.
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
|Globale</br>*Predefinita*|Isole|Falso|
||||

Queste istanze di criteri possono essere concesse a singoli utenti o a una base a livello di tenant. Ad esempio:
- Per aggiornare un utente ($SipAddress) a teams, concedere l'istanza "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Per aggiornare l'intero tenant, omettere il parametro Identity dal comando Grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>Considerazioni sulla Federazione

La Federazione da Teams a un altro utente che usa Skype for business richiede che l'utente dei team sia ospitato online in Skype for business.

TeamsUpgradePolicy regola il routing per le chiamate e le Chat federate in arrivo. Il comportamento di routing federato è lo stesso per gli scenari dello stesso tenant, *ad eccezione della modalità isole*.  Quando i destinatari sono in modalità isole: 
- Chat e chiamate avviate da teams Land in SfB se il destinatario si trova in un *tenant federato*.
- Chat e chiamate avviate da teams atterrano in teams se il destinatario si trova nello *stesso tenant*.
- Le chat e le chiamate avviate da SfB sempre atterrano in Skype for business.

Per altre informazioni, Vedi [coesistenza con Skype for business](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence).

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>Esperienza utente del client teams quando si usano le modalità SfB
Quando un utente si trova in una delle modalità Skype for business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), tutte le chat in arrivo e le chiamate vengono instradate al client Skype for business dell'utente. Per evitare la confusione degli utenti finali e garantire un corretto routing, le funzionalità di chiamata e chat nel client Team vengono automaticamente disabilitate quando un utente si trova in una delle modalità Skype for business. Allo stesso modo, la pianificazione delle riunioni in team viene automaticamente disabilitata quando gli utenti si trovano nelle modalità SfBOnly o SfBWithTeamsCollab e vengono abilitati automaticamente quando un utente si trova in modalità SfBWithTeamsCollabAndMeetings. Per informazioni dettagliate, vedere [esperienza del client teams e conformità alle modalità di coesistenza](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Prima della consegna dell'applicazione automatica di team e canali, le modalità SfbOnly e SfBWithTeamsCollab si comportano allo stesso modo.


## <a name="detailed-mode-descriptions"></a>Descrizioni delle modalità dettagliate
</br>
</br>

|Modalità|Spiegazione|
|---|---|
|**Isole**</br>predefinita|Un utente esegue sia Skype for business che Team affiancati. Questo utente:</br><ul><li>Può avviare chat e chiamate VoIP sia in Skype for business che in client teams. Nota: gli utenti con Skype for business homed non possono avviare da teams per raggiungere un altro utente di Skype for business, indipendentemente dalla modalità del destinatario.<li>Riceve chat & chiamate VoIP avviate in Skype for business da un altro utente nel client Skype for business.<li>Riceve le chat & chiamate VoIP avviate in teams da un altro utente nel client teams se si trovano nello *stesso tenant*.<li>Riceve le chat & chiamate VoIP avviate in team da un altro utente nel client Skype for business se si trovano in un *tenant federato*. <li>Ha funzionalità PSTN come indicato di seguito:<ul><li>Quando l'utente è ospitato in Skype for business locale e ha VoIP aziendale, le chiamate PSTN vengono sempre avviate e ricevute in Skype for business.<li>Quando l'utente è ospitato in Skype for business online e ha un sistema telefonico Microsoft, l'utente avvia sempre e riceve chiamate PSTN in Skype for business:<ul><li>Questo problema si verifica indipendentemente dal fatto che l'utente disponga di un piano di chiamata Microsoft o si connetta alla rete PSTN tramite Skype for Business Cloud Connector Edition o una distribuzione locale di Skype for Business Server (Hybrid Voice).<li>**Nota: il routing diretto di Microsoft teams Phone System non è supportato in modalità isole.**</ul></ul><li>Riceve le code di chiamata Microsoft e le chiamate di operatore automatico in Skype for business:<ul><li>I numeri di telefono assegnati alle code di chiamata e gli operatori automatici **non possono** essere i numeri di routing diretto del sistema telefonico Microsoft teams in modalità isole.</ul></ul><li>Può pianificare riunioni in teams o Skype for business (e vedrà entrambi i plug-in per impostazione predefinita).<li>Può partecipare a qualsiasi riunione Skype for business o Teams; la riunione verrà aperta nel rispettivo client.</ul>|
|**SfBOnly**|Un utente esegue solo Skype for business. Questo utente:</br><ul><li>Può avviare chat e chiamate solo da Skype for business.<li>Riceve qualsiasi chat/chiamata nel client Skype for business indipendentemente da dove è stato avviato, a meno che l'iniziatore non sia un utente di teams con Skype for business homed locale. *Può programmare solo riunioni Skype for business, ma può partecipare a riunioni Skype for business o teams. <li> </br> *L'uso della modalità isole con gli utenti locali non è consigliato in combinazione con altri utenti in modalità SfBOnly. Se un utente di teams con Skype for business homed avvia una chiamata o una chat a un utente di SfBOnly, l'utente di SfBOnly non è raggiungibile e riceve un messaggio di posta elettronica di chat o chiamate perse. *|
|**SfBWithTeamsCollab**|Un utente esegue sia Skype for business che Team affiancati. Questo utente:</br><ul><li>Ha la funzionalità di un utente in modalità SfBOnly.<li>I team sono abilitati solo per la collaborazione di gruppo (canali); la programmazione chat/chiamata/riunione è disabilitata.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Un utente esegue sia Skype for business che Team affiancati. Questo utente:<ul><li>Offre la funzionalità di chat e chiamate dell'utente in modalità SfBOnly.<li>Teams è abilitato per la collaborazione di gruppo (canali-include le conversazioni di canale); la chat e le chiamate sono disabilitate.<li>Può programmare solo riunioni di teams, ma può partecipare a riunioni Skype for business o teams.</ul>|
|**TeamsOnly**</br>(richiede SfB Home online)|Un utente esegue solo teams. Questo utente:<ul><li>Riceve tutte le chat e le chiamate nel client teams, indipendentemente dal punto in cui è stato avviato.<li>Può avviare chat e chiamate solo da teams.<li>Può programmare le riunioni solo in teams, ma può partecipare a riunioni Skype for business o teams.<li>Può continuare a usare i telefoni IP di Skype for business.<br><br>*L'uso della modalità TeamsOnly in combinazione con altri utenti in modalità isole non è consigliato finché l'adozione dei team non è satura, ossia tutti gli utenti della modalità isole usano e monitorano attivamente sia i team che i client Skype for business. Se un utente di TeamsOnly avvia una chiamata o una chat a un utente di isole, la chiamata o la chat atterrerà nel client Teams dell'utente Islands; Se l'utente Islands non USA o monitora i team, l'utente verrà visualizzato offline e non sarà raggiungibile dall'utente di TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Argomenti correlati

[Coesistenza con Skype for Business](https://docs.microsoft.com/microsoftteams/coexistence-chat-calls-presence)

[Esperienza del client di Teams e conformità alle modalità di coesistenza](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
