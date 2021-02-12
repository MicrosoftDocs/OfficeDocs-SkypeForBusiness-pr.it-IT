---
title: Scegli il percorso di aggiornamento da Skype for Business a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: Dettagli delle opzioni di coesistenza di Skype for Business e Microsoft Teams e dei possibili percorsi di aggiornamento a Teams, con scenari di esempio.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 23a71a075730f1447259d6e3a4a3dd21f650bfd7
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578159"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Scegli il percorso di aggiornamento da Skype for Business a Teams

![Diagramma percorso di aggiornamento, enfatizzando il passaggio Definizione progetto](media/upgrade-banner-project-definition.png "Fasi del percorso di aggiornamento, con enfasi sulla fase definizione del progetto")

Questo articolo fa parte della fase di definizione del progetto per il percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Integrare gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità comprensibili di Skype for Business e Teams](https://aka.ms/SkypeToTeams-Coexist)

Come cliente esistente di Skype for Business, la transizione completa a Teams potrebbe richiedere del tempo. Tuttavia, puoi iniziare a realizzare il valore di Teams oggi stesso, consentendo ai tuoi utenti di usare Teams insieme a Skype for Business. Dato che tra le due app vi sono alcune funzionalità sovrapposte, è consigliabile esaminare le modalità di coesistenza e aggiornamento disponibili per determinare il percorso giusto per l'organizzazione. Ad esempio, è possibile scegliere di abilitare tutti i carichi di lavoro in entrambe le soluzioni senza interoperabilità. Oppure, si potrebbe decidere di gestire l'esperienza utente, introducendo gradualmente le funzionalità di Teams o mirando gruppi di utenti a capacità selezionate, fino a quando l'organizzazione non sarà pronta ad aggiornare tutti gli utenti a Teams. Usare il risultato del progetto pilota per valutare il percorso di aggiornamento più giusto per l'organizzazione.

> [!IMPORTANT]
> Skype for Business Online verrà ritirato il 31 luglio 2021 e non sarà più accessibile o supportato. Per ottimizzare la realizzazione dei vantaggi e garantire alla tua organizzazione il tempo necessario per implementare il tuo aggiornamento, ti consigliamo di iniziare oggi stesso il tuo percorso verso Microsoft Teams.

Questo articolo illustra le varie modalità che consentono di gestire le modali in Skype for Business e Teams disponibili per gli utenti. Come per qualsiasi distribuzione, è [](pilot-essentials.md) consigliabile eseguire una distribuzione pilota del piano previsto con un gruppo selezionato di utenti prima di aggiornare l'organizzazione a Teams. Ricorda, l'introduzione di una nuova tecnologia può essere un'interruzione per gli utenti. Valutare la conformità degli utenti e implementare un piano di comunicazione e formazione prima di implementare una delle modalità descritte di seguito.

> [!TIP]
> Partecipa per laboratori interattivi dal vivo in cui condivideremo indicazioni, procedure consigliate e risorse progettate per avviare la pianificazione e l'implementazione degli aggiornamenti.
>
>Partecipa prima [alla sessione Pianificare l'aggiornamento](https://aka.ms/SkypeToTeamsPlanning) per iniziare.


## <a name="upgrade-journey-building-blocks"></a>Blocchi predefiniti per il percorso di aggiornamento

Per preparare formalmente l'organizzazione per il percorso verso Teams, è necessario iniziare a pianificare gli scenari di aggiornamento che alla fine consentiranno all'organizzazione di completare Teams come unica soluzione di collaborazione e comunicazione.

Per guidare il processo decisionale, acquisire familiarità con le varie modalità, concetti e terminologia rilevanti per l'aggiornamento da Skype for Business a Teams. Per ulteriori informazioni, vedere [La coesistenza](https://aka.ms/SkypeToTeams-Coexist)e l'interoperabilità di Microsoft Teams e Skype for Business.

> [!NOTE]
> È anche necessario considerare gli scenari di migrazione vocale. Sistema telefonico è la tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365 o Office 365. Per collegare il Sistema telefonico alla rete PSTN (Public Switched Telephone Network) in modo che gli utenti possano effettuare telefonate in tutto il mondo, hai a che fare in base alle tue esigenze aziendali. Per ulteriori informazioni sulle opzioni di connettività Sistema telefonico e PSTN, consulta [Voice - Sistema telefonico e connettività PSTN.](cloud-voice-landing-page.md)

Un utente migrato a Teams non usa più un client Skype for Business se non per partecipare a una riunione ospitata in Skype for Business. Tutte le chat e le chiamate in arrivo vengono effettuate nel client Teams dell'utente, indipendentemente dal fatto che il mittente usi Teams o Skype for Business. Tutte le nuove riunioni organizzate dall'utente aggiornato verranno pianificate come riunioni di Teams. Se l'utente tenta di utilizzare il client Skype for Business, l'avvio di chat e chiamate viene bloccato<sup>1.</sup> Tuttavia, l'utente può (e deve) continuare a usare il client Skype for Business per partecipare alle riunioni a cui è stato invitato.

Gli amministratori gestiscono la loro transizione a Teams utilizzando il concetto di [modalità,](migration-interop-guidance-for-teams-with-skype.md)che è una proprietà di [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) Un utente migrato a Teams come descritto in precedenza è in modalità "TeamsOnly". Per un'organizzazione che sta eseguendo la migrazione a Teams, l'obiettivo finale è spostare tutti gli utenti in modalità TeamsOnly.

Esistono due metodi per eseguire la migrazione di un'organizzazione esistente con Skype for Business (online o locale) a Teams:

- **Metodo di sovrapposizione** (con la modalità Isole): gli utenti di un'organizzazione esistente di Skype for Business vengono introdotti in Teams in modo che possano usare entrambi i client affiancati durante una fase di transizione. Durante questo periodo, la maggior parte delle funzionalità di Teams, ma non tutte, è disponibile. Questa modalità per questa configurazione si parla di Isole, ed è la modalità predefinita per qualsiasi organizzazione esistente con Skype for Business. Una volta che l'organizzazione è pronta, l'amministratore sposta gli utenti in modalità TeamsOnly.

- **Metodo** di selezione delle funzionalità (utilizzando una o più modalità di Skype for Business): l'amministratore gestisce la transizione (da Skype for Business a Teams) delle funzionalità di chat, chiamate e pianificazione delle riunioni per gli utenti dell'organizzazione. Ognuna di queste funzioni è disponibile in Skype for Business o Teams, ma non in entrambe. Gli amministratori usano TeamsUpgradePolicy per controllare quando spostare questa funzionalità in Teams per gli utenti. Gli utenti che non sono ancora in modalità TeamsOnly continuano a usare Skype for Business per chat e chiamate e i due set di utenti possono comunicare tramite funzionalità di interoperabilità. Gli amministratori gestiscono la transizione progressivamente eseguendo la migrazione di più utenti in modalità TeamsOnly.

<sup>1 I</sup> client Skype for Business precedenti al 2017 non rispettano teamsUpgradePolicy. Accertati di utilizzare l'ultima versione del client Skype for Business disponibile nel tuo canale Office.

Ecco i fattori chiave per decidere il percorso appropriato per l'organizzazione. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Metodo di funzionalità di sovrapposizione (uso della modalità Isole)

Con il metodo delle funzionalità sovrapposte, gli utenti possono usare sia Teams che i client skype for Business per chat, chiamate VoIP e riunioni. Con questo metodo, le chiamate voiP e chat in Teams sono incentrate sull'intera organizzazione, mentre Skype for Business consente chat e chiamate VOIP/PSTN con organizzazioni esterne (se configurate). Le riunioni possono essere pianificate e frequentate in entrambi i prodotti.

Quando si usa il metodo delle funzionalità sovrapposte, il traffico di comunicazione per Skype for Business e Teams rimane separato (anche per lo stesso utente) e i due client diversi non comunicano mai tra loro (per gli utenti all'interno della stessa organizzazione). Le esperienze utente sono basate sulla configurazione del destinatario. Ad esempio, si supponga che l'utente A del destinatario utilizzi questo metodo di aggiornamento:

- Le comunicazioni avviate dal client Skype for Business di un altro utente verranno sempre provenienti dal client Skype for Business dell'Utente A.

- Le comunicazioni avviate dal client Teams da *un utente nella stessa* organizzazione verranno sempre provenienti dal client Teams dell'utente A.

- Le comunicazioni avviate dal client Teams da *un utente di un'organizzazione esterna* verranno sempre provenienti dal client Skype for Business dell'Utente A.

Se è stata assegnata una licenza di Microsoft 365 o Office 365 agli utenti, questa sarà l'esperienza di aggiornamento predefinita per l'organizzazione. Quando si assegna una licenza di Microsoft 365 o Office 365, le licenze di Teams e Skype for Business online vengono assegnate per impostazione predefinita. <sup>2</sup>

Per un funzionamento efficace di questo metodo, tutti gli utenti devono eseguire entrambi i client contemporaneamente. Le chat e le chiamate in arrivo dall'interno dell'organizzazione a un utente in modalità Isole possono essere effettuate nel client Skype for Business o Teams e questo non è sotto il controllo del destinatario. Dipende dal client utilizzato dal mittente per avviare la comunicazione. Se il mittente e il destinatario sono in organizzazioni diverse, le chiamate e le chat in arrivo verso un utente in modalità Isole vengono sempre verso il client Skype for Business.

Ad esempio, se un destinatario in modalità Isole ha effettuato l'accesso a Skype for Business ma non a Teams e qualcuno lo invia un messaggio da Teams, il destinatario in modalità Isole non vede il messaggio (ma alla fine riceverà un messaggio e-mail che indica che ha perso un messaggio in Teams). Allo stesso modo, se un utente esegue Teams ma non Skype for Business e qualcuno riceve messaggi da Skype for Business, l'utente non vede quella chat. Il comportamento in ognuno di questi casi è simile per le chiamate. Se gli utenti non eseguono entrambi i client, può facilmente causare frustrazione.

Con questo metodo di aggiornamento, la presenza funziona anche in modo indipendente tra Teams e Skype for Business. Questo significa che gli altri utenti potrebbero vedere stati presenza diversi per l'Utente A, a seconda del client che usano. Per maggiori dettagli, vedere [Presenza.](upgrade-to-Teams-on-prem-coexistence.md#presence)

- Gli altri utenti, quando usano Teams, visualizzano la presenza in base all'attività dell'utente A in Teams.

- Gli altri utenti, quando usano Skype for Business, visualizzano la presenza in base all'attività dell'utente A in Skype for Business.

Quando si è pronti per aggiornare gli utenti alla modalità TeamsOnly, è possibile aggiornare gli utenti singolarmente oppure contemporaneamente l'intero tenant usando il criterio a livello di tenant<sup>3.</sup> Dopo l'aggiornamento alla modalità TeamsOnly, un utente riceve tutte le chat e le chiamate in arrivo in Teams.

Tuttavia, i destinatari non aggiornati in modalità Isole possono continuare a ricevere chat e chiamate da un utente TeamsOnly nei client Skype for Business o Teams. Per le conversazioni esistenti, l'utente TeamsOnly risponderà al client da cui il mittente ha avviato la chat o la chiamata. 

Per le nuove conversazioni dal punto di vista dell'utente TeamsOnly, la chat o la chiamata andrà sempre al client Teams in modalità Isole. Ciò è dovuto al fatto che il client Teams mantiene thread di conversazione separati per le comunicazioni teams-to-teams e Teams-to-Skype for Business, anche per lo stesso utente. Per altre informazioni, vedere [Conversazioni di Teams - Interoperabilità e thread nativi.](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads)

La tabella seguente riepiloga l'esperienza di Teams sia per la modalità Isole che per la modalità TeamsOnly:

| Esperienza in Teams | In modalità Isole | In modalità TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chat e chiamate in arrivo ricevute in:|  Teams o Skype for Business | Teams |
| Chiamate PSTN ricevute in: | Skype for Business <br>L'uso della funzionalità PSTN in Teams non è supportato nella modalità Isole.     | Teams |   
 |Icone di presenza    | La presenza in Skype for Business e Teams è indipendente. Gli utenti possono visualizzare stati diversi per lo stesso utente di isole, a seconda del client che usano. | La presenza si basa esclusivamente sull'attività dell'utente in Teams. Tutti gli altri utenti, indipendentemente dal client che usano, possono vedere tale presenza. | 
 | Pianificazione delle riunioni    | Gli utenti possono pianificare riunioni in Teams o Skype for Business. Per impostazione predefinita, vengono visualizzati entrambi i componenti aggiuntivi in Outlook. È possibile impostare un criterio per le riunioni di Teams per controllare se gli utenti possono usare solo il componente aggiuntivo Riunione di Teams o entrambi i componenti aggiuntivi Riunione di Teams e Riunione Skype for Business. Per altre informazioni, vedere [Impostare il provider di riunioni per gli utenti in modalità Isole.](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode) |     Gli utenti pianificano solo riunioni in Teams. Solo il componente aggiuntivo di Teams è disponibile in Outlook. | 

La tabella seguente riepiloga i vantaggi e i vantaggi dell'uso del metodo di sovrapposizione delle funzionalità per eseguire la migrazione dell'organizzazione a Teams.

| Professionisti     |       Contro |
| :------------------ | :---------------- |
| Consente un'adozione rapida all'interno di un'organizzazione.| Potenziale confusione per gli utenti finali, perché sono presenti due client con funzionalità simili, ma interfacce utente diverse. Inoltre, non hanno alcun controllo su quale client vengono effettuate le chat/chiamate in arrivo. |
| Consente agli utenti di imparare e acquisire familiarità con Teams pur avendo accesso completo a Skype for Business. | Possibile insoddisfazione dell'utente finale a causa di messaggi persi se l'utente non esegue entrambi i client.|
| Attività amministrative minime per iniziare a usare Teams. | Può essere difficile uscire dalla modalità Isole e passare alla modalità TeamsOnly se gli utenti e quelli con cui comunicano regolarmente non usano attivamente Teams.|
|Consente agli utenti di sfruttare funzionalità per migliorare il lavoro in team che non sono disponibili in Skype for Business.| Un utente che usa Skype for Business locale e Teams non sarà in grado di comunicare da Teams con un altro utente che usa Skype for Business locale ma non ha Teams.  |

<sup>2</sup> Ciò vale anche se l'utente è ospitata in locale in Skype for Business Server. Sia che l'utente sia ospitata in locale o online, lasciare abilitata la licenza di Skype for Business Online, perché è attualmente necessaria per le funzionalità complete di Teams.

<sup>3</sup> Tenere presente che la migrazione delle riunioni di Skype for Business alle riunioni di Teams viene attivata solo quando si applica TeamsUpgradePolicy ai singoli utenti, non per singoli tenant. Per [informazioni dettagliate, vedere](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) Migrazione delle riunioni.

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Metodo di selezione delle funzionalità (utilizzo delle modalità Skype for Business)

Alcune organizzazioni potrebbero preferire offrire agli utenti finali un'esperienza più prevedibile durante il passaggio da Skype for Business a Teams. In questo modello, gli amministratori IT usano una delle modalità di Skype for Business in TeamsUpgradePolicy per designare esplicitamente quali funzionalità rimangono in Skype for Business prima della migrazione alla modalità TeamsOnly. Quando sono pronte a spostare le funzionalità selezionate in modalità TeamsOnly, l'amministratore aggiorna la modalità per tali utenti a TeamsOnly. Durante la transizione:

- Gli amministratori hanno la possibilità di abilitare determinate funzionalità di Teams per gli utenti, mantenendo allo stesso tempo le funzionalità di chat e chiamata in Skype for Business prima che gli utenti si spostino in TeamsOnly. L'amministrazione può abilitare le funzionalità di collaborazione di Teams o le riunioni e le funzionalità di collaborazione di Teams.

- Gli utenti che utilizzano ancora Skype for Business ricevono tutte le chat e le chiamate in arrivo nel client Skype for Business, indipendentemente dal fatto che la comunicazione sia stata originata dal client Teams dell'altro utente o Skype for Business. Inoltre, per questi utenti Skype for Business, le funzionalità di chiamata e chat nel client Teams sono disabilitate per evitare confusione degli utenti finali e per garantire routing e presenza adeguati.

- Gli utenti in modalità TeamsOnly ricevono tutte le chat e le chiamate in arrivo nel client di Teams e la presenza viene fornita da Teams, indipendentemente da dove proviene la comunicazione: Teams, Skype for Business o qualsiasi tipo di utente federato.

A differenza del metodo delle funzionalità sovrapposte, nel metodo di selezione delle funzionalità, gli utenti che usano Skype for Business possono comunicare con gli utenti in TeamsOnly. La comunicazione tra un utente Skype for Business e un utente teams è nota come [interoperabilità](upgrade-to-Teams-on-prem-coexistence.md#interoperability) o "interoperabilità". La comunicazione interoperabilità è possibile uno-a-uno per chat e chiamate tra un utente in Skype for Business e un altro utente in Teams. Inoltre, gli utenti invitati possono sempre partecipare a una riunione Skype for Business o Teams, tuttavia devono utilizzare un client corrispondente al tipo di riunione. Per altre informazioni, vedere [Riunioni.](upgrade-to-Teams-on-prem-coexistence.md#meetings)

Per gli utenti con un metodo di funzionalità di selezione, la presenza per un utente è coerente indipendentemente dal client usato dall'altro utente. Se l'utente è in una delle modalità Skype for Business, tutti gli altri utenti visualizzano la presenza in base all'attività dell'utente in Skype for Business. Allo stesso modo, se un utente è in modalità TeamsOnly, tutti gli altri utenti vedono la presenza in base all'attività dell'utente in Teams. Per informazioni dettagliate, vedere [Presenza.](upgrade-to-Teams-on-prem-coexistence.md#presence)

Per un'organizzazione che ha scelto di seguire il metodo di selezione delle funzionalità, l'amministratore deve modificare la modalità a livello di tenant da Isole alla modalità di coesistenza di Skype for Business appropriata (SfbWithTeamsCollab o SfBWithTeamsCollabAndMeetings).  

Le esperienze utente guest aderiranno alla modalità di coesistenza assegnata al tenant. Se si imposta una modalità Skype for Business a livello di tenant, i guest non possono chattare, chiamare o mostrare la loro presenza. Per altre informazioni, vedere [Accesso guest in Teams](guest-access.md).

Quando la modalità cambia da Isole a SfbWithTeamsCollab, un utente che non ha mai usato Teams non avrà alcuna differenza nel modo in cui usa Skype for Business. Tuttavia, se un utente iniziasse a usare Teams, verrebbe esposto solo a funzionalità come Teams & Channel e File. Le chat, le chiamate e la pianificazione delle riunioni non sono disponibili in Teams, perché l'amministratore ha (per ora) designato Skype for Business come client desiderato per queste funzioni.

> [!NOTE]
> Quando l'Utente A cambia modalità isole a una delle modalità Skype for Business, il client Teams di qualsiasi altro utente che comunica con l'Utente A deve sapere che la modalità dell'utente A è cambiata in modo da poter instradare la comunicazione al client appropriato per l'Utente A. Per tutti gli utenti che hanno già stabilito chat native Teams su Teams con l'Utente A, può essere necessario del tempo prima che i client di Teams di questi altri utenti siano a conoscenza del cambiamento di modalità da Isole a qualsiasi modalità Skype for Business. Quando gli amministratori sono pronti, possono spostare la chat, le chiamate e la pianificazione delle riunioni per un determinato utente in Teams in una sola volta aggiornando la modalità dell'utente a TeamsOnly.

In alternativa, l'amministratore può spostare in Teams solo la pianificazione delle riunioni, lasciando la chat e chiamando le funzioni in Skype for Business usando la modalità SfBWithTeamsCollabAndMeetings. Questa modalità consente alle organizzazioni di passare a Teams per le riunioni, se gli utenti non sono ancora pronti a passare alla modalità TeamsOnly (ad esempio, non si è ancora pronti per eseguire la migrazione delle funzionalità PSTN esistenti). Questo scenario di transizione si parla di [prima](meetings-first.md)riunione.


|Esperienza in Teams  |In modalità SfBWithTeamsCollab |In modalità SfBWithTeamsCollabAndMeetings |In modalità TeamsOnly  |
|---------|---------|---------|---------|
|Chat in arrivo e chiamate VOIP da utenti dell'organizzazione ricevuti in:     | Skype for Business        | Skype for Business       | Teams        |
|Chiamate PSTN ricevute in:     | Skype for Business        |Skype for Business         | Teams        |
|Icone di presenza     | Skype for Business        |Skype for Business         | Teams        |
|Pianificazione di riunioni     | Skype for Business         | Teams        | Teams        |


La tabella seguente riepiloga i vantaggi e i vantaggi dell'uso delle modalità Skype for Business come passaggio di transizione verso la modalità TeamsOnly.

| Professionisti     |       Contro |
| :------------------ | :---------------- |
| Routing prevedibile per l'utente finale. Tutte le chiamate e le chat vengono effettuate in Skype for Business o Teams (ma non in entrambi), in base alla selezione dell'amministratore.|Le conversazioni di interoperabilità non supportano il formato RTF, la condivisione di file e la condivisione dello schermo. Questa operazione può essere utilizzata sfruttando la funzionalità Riunione adesso per avviare una riunione. |
|Può ridurre la confusione degli utenti finali perché una determinata funzionalità è disponibile solo in un client. | Gli utenti non hanno accesso a Teams per le attività comuni eseguite in Skype for Business come la chat e le chiamate in anticipo rispetto all'aggiornamento a TeamsOnly.|
|L'amministratore ha aumentato il controllo sul set di funzionalità disponibili per gli utenti durante la transizione da Skype for Business a Teams. | |
| Consente a un'organizzazione di usare Teams per le riunioni, anche se non è ancora ancora pronto per essere spostato completamente in modalità TeamsOnly.||
|La presenza di un determinato utente come visualizzato da altri è la stessa, indipendentemente dal client che usano.||

## <a name="summary-of-upgrade-methods"></a>Riepilogo dei metodi di aggiornamento
La tabella seguente riepiloga i metodi di aggiornamento:


|Funzionalità di sovrapposizione (con la modalità Isole)  |Funzionalità selezionate (utilizzando le modalità Skype for Business)  |
|---------|---------|
|Prima di essere aggiornati a TeamsOnly, gli utenti devono eseguire entrambi i client contemporaneamente, perché le chat e le chiamate in arrivo potrebbero essere in entrambi i client.     | Le chat e le chiamate vengono effettuate su un solo client, in base alla modalità del destinatario. Gli utenti non aggiornati possono eseguire entrambi i client, ma non esiste alcuna sovrapposizione funzionale (le chiamate e le chat non sono disponibili in Teams).         |
|Consente agli amministratori di introdurre funzionalità sovrapposte (chat, riunioni, chiamate VOIP) sia in Skype for Business che in Teams agli utenti finali, nonché nuove funzionalità (team e canali) in Teams.     | Consente agli amministratori di introdurre funzionalità selezionate di Teams agli utenti finali (team e canali), senza fornire le stesse funzionalità già presenti in Skype for Business.        |
|L'interoperabilità tra Skype for Business e Teams non esiste mentre entrambi gli utenti sono in modalità Isole.      |L'interoperabilità è necessaria per la comunicazione tra gli utenti di Skype for Business e Teams.         |

> [!NOTE]
> Se non sei in grado di seguire i metodi supportati per la migrazione degli utenti di Skype for Business Server a Teams, sarebbe possibile eseguire la transizione degli utenti a Teams rimuovendo Skype for Business Server e tutti gli attributi utente correlati in Active Directory. Dopo aver cancellato gli attributi di Azure Active Directory degli utenti dagli attributi di Skype for Business Server e aver fatto di nuovo riferimento ai record DNS a Microsoft 365 o Office 365, sarebbe quindi possibile ottenere una licenza per gli utenti in Microsoft 365 o Office 365 e aggiornarli a Teams. 

> [!IMPORTANT]
> Con la migrazione completa, i dati dei contatti e le riunioni non verranno migrati dall'ambiente locale a Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Punto di decisione</td><td><ul> Quale percorso di aggiornamento è adatto ai requisiti aziendali dell'organizzazione?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Passaggio successivo</td><td><ul> Identificare il modello di distribuzione corrente, gli scenari di utilizzo e le considerazioni chiave per l'organizzazione informerà il percorso verso Teams più adatto alla propria organizzazione.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Punto di decisione</td><td><ul> Quale scenario di aggiornamento è applicabile alla tua organizzazione?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul> Decidi la sequenza temporale del percorso di aggiornamento della tua organizzazione in base ai requisiti aziendali relativi a messaggistica, riunioni e chiamate.<br><br> Decidi il lavoro aggiuntivo necessario per completare il percorso di aggiornamento.<br><br></ul></td></tr>
</table>

Dopo aver scelto il percorso di aggiornamento migliore per la propria organizzazione, [eseguire l'aggiornamento a Teams.](https://aka.ms/SkypeToTeams-Upgrade)
