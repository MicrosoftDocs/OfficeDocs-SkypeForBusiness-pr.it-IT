---
title: Eseguire l'aggiornamento a Teams da una distribuzione locale di Skype for Business - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc8afc48db6264cef5c5ad959f33dd7e738e116
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515793"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>Metodi di aggiornamento &mdash; per gli amministratori IT

Questo articolo descrive i metodi di aggiornamento per la migrazione a Teams. Questo articolo è il secondo di diversi articoli che descrivono i concetti e l'implementazione dell'aggiornamento per gli amministratori IT.  

- [Panoramica](upgrade-to-teams-on-prem-overview.md)
- **Metodi di aggiornamento** (questo articolo)
- [Strumenti per la gestione dell'aggiornamento](upgrade-to-teams-on-prem-tools.md)
- [Considerazioni aggiuntive per le organizzazioni con Skype for Business locale](upgrade-to-teams-on-prem-considerations.md)
- [Implementazione dell'aggiornamento](upgrade-to-teams-on-prem-implement.md)
- [Considerazioni sulla rete PSTN (Public Switched Telephone Network)](upgrade-to-teams-on-prem-pstn-considerations.md)

Gli articoli seguenti descrivono inoltre concetti importanti sull'aggiornamento e comportamenti di coesistenza:

- [Coesistenza di Teams e Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>Metodi di aggiornamento

Esistono due metodi per aggiornare a Teams un'organizzazione esistente con Skype for Business (online o locale): il metodo delle funzionalità sovrapposte e il metodo delle funzionalità di selezione. Questo articolo aiuta a scegliere il metodo più appropriato per l'organizzazione, descrivendo entrambi i metodi e presentando i vantaggi e i vantaggi di ognuno. 

- [Metodo di funzionalità di sovrapposizione (uso della modalità Isole)](#overlapping-capabilities-method-using-islands-mode)

   Gli utenti di un'organizzazione esistente di Skype for Business vengono introdotti in Teams in modo che possano usare entrambi i client durante una fase di transizione. Durante questo periodo, la maggior parte delle funzionalità di Teams, ma non tutte, è disponibile. Questa modalità per questa configurazione si parla di Isole, ed è la modalità predefinita per qualsiasi organizzazione esistente con Skype for Business. Una volta che l'organizzazione è pronta, l'amministratore sposta gli utenti in modalità TeamsOnly.

- [Metodo di selezione delle funzionalità (utilizzando una o più modalità di Skype for Business)](#select-capabilities-method-using-skype-for-business-modes)

   L'amministratore gestisce la transizione (da Skype for Business a Teams) delle funzionalità di chat, chiamate e pianificazione delle riunioni per gli utenti dell'organizzazione.  Ognuna di queste funzioni è disponibile in Skype for Business o Teams, ma non in entrambe. Gli amministratori usano TeamsUpgradePolicy per controllare quando spostare questa funzionalità in Teams per gli utenti. Gli utenti che non sono ancora in modalità TeamsOnly continuano a usare Skype for Business per chat e chiamate e i due set di utenti possono comunicare tramite funzionalità di interoperabilità. Gli amministratori gestiscono la transizione progressivamente eseguendo la migrazione di più utenti in modalità TeamsOnly.  

Dopo aver compreso e scelto il metodo di aggiornamento, è possibile ottenere informazioni sugli strumenti per gestire [l'aggiornamento a Teams dell'organizzazione.](upgrade-to-teams-on-prem-tools.md)

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Metodo di funzionalità di sovrapposizione (uso della modalità Isole)

Con il metodo delle funzionalità sovrapposte, gli utenti possono usare sia Teams che i client skype for Business per chat, chiamate VoIP e riunioni. Questo stato viene definito modalità "Isole" perché il traffico di comunicazione per Skype for Business e Teams rimane separato (anche per lo stesso utente) e i due client diversi non comunicano mai tra loro (per gli utenti all'interno della stessa organizzazione). Ad esempio, si supponga che l'utente A del destinatario sia in modalità Isole:

- Le comunicazioni avviate dal client Skype for Business di un altro utente verranno sempre provenienti dal client Skype for Business dell'Utente A.

- Le comunicazioni avviate dal client Teams di un altro utente verranno sempre provenienti dal client Teams dell'utente A, se l'altro utente *fa parte della stessa organizzazione.* 

- Le comunicazioni avviate dal client Teams di un altro utente verranno sempre visualizzate nel client Skype for Business dell'utente A, se l'altro utente fa parte *di un'organizzazione federata.*

La modalità Isole è la modalità predefinita di TeamsUpgradePolicy per qualsiasi organizzazione esistente che non abbia ancora eseguito l'aggiornamento a TeamsOnly. Quando si assegna una licenza di Microsoft 365 o Office 365, le licenze di Teams e Skype for Business online vengono assegnate per impostazione predefinita. Questo vale anche se l'utente è ospitata in locale in Skype for Business Server. Sia che l'utente sia ospitata in locale o online, lasciare abilitata la licenza di Skype for Business Online, perché è attualmente necessaria per le funzionalità complete di Teams. Infatti, se non è stata eseguita alcuna procedura per modificare la configurazione predefinita, è possibile che si abbia già un uso significativo di Teams nell'organizzazione.  Questo è uno dei vantaggi dell'approccio con funzionalità sovrapposte. Permette un'adozione rapida e basata sull'utente finale all'interno di un'organizzazione.

Per un funzionamento efficace di questo metodo, è necessario che tutti gli utenti eseeseguono entrambi i client contemporaneamente. Le chat e le chiamate in arrivo dall'interno dell'organizzazione a un utente in modalità Isole possono essere effettuate nel client Skype for Business o Teams e questo non è sotto il controllo del destinatario. Se il mittente e il destinatario sono nella stessa organizzazione, dipende dal client utilizzato dal mittente per avviare la comunicazione. Se il mittente e il destinatario sono in organizzazioni diverse, le chiamate e le chat in arrivo verso un utente in modalità Isole vengono sempre verso il client Skype for Business.  

Ad esempio, se un destinatario in modalità Isole esegue Skype for Business ma non Teams e qualcuno nella stessa organizzazione lo invia messaggi da Teams, il destinatario in modalità Isole non vede il messaggio (ma alla fine riceverà un messaggio e-mail che indica che ha perso un messaggio in Teams). Allo stesso modo, se un utente esegue Teams ma non Skype for Business e qualcuno riceve messaggi da Skype for Business, l'utente non vede quella chat.  Il destinatario riceverà un messaggio di posta elettronica che indica che si è perso un messaggio. Il comportamento in ognuno di questi casi è simile per le chiamate. Se gli utenti non eseguono entrambi i client, può facilmente causare frustrazione.

Quando l'Utente A è in modalità Isole, la presenza dell'utente A, così come è stata vista da altri utenti in Teams e in Skype for Business, è indipendente:

- Gli altri utenti, quando usano Teams, visualizzano la presenza in base all'attività dell'utente A in Teams. 
- Gli altri utenti, quando usano Skype for Business, visualizzano la presenza in base all'attività dell'utente A in Skype for Business. 

Questo significa che gli altri utenti potrebbero vedere stati presenza diversi per l'Utente A, a seconda del client che usano. Per altre informazioni, vedere [Presenza.](upgrade-to-teams-on-prem-coexistence.md#presence)

Quando si è pronti per aggiornare gli utenti alla modalità TeamsOnly, è possibile aggiornare gli utenti singolarmente oppure contemporaneamente l'intero tenant usando i criteri a livello di tenant. Dopo l'aggiornamento alla modalità TeamsOnly, un utente riceve tutte le chat e le chiamate in arrivo in Teams. La migrazione delle riunioni di Skype for Business alle riunioni di Teams viene attivata solo quando si applica TeamsUpgradePolicy ai singoli utenti, non per singoli tenant. Per [informazioni dettagliate, vedere](upgrade-to-teams-on-prem-tools.md#meeting-migration) Migrazione riunioni.

Tuttavia, i destinatari non aggiornati in modalità Isole possono continuare a ricevere chat e chiamate da un utente TeamsOnly nei client Skype for Business o Teams.  Ciò è dovuto al fatto che il client Teams mantiene thread di conversazione separati per le comunicazioni teams-to-teams e Teams-to-Skype for Business, anche per lo stesso utente.  Vedere Le conversazioni [di Teams : interoperabilità e thread nativi.](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads)  Ad esempio, si supponga che l'utente isole A usi Teams per inviare a Teams solo l'utente B. Quando l'Utente B risponde a quella chat, la comunicazione viene sul client Teams dell'utente A. Ora presuppongono che l'utente A usi il client Skype for Business per inviare a Teams solo l'utente B. L'utente B riceverà la chat in Teams, ma si tratta di una conversazione separata nel client Teams dell'utente B rispetto all'altra conversazione. Se l'Utente B risponde a questa conversazione con l'Utente A, verrà visualizzato nel client Skype for Business dell'Utente A. 

La tabella seguente riepiloga l'esperienza di Teams sia per la modalità Isole che per la modalità TeamsOnly:  

| Esperienza in Teams | In modalità Isole | In modalità TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chat e chiamate in arrivo ricevute in:|  Teams o Skype for Business | Teams |
| Chiamate PSTN ricevute in: | Skype for Business <br>L'uso della funzionalità PSTN in Teams non è supportato nella modalità Isole.    | Teams |   
 |Icone di presenza  | La presenza in Skype for Business e Teams è indipendente. Gli utenti possono visualizzare stati diversi per lo stesso utente di isole, a seconda del client che usano. | La presenza si basa esclusivamente sull'attività dell'utente in Teams. Tutti gli altri utenti, indipendentemente dal client che usano, possono vedere tale presenza. | 
 | Pianificazione di riunioni   | Per impostazione predefinita, gli utenti possono pianificare riunioni in Teams o Skype for Business. Verranno visualizzati entrambi i componenti aggiuntivi in Outlook. |   Gli utenti pianificano solo riunioni in Teams. Solo il componente aggiuntivo di Teams è disponibile in Outlook. | 

La tabella seguente riepiloga i vantaggi e i vantaggi dell'uso del metodo di sovrapposizione delle funzionalità per eseguire la migrazione dell'organizzazione a Teams.

| Professionisti     |       Contro |
| :------------------ | :---------------- |
| Consente un'adozione rapida all'interno di un'organizzazione.| Possibilità di confusione per gli utenti finali perché sono presenti due client con funzionalità simili, ma interfacce utente diverse. Inoltre, non hanno alcun controllo su quale client vengono effettuate le chat/chiamate in arrivo. |
| Consente agli utenti di imparare e acquisire familiarità con Teams pur avendo accesso completo a Skype for Business. | Potenziale insoddisfazione dell'utente finale a causa di messaggi persi se l'utente non esegue entrambi i client. Gli utenti possono lamentarsi di non ricevere messaggi.|
| Attività amministrative minime per iniziare a usare Teams. | Può essere difficile uscire dalla modalità Isole e passare alla modalità TeamsOnly se non tutti gli utenti dell'organizzazione usano Teams, soprattutto se non tutti gli utenti sono attivi in Teams. Ad esempio, dopo l'aggiornamento di un sottoinsieme di utenti alla modalità TeamsOnly, tali utenti inviano solo in Teams. Per il resto della popolazione in modalità Isole, questi messaggi verranno sempre inviati a Teams. Ma se alcuni utenti non eseguono Teams, percepiranno questi messaggi come non letti. |
|  | Quando si usa Teams, gli utenti che dispongono di un account locale in Skype for Business Server non hanno supporto di interoperabilità o federazione.  Questo potrebbe creare confusione nel caso di un mix di utenti di isole, alcuni ospitati in Skype for Business online e altri in Skype for Business locale.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Metodo di selezione delle funzionalità (utilizzo delle modalità Skype for Business)

Alcune organizzazioni potrebbero preferire offrire agli utenti finali un'esperienza più semplice e prevedibile durante il passaggio da Skype for Business a Teams. In questo modello, gli amministratori IT usano una delle modalità di Skype for Business in TeamsUpgradePolicy per designare esplicitamente quali utenti rimangono in Skype for Business prima di eseguire la migrazione alla modalità TeamsOnly. Quando sono pronti a spostare gli utenti selezionati in modalità TeamsOnly, l'amministratore aggiorna la modalità per tali utenti a TeamsOnly. Con l'avanzamento della distribuzione, sempre più utenti passano dalla modalità Skype for Business alla modalità TeamsOnly.  Durante la transizione:

- Gli utenti che utilizzano ancora Skype for Business ricevono tutte le chat e le chiamate in arrivo nel client Skype for Business, indipendentemente dal fatto che la comunicazione sia stata originata dal client Teams dell'altro utente o Skype for Business. Inoltre, per questi utenti Skype for Business, le funzionalità di chiamata e chat nel client Teams sono disabilitate per evitare confusione degli utenti finali e per garantire un routing corretto. 

- Gli utenti in modalità TeamsOnly ricevono tutte le chat e le chiamate in arrivo nel client Teams, indipendentemente dall'origine della comunicazione: Teams, Skype for Business o qualsiasi tipo di utente federato. 

A differenza del metodo Isole, nel metodo delle funzionalità di selezione, gli utenti di Skype for Business e gli utenti TeamsOnly possono comunicare tra loro. La comunicazione tra un utente Skype for Business e un utente teams è nota come interoperabilità o "interoperabilità". La comunicazione interoperabilità è possibile uno-a-uno per chat e chiamate tra un utente in Skype for Business e un altro utente in Teams; Tuttavia, alcune funzionalità avanzate potrebbero non essere disponibili. Vedere [interoperabilità.](upgrade-to-teams-on-prem-coexistence.md#interoperability) Inoltre, gli utenti invitati possono sempre partecipare a una riunione Skype for Business o Teams, tuttavia devono utilizzare un client corrispondente al tipo di riunione. Per altre informazioni, vedere [Riunioni.](upgrade-to-teams-on-prem-coexistence.md#meetings)

Poiché gli utenti di una transizione con funzionalità di selezione in genere non sono in modalità Isole, la presenza per un utente è coerente indipendentemente dal client usato dall'altro utente. Se l'utente è in una delle modalità Skype for Business, tutti gli altri utenti visualizzano la presenza in base all'attività dell'utente in Skype for Business. Allo stesso modo, se un utente è in modalità TeamsOnly, tutti gli altri utenti vedono la presenza in base all'attività dell'utente in Teams. Per informazioni dettagliate, vedere [Presenza.](upgrade-to-teams-on-prem-coexistence.md#presence)

Per un'organizzazione che non ha ancora iniziato a usare Teams, l'amministratore deve modificare la modalità a livello di tenant da Isole a SfbWithTeamsCollab. (Per le organizzazioni che hanno già un utilizzo di Teams, l'amministratore deve "avere" utenti già attivi in Teams per assicurarsi che questa modifica non sia applicabile. Per informazioni dettagliate, vedere un metodo di selezione delle funzionalità per [un'organizzazione](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)che usa già Teams in modalità Isole.

Quando la modalità cambia da Isole a SfbWithTeamsCollab, un utente che non ha mai usato Teams non avrà alcuna differenza nel modo in cui usa Skype for Business. Tuttavia, se un utente iniziasse a usare Teams, verrebbe esposto solo a funzionalità come Teams & Channel e File. Le chat, le chiamate e la pianificazione delle riunioni non sono disponibili in Teams, perché l'amministratore ha (per ora) designato Skype for Business come client desiderato per queste funzioni.  

Nota: quando l'utente A cambia modalità da Isole a una delle modalità Skype for Business, il client Teams di qualsiasi altro utente che comunica con l'Utente A deve sapere che la modalità dell'utente A è cambiata in modo da poter instradare la comunicazione al client appropriato per l'Utente A.  Per tutti gli utenti che hanno già stabilito chat native Teams su Teams con l'Utente A, possono essere necessario fino a 36 ore prima che i client Teams di questi altri utenti siano a conoscenza del cambiamento di modalità da Isole a qualsiasi modalità Skype for Business.   Al contrario, le modifiche apportate da un utente esistente alla modalità TeamsOnly vengono rilevate da altri client entro 2 ore.

Quando gli amministratori sono pronti, possono spostare la chat, le chiamate e la pianificazione delle riunioni per un determinato utente in Teams in una sola volta aggiornando la modalità dell'utente a TeamsOnly.  

In alternativa, l'amministratore può spostare in Teams solo la pianificazione delle riunioni, lasciando la chat e chiamando le funzioni in Skype for Business usando la modalità SfBWithTeamsCollabAndMeetings. Questa modalità consente alle organizzazioni di passare a Teams per le riunioni, se gli utenti non sono ancora pronti a passare alla modalità TeamsOnly (in genere, perché potrebbe essere necessario più tempo per eseguire la migrazione delle funzionalità PSTN esistenti). Questo scenario di transizione si parla di [prima](meetings-first.md)riunione.

La tabella seguente riepiloga i vantaggi e i vantaggi dell'uso delle modalità Skype for Business come passaggio di transizione verso la modalità TeamsOnly.


| Professionisti     |       Contro |
| :------------------ | :---------------- |
| Routing prevedibile per l'utente finale.  Tutte le chiamate e le chat vengono effettuate in Skype for Business o Teams (ma non in entrambi), in base alla selezione dell'amministratore.  | Le conversazioni di interoperabilità non supportano il formato RTF, la condivisione di file e la condivisione dello schermo.  Si tratta di una soluzione per le riunioni su richiesta, ma non è un'operazione semplice.  |
| Eliminare la confusione degli utenti finali perché una determinata funzionalità è disponibile solo in un client.  | Gli utenti non possono provare entrambi i client affiancati per lo stesso set di funzionalità. Questo può essere in particolare un fattore se gli utenti percepiscono il passaggio da Skype for Business a Teams come un cambiamento di principale cambio di paradigma. |
| Consente un'introduzione incrementale di Teams.  |  | |
| L'amministratore ha il controllo completo della transizione da Skype for Business a Teams. |  | | 
| Consente a un'organizzazione di usare Teams per le riunioni, anche se non è ancora ancora pronto per essere spostato completamente in modalità TeamsOnly. |  | |
| La presenza di un determinato utente come visualizzato da altri è la stessa, indipendentemente dal client che usano.  |  | |

## <a name="summary-of-upgrade-methods"></a>Riepilogo dei metodi di aggiornamento

La tabella seguente riepiloga i metodi di aggiornamento:

| Funzionalità di sovrapposizione (con la modalità Isole)     |      Funzionalità di selezione (utilizzando le modalità Skype for Business) |
| :------------------ | :---------------- |
| Prima di essere aggiornati a TeamsOnly, gli utenti devono eseguire entrambi i client contemporaneamente, perché le chat e le chiamate in arrivo potrebbero essere in entrambi i client.   | Le chat e le chiamate vengono effettuate su un solo client, in base alla modalità del destinatario. Gli utenti non aggiornati possono eseguire entrambi i client, ma non esiste alcuna sovrapposizione funzionale (le chiamate e le chat non sono disponibili in Teams).  Gli amministratori possono anche controllare se gli utenti pianificano riunioni in Teams o Skype for Business.   |
| Gli utenti possono usare Skype for Business e Teams affiancati per ottenere le stesse funzionalità.   | Consente agli amministratori di presentare nuove funzionalità nette di Teams agli utenti finali (team e canali), senza fornire le stesse funzionalità già presenti in Skype for Business.   |
|L'interoperabilità tra Skype for Business e Teams non esiste mentre entrambi gli utenti sono in modalità Isole. Dopo l'aggiornamento di alcuni utenti a TeamsOnly, può verificarsi una conversazione di interoperabilità tra tali utenti e altri utenti ancora in modalità Isole. Tuttavia, l'utente delle isole potrebbe scegliere di usare Teams ed evitare la conversazione di interoperabilità. | L'interoperabilità è necessaria per la comunicazione tra gli utenti di Skype for Business e Teams.   |


## <a name="related-links"></a>Collegamenti correlati

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio MMS (Meeting Migration Service)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

