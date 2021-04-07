---
title: Scegli il percorso di aggiornamento da Skype for Business a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: Dettagli sulle opzioni di coesistenza di Skype for Business e Microsoft Teams e sui possibili percorsi di aggiornamento a Teams, con scenari di esempio.
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
ms.openlocfilehash: 015a0f079f5e95f43c4245ff48f2d88df0e1fa74
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598305"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Scegli il percorso di aggiornamento da Skype for Business a Teams

![Diagramma percorso di aggiornamento, enfatizzando la fase di definizione del progetto](media/upgrade-banner-project-definition.png "Fasi del percorso di aggiornamento, con enfasi sulla fase definizione progetto")

Questo articolo fa parte della fase definizione progetto del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Coinvolgimento degli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](./upgrade-define-project-scope.md)
- [Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

In quanto cliente skype for business esistente, la transizione completa a Teams potrebbe richiedere del tempo. Tuttavia, puoi iniziare a renderti conto del valore di Teams oggi stesso, consentendo agli utenti di usare Teams insieme a Skype for Business. Dato che tra le due app sono presenti alcune funzionalità sovrapposte, è consigliabile esaminare le modalità di coesistenza e aggiornamento disponibili per determinare il percorso più corretto per l'organizzazione. Ad esempio, è possibile scegliere di abilitare tutti i carichi di lavoro in entrambe le soluzioni senza interoperabilità. Oppure, è possibile decidere di gestire l'esperienza utente, introducendo gradualmente le funzionalità di Teams o selezionando gruppi di utenti per le funzionalità selezionate, fino a quando l'organizzazione non sarà pronta per l'aggiornamento di tutti gli utenti a Teams. Usare il risultato del progetto pilota per valutare il percorso di aggiornamento più giusto per l'organizzazione.

> [!IMPORTANT]
> Skype for Business Online verrà ritirato il 31 luglio 2021 e non sarà più accessibile o supportato. Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti consigliamo di iniziare il tuo viaggio verso Microsoft Teams oggi stesso.

Questo articolo descrive le varie modalità che consentono di gestire le modalità disponibili per gli utenti in Skype for Business e Teams. Come per qualsiasi distribuzione, è [](pilot-essentials.md) consigliabile pilotare il piano previsto con un gruppo selezionato di utenti prima di aggiornare l'organizzazione a Teams. Tenere presente che l'introduzione di nuove tecnologie può essere dirompente per gli utenti. Valutare la conformità degli utenti e implementare un piano di comunicazione e formazione prima di implementare una delle modalità descritte di seguito.

> [!TIP]
> Unisciti a noi per laboratori interattivi in tempo reale in cui condivideremo indicazioni, procedure consigliate e risorse progettate per avviare la pianificazione e l'implementazione degli aggiornamenti.
>
>Per [iniziare, partecipare](./upgrade-workshops-landing-page.yml) alla sessione Di pianificazione dell'aggiornamento.


## <a name="upgrade-journey-building-blocks"></a>Blocchi predefiniti del percorso di aggiornamento

Per preparare formalmente l'organizzazione per il suo viaggio in Teams, è necessario iniziare a pianificare gli scenari di aggiornamento che alla fine consentiranno all'organizzazione di adottare completamente Teams come unica soluzione di comunicazione e collaborazione.

Per guidare il processo decisionale, familiarizzare con le varie modalità, concetti e terminologia rilevanti per l'aggiornamento da Skype for Business a Teams. Per altre informazioni, vedere Coesistenza e interoperabilità di Microsoft Teams e [Skype for Business.](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

> [!NOTE]
> È anche necessario considerare gli scenari di migrazione vocale. Sistema telefonico è la tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365 o Office 365. Per connettere Sistema telefonico alla rete PSTN (Public Switched Telephone Network) in modo che gli utenti possano effettuare chiamate telefoniche in tutto il mondo, sono disponibili opzioni in base alle esigenze aziendali. Per altre informazioni sulle opzioni di connettività Sistema telefonico e PSTN, vedere [Voce - Sistema telefonico e Connettività PSTN.](cloud-voice-landing-page.md)

Un utente di cui è stata eseguita la migrazione a Teams non usa più un client Skype for Business se non per partecipare a una riunione ospitata in Skype for Business. Tutte le chat e le chiamate in arrivo vengono effettuate nel client Teams dell'utente, indipendentemente dal fatto che il mittente usi Teams o Skype for Business. Le nuove riunioni organizzate dall'utente aggiornato verranno pianificate come riunioni di Teams. Se l'utente prova a usare il client Skype for Business, l'avvio di chat e chiamate viene bloccato<sup>1</sup>. Tuttavia, l'utente può (e deve) continuare a usare il client Skype for Business per partecipare alle riunioni a cui è invitato.

Gli amministratori gestiscono la transizione a Teams usando il concetto di [modalità](migration-interop-guidance-for-teams-with-skype.md), che è una proprietà di [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true). Un utente di cui è stata eseguita la migrazione a Teams come descritto in precedenza è in modalità "TeamsOnly". Per un'organizzazione che esegue la migrazione a Teams, l'obiettivo finale è spostare tutti gli utenti in modalità TeamsOnly.

Esistono due metodi per eseguire la migrazione di un'organizzazione esistente con Skype for Business (online o locale) a Teams:

- **Metodo delle funzionalità** sovrapposte (con la modalità Isole): gli utenti di un'organizzazione Skype for Business esistente vengono introdotti in Teams in modo che possano usare entrambi i client affiancati durante una fase di transizione. Durante questo periodo, la maggior parte delle funzionalità di Teams, ma non tutte, è disponibile. La modalità per questa configurazione è denominata Isole e questa è la modalità predefinita per qualsiasi organizzazione esistente con Skype for Business. Quando l'organizzazione è pronta, l'amministratore sposta gli utenti in modalità TeamsOnly.

- Metodo di selezione delle funzionalità **(con** una o più modalità Skype for Business): l'amministratore gestisce la transizione (da Skype for Business a Teams) della funzionalità di chat, chiamate e pianificazione delle riunioni per gli utenti dell'organizzazione. Ognuna di queste funzioni è disponibile in Skype for Business o Teams, ma non in entrambe. Gli amministratori usano TeamsUpgradePolicy per controllare quando spostare questa funzionalità in Teams per gli utenti. Gli utenti che non sono ancora in modalità TeamsOnly continuano a usare Skype for Business per chat e chiamate e i due set di utenti possono comunicare tramite funzionalità di interoperabilità. Gli amministratori gestiscono la transizione eseguendo progressivamente la migrazione di più utenti in modalità TeamsOnly.

<sup>1</sup> I client Skype for Business meno recenti spediti prima del 2017 non rispettano TeamsUpgradePolicy. Assicurati di usare l'ultimo client Skype for Business disponibile nel tuo canale Office.

Dopo aver compreso e scelto il metodo di aggiornamento, è possibile ottenere informazioni sugli strumenti per la gestione [dell'aggiornamento dell'organizzazione a Teams.](upgrade-to-teams-on-prem-tools.md)

Di seguito sono riportati i fattori chiave per decidere il percorso appropriato per l'organizzazione.

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Metodo delle funzionalità sovrapposte (con la modalità Isole)

Con il metodo delle funzionalità sovrapposte, gli utenti possono usare sia i client teams che i client Skype for Business per chat, chiamate VoIP e riunioni. In questo metodo, le chiamate di chat e VOIP in Teams sono incentrate sull'intera organizzazione, mentre Skype for Business abilita la chat e le chiamate VOIP/PSTN con organizzazioni esterne (se configurate). Le riunioni possono essere pianificate e frequentate in entrambi i prodotti.

Quando si usa il metodo delle funzionalità sovrapposte, il traffico di comunicazione per Skype for Business e Teams rimane separato (anche per lo stesso utente) e i due client diversi non comunicano mai tra loro (per gli utenti all'interno della stessa organizzazione). Le esperienze utente si basano sulla configurazione del destinatario. Si supponga, ad esempio, che il destinatario Utente A sia in modalità Isole:

- Le comunicazioni avviate dal client Skype for Business di un altro utente saranno sempre presenti nel client Skype for Business dell'utente A.

- Le comunicazioni avviate dal client Teams da un *utente* della stessa organizzazione saranno sempre presenti nel client Teams dell'utente A.

- Le comunicazioni avviate dal client Teams da un *utente in* un'organizzazione esterna saranno sempre presenti nel client Skype for Business dell'utente A.

Se agli utenti è stata assegnata una licenza di Microsoft 365 o Office 365, questa sarà l'esperienza di aggiornamento predefinita per l'organizzazione. Quando si assegna una licenza di Microsoft 365 o Office 365, per impostazione predefinita vengono assegnate sia le licenze di Teams che di Skype for Business online. <sup>2</sup>

Per il funzionamento efficace di questo metodo, tutti gli utenti devono eseguire entrambi i client contemporaneamente. Le chat e le chiamate in arrivo dall'interno dell'organizzazione a un utente in modalità Isole possono essere effettuate nel client Skype for Business o Teams, che non è sotto il controllo del destinatario. Dipende dal client utilizzato dal mittente per avviare la comunicazione. Se il mittente e il destinatario sono in organizzazioni diverse, le chiamate in arrivo e le chat con un utente in modalità Isole vengono sempre effettuate nel client Skype for Business.

Ad esempio, se un destinatario della modalità Isole è connesso a Skype for Business ma non a Teams e qualcuno li invia un messaggio da Teams, il destinatario della modalità Isole non visualizza il messaggio (ma alla fine riceverà un messaggio di posta elettronica che indica che ha perso un messaggio in Teams). Allo stesso modo, se un utente esegue Teams ma non Skype for Business e un utente riceve un messaggio da Skype for Business, l'utente non vede la chat. Il comportamento in ognuno di questi casi è simile per le chiamate. Se gli utenti non eseguono entrambi i client, può facilmente causare frustrazione.

La presenza funziona anche in modo indipendente tra Teams e Skype for Business quando usi questo metodo di aggiornamento. Questo significa che altri utenti potrebbero vedere stati di presenza diversi per l'utente A, a seconda del client che usano. Per altre informazioni, vedere [Presenza](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence).

- Gli altri utenti, quando usano Teams, visualizzano la presenza in base all'attività dell'utente A in Teams.

- Gli altri utenti, quando usano Skype for Business, visualizzano la presenza in base all'attività dell'utente A in Skype for Business.

Dopo aver completato l'aggiornamento degli utenti alla modalità TeamsOnly, è possibile aggiornare gli utenti singolarmente oppure l'intero tenant contemporaneamente usando i criteri a livello di tenant<sup>3.</sup> Dopo l'aggiornamento alla modalità TeamsOnly, un utente riceve tutte le chat e le chiamate in arrivo in Teams. Si noti che la migrazione delle riunioni Skype for Business alle riunioni di Teams viene attivata solo quando si applica TeamsUpgradePolicy ai singoli utenti, non in base al tenant. Per [informazioni dettagliate, vedere](upgrade-to-teams-on-prem-tools.md#meeting-migration) Migrazione delle riunioni.

Tuttavia, i destinatari non aggiornati in modalità Isole potrebbero continuare a ricevere chat e chiamate da un utente TeamsOnly nei client Skype for Business o Teams. Per le conversazioni esistenti, l'utente TeamsOnly risponderà al client da cui il mittente ha avviato la chat o la chiamata. 

Per le nuove conversazioni dal punto di vista dell'utente TeamsOnly, la chat o la chiamata passa sempre al client Teams in modalità Isole. Questo perché il client Teams mantiene thread di conversazione separati per le comunicazioni teams-to-Teams e Teams-to-Skype for Business, anche per lo stesso utente. Per altre informazioni, vedere [Conversazioni di Teams - Interoperabilità e thread nativi.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)

La tabella seguente riepiloga l'esperienza di Teams sia per la modalità Isole che per la modalità TeamsOnly:

| Esperienza di Teams | In modalità Isole | In modalità TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chat e chiamate in arrivo ricevute in:|  Teams o Skype for Business | Teams |
| Chiamate PSTN ricevute in: | Skype for Business <br>L'uso della funzionalità PSTN in Teams non è supportato in modalità Isole.     | Teams |   
 |Icone di presenza    | La presenza in Skype for Business e Teams è indipendente. Gli utenti possono visualizzare stati diversi per lo stesso utente delle Isole, a seconda del client che usano. | La presenza si basa esclusivamente sull'attività dell'utente in Teams. Tutti gli altri utenti, indipendentemente dal client che usano, vedono questa presenza. | 
 | Pianificazione delle riunioni    | Gli utenti possono pianificare riunioni in Teams o Skype for Business. Per impostazione predefinita, verranno visualizzati entrambi i componenti aggiuntivi in Outlook. È possibile impostare criteri di riunione di Teams per controllare se gli utenti possono usare solo il componente aggiuntivo Riunione di Teams o entrambi i componenti aggiuntivi Riunione Teams e Riunione Skype for Business. Per altre informazioni, vedere [Impostare il provider di riunioni per gli utenti in modalità Isole.](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode) |     Gli utenti pianificano solo riunioni in Teams. In Outlook è disponibile solo il componente aggiuntivo Teams. | 

La tabella seguente riepiloga i pro e i contro dell'uso del metodo delle funzionalità sovrapposte per eseguire la migrazione dell'organizzazione a Teams.

| Professionisti     |       Contro |
| :------------------ | :---------------- |
| Consente un'adozione rapida all'interno di un'organizzazione.| Potenziale confusione per gli utenti finali perché esistono due client con funzionalità simili, ma interfacce utente diverse. Inoltre, non hanno alcun controllo sul client in cui vengono effettuate le chat/chiamate in arrivo. |
| Consente agli utenti di imparare e acquisire familiarità con Teams pur avendo accesso completo a Skype for Business. | Potenziale insoddisfazione dell'utente finale a causa di messaggi persi se l'utente non esegue entrambi i client.|
| Attività amministrative minime per iniziare a usare Teams. | Può essere difficile uscire dalla modalità "Isole" e passare alla modalità TeamsOnly se gli utenti e gli utenti con cui comunicano regolarmente non usano attivamente Teams. Ad esempio, dopo l'aggiornamento di un sottoinsieme di utenti alla modalità TeamsOnly, questi utenti invieranno solo in Teams. Per il resto della popolazione in modalità Isole, questi messaggi verranno sempre inviati a Teams. Ma se alcuni di questi utenti non eseguono Teams, percepiranno questi messaggi come persi.|
|Consente agli utenti di sfruttare le funzionalità per migliorare il lavoro in team che non sono disponibili in Skype for Business.| Un utente che usa Skype for Business locale e Teams non sarà in grado di comunicare da Teams con un altro utente che usa Skype for Business in locale ma non ha Teams.  |
|  | Quando si usa Teams, gli utenti che hanno un account locale in Skype for Business Server non hanno supporto per l'interoperabilità o la federazione.  Questo può creare confusione se si ha un mix di utenti delle Isole, alcuni ospitati in Skype for Business online e altri in Skype for Business locale.   |

<sup>2</sup> Questo vale anche se l'utente è ospitata in locale in Skype for Business Server. Indipendentemente dal fatto che l'utente sia ospitata in locale o online, lasciare abilitata la licenza di Skype for Business Online, perché è attualmente necessaria per le funzionalità complete di Teams.

<sup>3</sup> Tenere presente che la migrazione delle riunioni Skype for Business alle riunioni di Teams viene attivata solo quando si applica TeamsUpgradePolicy ai singoli utenti, non in base al tenant. Per [informazioni dettagliate, vedere](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) Migrazione delle riunioni.

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Metodo di selezione delle funzionalità (con le modalità Skype for Business)

Alcune organizzazioni potrebbero preferire offrire agli utenti finali un'esperienza più prevedibile quando l'organizzazione passa da Skype for Business a Teams. In questo modello, gli amministratori IT usano una delle modalità Skype for Business in TeamsUpgradePolicy per designare esplicitamente le funzionalità che rimangono in Skype for Business prima della migrazione alla modalità TeamsOnly. Quando sono pronti a spostare le funzionalità selezionate in modalità TeamsOnly, l'amministratore aggiorna la modalità per tali utenti a TeamsOnly. Durante questa transizione:

- Gli amministratori hanno opzioni per abilitare determinate funzionalità di Teams per gli utenti mantenendo le funzionalità di chat e chiamate in Skype for Business prima che gli utenti spostino all'esperienza TeamsOnly. L'amministrazione può abilitare le funzionalità di collaborazione di Teams o le riunioni di Teams e le funzionalità di collaborazione.

- Gli utenti ancora su Skype for Business ricevono tutte le chat e le chiamate in arrivo nel client Skype for Business, indipendentemente dal fatto che la comunicazione sia stata originata dal client Teams o Skype for Business dell'altro utente. Inoltre, per questi utenti di Skype for Business, le funzionalità di chiamata e chat nel client Teams sono disabilitate per evitare confusione tra gli utenti finali e per garantire un routing e una presenza adeguati.

- Gli utenti in modalità TeamsOnly ricevono tutte le chat e le chiamate in arrivo nel client di Teams e la presenza è fornita da Teams, indipendentemente da dove ha avuto origine la comunicazione: Teams, Skype for Business o qualsiasi tipo di utente federato.

A differenza del metodo delle funzionalità sovrapposte (Isole), nel metodo di selezione delle funzionalità, gli utenti che usano Skype for Business possono comunicare con gli utenti che usano TeamsOnly. La comunicazione tra un utente skype for business e un utente di Teams è [nota](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability) come interoperabilità o "interoperabilità". La comunicazione di interoperabilità è possibile uno-a-uno per le chat e le chiamate tra un utente in Skype for Business e un altro utente in Teams. Inoltre, gli utenti invitati possono sempre partecipare a una riunione Skype for Business o Teams, ma devono usare un client corrispondente al tipo di riunione. Per altre informazioni, vedere [Riunioni](teams-and-skypeforbusiness-coexistence-and-interoperability.md#meetings).

Per gli utenti in un metodo di transizione delle funzionalità di selezione, la presenza per un utente è coerente indipendentemente dal client usato dall'altro utente. Se l'utente è in una delle modalità Skype for Business, tutti gli altri utenti vedono la presenza in base all'attività dell'utente in Skype for Business. Analogamente, se un utente è in modalità TeamsOnly, tutti gli altri utenti vedono la presenza in base all'attività dell'utente in Teams. Per informazioni dettagliate, vedere [Presenza](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence).

Per un'organizzazione che non ha ancora iniziato a usare Teams, l'amministratore deve cambiare la modalità a livello di tenant da Isole a SfbWithTeamsCollab. Per le organizzazioni che hanno già un utilizzo di Teams, l'amministratore deve "nonno" gli utenti già attivi in Teams per assicurarsi che questa modifica non sia applicabile. Per informazioni dettagliate, vedere [Metodo di selezione delle funzionalità per un'organizzazione](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)che usa già Teams in modalità Isole. 

Le esperienze utente guest saranno conformi alla modalità di coesistenza assegnata al tenant. Se si imposta una modalità Skype for Business a livello di tenant, gli ospiti non possono chattare, chiamare o mostrare la loro presenza. Per altre informazioni, vedere [Accesso guest in Teams](guest-access.md).

Quando la modalità cambia da Isole a SfbWithTeamsCollab, un utente che non ha mai usato Teams non vede alcuna differenza nel modo in cui usa Skype for Business. Tuttavia, se l'utente iniziasse a usare Teams, verrebbe esposto solo a funzionalità come Teams & Channel e Files. La chat, le chiamate e la pianificazione delle riunioni non sarebbero disponibili in Teams, perché l'amministratore ha (per ora) designato Skype for Business come client desiderato per queste funzioni.

> [!NOTE]
> Quando l'utente A cambia da Isole a una delle modalità Skype for Business, il client Teams di qualsiasi altro utente che comunica con l'Utente A deve sapere che la modalità dell'utente A è cambiata in modo da poter instradare la comunicazione al client appropriato per l'Utente A. Per tutti gli utenti che hanno già stabilito chat native di Teams-to-Teams con l'Utente A, possono essere necessario fino a 36 ore perché i client di Teams di questi altri utenti siano a conoscenza del cambio di modalità da Isole a qualsiasi modalità Skype for Business. Al contrario, le modifiche apportate da un utente esistente alla modalità TeamsOnly vengono individuate da altri client entro 2 ore.<br>
> Quando gli amministratori sono pronti, possono spostare la chat, le chiamate e la pianificazione delle riunioni per un determinato utente in Teams contemporaneamente aggiornando la modalità dell'utente a TeamsOnly.

In alternativa, l'amministratore può prima spostare solo la pianificazione delle riunioni in Teams, lasciando le funzioni di chat e chiamate in Skype for Business usando la modalità SfBWithTeamsCollabAndMeetings. Questa modalità consente alle organizzazioni di passare a Teams per le riunioni, se gli utenti non sono ancora pronti per passare alla modalità TeamsOnly, ad esempio se non si è ancora pronti per eseguire la migrazione delle funzionalità PSTN esistenti. Questo scenario di transizione è denominato [Riunioni per prime.](meetings-first.md)


|Esperienza di Teams  |In modalità SfBWithTeamsCollab |In modalità SfBWithTeamsCollabAndMeetings |In modalità TeamsOnly  |
|---------|---------|---------|---------|
|Le chat in arrivo e le chiamate VOIP degli utenti dell'organizzazione hanno ricevuto in:     | Skype for Business        | Skype for Business       | Teams        |
|Chiamate PSTN ricevute in:     | Skype for Business        |Skype for Business         | Teams        |
|Icone di presenza     | Skype for Business        |Skype for Business         | Teams        |
|Pianificazione riunione     | Skype for Business         | Teams        | Teams        |


La tabella seguente riepiloga i vantaggi e i vantaggi dell'uso delle modalità Skype for Business come passaggio di transizione verso la modalità TeamsOnly.

| Professionisti     |       Contro |
| :------------------ | :---------------- |
| Routing prevedibile per l'utente finale. Tutte le chiamate e le chat vengono effettuate in Skype for Business o Teams (ma non in entrambe), in base alla selezione dell'amministratore.|Le conversazioni di interoperabilità non supportano il formato RTF, la condivisione di file e la condivisione dello schermo. Questo può essere utilizzato per sfruttare la funzionalità Riunione ora per avviare una riunione. |
|Può ridurre la confusione degli utenti finali perché una determinata funzionalità è disponibile solo in un client. | Prima dell'aggiornamento a TeamsOnly, gli utenti non hanno accesso a Teams per le attività comuni eseguite in Skype for Business, ad esempio chat e chiamate. Significato, nessuna funzionalità affiancata.|
|L'amministratore ha il controllo sul set di funzionalità disponibili per gli utenti durante la transizione da Skype for Business a Teams. Questo controllo include la possibilità di introdurre in modo incrementale le funzionalità di Teams. | |
| Consente a un'organizzazione di usare Teams per le riunioni, anche se non è ancora pronto per passare completamente alla modalità TeamsOnly.||
|La presenza di un determinato utente come visualizzato da altri utenti è la stessa, indipendentemente dal client che usa.||

## <a name="summary-of-upgrade-methods"></a>Riepilogo dei metodi di aggiornamento
La tabella seguente riepiloga i metodi di aggiornamento:


|Funzionalità sovrapposte (con la modalità Isole)  |Funzionalità selezionate (con le modalità Skype for Business)  |
|---------|---------|
|Prima di essere aggiornati a TeamsOnly, gli utenti devono eseguire entrambi i client contemporaneamente, perché le chat e le chiamate in arrivo possono essere effettuate in entrambi i client.     | Le chat e le chiamate vengono effettuate solo in un client, in base alla modalità del destinatario. Gli utenti non aggiornati possono eseguire entrambi i client, ma non ci sono sovrapposizioni funzionali (le chiamate e le chat non sono disponibili in Teams). Gli amministratori possono anche controllare se gli utenti pianificano riunioni in Teams o Skype for Business.         |
|Consente agli amministratori di introdurre funzionalità sovrapposte (chat, riunioni, chiamate VOIP) sia in Skype for Business che in Teams agli utenti finali (consentendo funzionalità affiancate), nonché nuove funzionalità (Teams e Canali) in Teams.     | Consente agli amministratori di introdurre funzionalità selezionate di Teams agli utenti finali (Teams e Canali), senza fornire le stesse funzionalità disponibili anche in Skype for Business.        |
|L'interoperabilità tra Skype for Business e Teams non esiste mentre entrambi gli utenti sono in modalità Isole. Dopo l'aggiornamento di alcuni utenti a TeamsSolo può verificarsi una conversazione di interoperabilità tra tali utenti e altri utenti che sono ancora in modalità Isole. Tuttavia, gli utenti delle Isole potevano scegliere di usare Teams ed evitare la conversazione di interoperabilità.      |L'interoperabilità è necessaria per le comunicazioni tra utenti di Skype for Business e Teams.         |

> [!NOTE]
> Se non si riesce a seguire i metodi supportati per la migrazione degli utenti di Skype for Business Server a Teams, è possibile eseguire la transizione degli utenti a Teams rimuovendo Skype for Business Server e tutti gli attributi utente correlati in Active Directory. Dopo che gli attributi di Azure Active Directory degli utenti sono stati cancellati dagli attributi di Skype for Business Server e i record DNS sono stati ri-puntati a Microsoft 365 o Office 365, sarà quindi possibile ottenere una licenza per gli utenti in Microsoft 365 o Office 365 e aggiornarli a Teams. 

> [!IMPORTANT]
> Con la migrazione completa, i dati dei contatti e delle riunioni non verranno migrati dall'ambiente locale a Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Punto di decisione</td><td><ul> Quale percorso di aggiornamento è adatto ai requisiti aziendali dell'organizzazione?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Passaggio successivo</td><td><ul> L'identificazione del modello di distribuzione corrente, degli scenari dei casi di utilizzo e delle considerazioni chiave per l'organizzazione informerà il percorso verso Teams più adatto all'organizzazione.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Punto di decisione</td><td><ul> Quale scenario di aggiornamento è applicabile all'organizzazione?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul> Decidere la sequenza temporale del percorso di aggiornamento dell'organizzazione in base ai requisiti aziendali di messaggistica, riunioni e chiamate.<br><br> Decidere il lavoro aggiuntivo necessario per completare il percorso di aggiornamento.<br><br></ul></td></tr>
</table>

Dopo aver scelto il percorso di aggiornamento migliore per l'organizzazione, [eseguire l'aggiornamento a Teams.](./upgrade-to-teams.md)

## <a name="related-links"></a>Collegamenti correlati

[Guida alla migrazione e all'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true)

[Uso del servizio di migrazione delle riunioni (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)