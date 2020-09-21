---
title: Eseguire l'aggiornamento a teams da una distribuzione locale di Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
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
ms.openlocfilehash: 2a6c4fb2e2f6433b21972a3c5e5c324d0c3d78f3
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955942"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>Metodi &mdash; di aggiornamento per gli amministratori IT

Questo articolo descrive i metodi di aggiornamento per la migrazione a teams. Questo articolo è il secondo di diversi che descrivono i concetti di aggiornamento e l'implementazione per gli amministratori IT.  

- [Panoramica](upgrade-to-teams-on-prem-overview.md)
- **Metodi di aggiornamento** (questo articolo)
- [Strumenti per la gestione dell'aggiornamento](upgrade-to-teams-on-prem-tools.md)
- [Considerazioni aggiuntive per le organizzazioni con Skype for business locale](upgrade-to-teams-on-prem-considerations.md)
- [Implementazione dell'aggiornamento](upgrade-to-teams-on-prem-implement.md)
- [Considerazioni su PSTN (Public Switched Telephone Network)](upgrade-to-teams-on-prem-pstn-considerations.md)

Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:

- [Coesistenza di teams e Skype for business](upgrade-to-teams-on-prem-coexistence.md)
- [Modalità di coesistenza-riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>Metodi di aggiornamento

Esistono due metodi per aggiornare un'organizzazione esistente con Skype for business (sia online che locale) a teams: metodo di funzionalità sovrapposte e il metodo di selezione delle funzionalità. Questo articolo consente di scegliere il metodo giusto per l'organizzazione descrivendo entrambi i metodi e presentando i pro e i contro di ognuno di essi. 

- [Metodo di funzionalità sovrapposte (utilizzo della modalità isole)](#overlapping-capabilities-method-using-islands-mode)

   Gli utenti di un'organizzazione Skype for business esistenti vengono introdotti in teams in modo che possano usare entrambi i client durante una fase di transizione. Durante questo periodo, la maggior parte--ma non tutte--la funzionalità dei team è disponibile. La modalità per questa configurazione è denominata isole e questa è la modalità predefinita per qualsiasi organizzazione esistente con Skype for business. Quando l'organizzazione è pronta, l'amministratore sposta gli utenti in modalità TeamsOnly.

- [Selezionare il metodo capabilities (usando una o più modalità di Skype for business)](#select-capabilities-method-using-skype-for-business-modes)

   L'amministratore gestisce la transizione (da Skype for business a teams) della chat, delle chiamate e delle funzionalità di pianificazione delle riunioni per gli utenti dell'organizzazione.  Ognuna di queste funzioni è disponibile sia in Skype for business che in teams, ma non in entrambi. Gli amministratori usano TeamsUpgradePolicy per controllare quando spostare questa funzionalità in teams per gli utenti. Gli utenti che non sono ancora in modalità TeamsOnly continuano a usare Skype for business per la chat e le chiamate e i due set di utenti possono comunicare tramite la funzionalità di interoperabilità. Gli amministratori gestiscono la transizione migrando progressivamente più utenti in modalità TeamsOnly.  

Dopo aver compreso e scelto il metodo di aggiornamento, è possibile conoscere gli [strumenti per la gestione dell'aggiornamento dell'organizzazione ai team](upgrade-to-teams-on-prem-tools.md).

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Metodo di funzionalità sovrapposte (utilizzo della modalità isole)

Con il metodo di funzionalità sovrapposte, gli utenti possono usare sia i team che i client Skype for business per la chat, le chiamate VoIP e le riunioni. Questo stato si chiama modalità "isole" perché il traffico delle comunicazioni per Skype for business e teams rimane distinto (anche per lo stesso utente) e i due diversi client non comunicano mai tra loro (per gli utenti all'interno della stessa organizzazione). Supponiamo ad esempio che l'utente destinatario A sia in modalità isole:

- Le comunicazioni avviate dal client Skype for business di un altro utente verranno sempre atterrate nel client Skype for business dell'utente.

- Le comunicazioni avviate dal client teams di un altro utente saranno sempre presenti nel client teams di un utente, *se l'altro utente si trova nella stessa organizzazione*. 

- Le comunicazioni avviate dal client teams di un altro utente sbarcheranno sempre nel client Skype for business di un utente, *se l'altro utente si trova in un'organizzazione federata*.

La modalità Islands è la modalità predefinita di TeamsUpgradePolicy per qualsiasi organizzazione esistente che non sia ancora stata aggiornata a TeamsOnly. Quando si assegna una licenza Microsoft 365 o Office 365, per impostazione predefinita vengono assegnate entrambe le licenze teams e Skype for business online. (Questo vale anche se l'utente è ospitato in locale in Skype for Business Server. Se l'utente è ospitato in locale o online, lascia la licenza di Skype for business online abilitata, perché è attualmente necessaria per la funzionalità completa di teams. In realtà, se non hai adottato alcuna procedura per modificare la configurazione predefinita, potresti avere già un uso significativo dei team nell'organizzazione.  Questo è uno dei vantaggi dell'approccio delle funzionalità sovrapposte. Consente l'adozione rapida e guidata dall'utente finale all'interno di un'organizzazione.

Affinché questo metodo funzioni in modo efficace, è necessario che tutti gli utenti eseguano contemporaneamente entrambi i client. Le chat in arrivo e le chiamate dall'interno dell'organizzazione a un utente in modalità isole possono atterrare nel client Skype for business o teams e questo non è sotto il controllo del destinatario. Se il mittente e il destinatario si trovano nella stessa organizzazione, dipende dal client usato dal mittente per avviare la comunicazione. Se il mittente e il destinatario si trovano in organizzazioni diverse, le chiamate in arrivo e le chat di un utente in modalità isole atterrano sempre nel client Skype for business.  

Ad esempio, se un destinatario in modalità isole è in uso in Skype for business ma non in teams e qualcuno nella stessa organizzazione li invia tramite posta elettronica, il destinatario della modalità isole non vedrà il messaggio (ma alla fine riceverà un messaggio che indica che non è stato inviato in teams). Allo stesso modo, se un utente ha in uso teams, ma non Skype for business, e i messaggi inviati dall'utente da Skype for business, l'utente non vedrà quella chat.  Si riceverà un messaggio di posta elettronica che indica che è stato visualizzato uno stato. Il comportamento in ognuno di questi casi è simile per la chiamata. Se gli utenti non eseguono entrambi i client, può facilmente comportare frustrazione.

Quando l'utente A è in modalità isole, la presenza di un utente come visibile da altri utenti in teams e in Skype for business è indipendente:

- Altri utenti, quando usano teams, vedranno la presenza in base alle attività dell'utente in teams. 
- Altri utenti, quando usano Skype for business, vedranno la presenza in base alle attività dell'utente in Skype for business. 

Questo significa che gli altri utenti possono visualizzare stati di presenza diversi per l'utente A, a seconda del client che usano. Per altre informazioni, Vedi [presenza](upgrade-to-teams-on-prem-coexistence.md#presence).

Quando si è pronti per aggiornare gli utenti alla modalità TeamsOnly, è possibile aggiornare gli utenti singolarmente oppure è possibile aggiornare l'intero tenant in una sola volta usando i criteri a livello di tenant. Quando un utente viene aggiornato alla modalità TeamsOnly, riceve tutte le chat in arrivo e le chiamate in teams. Tieni presente che la migrazione delle riunioni di Skype for business alle riunioni di teams viene attivata solo quando applichi TeamsUpgradePolicy a singoli utenti, non in base a un tenant. Per informazioni dettagliate, vedere [migrazione delle riunioni](upgrade-to-teams-on-prem-tools.md#meeting-migration) .

Tuttavia, i destinatari non aggiornati in modalità isole possono continuare a ricevere chat e chiamate da un utente di TeamsOnly nei client Skype for business o teams.  Questo perché il client teams mantiene i thread di conversazione separati per le comunicazioni team-to-teams e teams-to-Skype for business, anche per lo stesso utente.  Vedere [conversazioni in teams-interoperabilità versus thread nativi](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads).  Supponiamo ad esempio che l'utente Islands a usi teams to Message TeamsOnly utente B. Quando l'utente B risponde alla chat, la comunicazione atterrerà nel client teams di un utente. Ora si presuppone che l'utente A usi il client Skype for business per inviare un messaggio a TeamsOnly utente b. l'utente B riceverà la chat in teams, ma questa sarà una conversazione separata nel client Teams dell'utente B rispetto all'altra conversazione. Se l'utente B risponde a questa conversazione con l'utente A, atterrerà nel client Skype for business di un utente. 

La tabella seguente riepiloga l'esperienza dei team per la modalità Islands e TeamsOnly:  

| Esperienza Teams | In modalità Isole | In modalità TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chat in arrivo e chiamate ricevute in:|  Teams o Skype for business | Team |
| Chiamate PSTN ricevute in: | Skype for Business <br>L'uso della funzionalità PSTN in teams non è supportato in modalità Islands.    | Team |   
 |Icone di presenza  | La presenza in Skype for business e teams è indipendente. Gli utenti possono visualizzare stati diversi per gli stessi utenti delle isole, a seconda del client che usano. | La presenza si basa esclusivamente sulle attività dell'utente in teams. Tutti gli altri utenti, indipendentemente dal client che usano, vedono quella presenza. | 
 | Pianificazione delle riunioni   | Per impostazione predefinita, gli utenti possono pianificare le riunioni in teams o in Skype for business. Vedranno entrambi i componenti aggiuntivi in Outlook. |   Gli utenti pianificano solo riunioni in teams. Solo il componente aggiuntivo teams è disponibile in Outlook. | 

La tabella seguente riepiloga i pro e i contro dell'uso del metodo di funzionalità sovrapposte per eseguire la migrazione dell'organizzazione a teams.

| I professionisti     |       Contro |
| :------------------ | :---------------- |
| Consente l'adozione rapida all'interno di un'organizzazione.| Possibilità di confusione per gli utenti finali perché esistono due client con funzionalità simili, ma interfacce utente diverse. Inoltre, non hanno alcun controllo su quale client le chat in arrivo/chiamate atterrano. |
| Consente agli utenti di acquisire familiarità con i team e di avere ancora accesso completo a Skype for business. | Possibilità di insoddisfazione degli utenti finali a causa di messaggi mancanti se l'utente non ha eseguito entrambi i client. Gli utenti potrebbero lamentarsi di non ricevere messaggi.|
| Sforzo di amministrazione minimo per iniziare in teams. | Può essere difficile "uscire dalle isole" e passa alla modalità TeamsOnly, se non tutti gli utenti dell'organizzazione usano team, specialmente se non tutti i partecipanti sono attivi in teams. Ad esempio, quando un sottoinsieme di utenti viene aggiornato alla modalità TeamsOnly, questi utenti invieranno solo in teams. Per il resto della popolazione in modalità isole, i messaggi verranno sempre sbarcati in teams. Ma se alcuni di questi utenti non eseguono Team, questi messaggi verranno percepiti come mancanti. |
|  | Quando si usano teams, gli utenti che hanno un account locale in Skype for Business Server non hanno supporto per l'interoperabilità o la Federazione.  Questo può potenzialmente creare confusione se si dispone di un mix di utenti di isole--alcuni residenti in Skype for business online e alcuni in Skype for business locale.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Metodo di selezione delle funzionalità (utilizzo delle modalità Skype for business)

Alcune organizzazioni preferiscono offrire agli utenti finali un'esperienza più semplice e prevedibile per le transizioni dell'organizzazione da Skype for business a teams. In questo modello gli amministratori IT usano una delle modalità Skype for business in TeamsUpgradePolicy per designare esplicitamente gli utenti rimasti in Skype for business prima di eseguire la migrazione alla modalità TeamsOnly. Dato che sono pronti a spostare gli utenti selezionati in modalità TeamsOnly, l'amministratore aggiorna la modalità per gli utenti a TeamsOnly. Man mano che la distribuzione avanza, sempre più utenti vengono trasferiti da Skype for business alla modalità TeamsOnly.  Durante questa transizione:

- Gli utenti ancora in Skype for Business ricevono tutte le chat in arrivo e le chiamate nel client Skype for business, indipendentemente dal fatto che la comunicazione sia stata originata dai team di altri utenti o dal client Skype for business. Inoltre, per questi utenti di Skype for business, le funzionalità di chiamata e chat nel client teams sono disabilitate per evitare confusione per gli utenti finali e per garantire un routing corretto. 

- Gli utenti in modalità TeamsOnly ricevono tutte le chat in arrivo e le chiamate nel client teams, indipendentemente da dove la comunicazione ha avuto origine da: teams, Skype for business o da qualsiasi tipo di utente federato. 

Diversamente dal metodo Islands, nel metodo Select capabilities gli utenti di Skype for business e gli utenti di TeamsOnly possono comunicare tra loro. La comunicazione tra un utente di Skype for business e un utente di teams è nota come interoperabilità o "Interop". La comunicazione interoperabilità è possibile su base uno-a-uno per le chat e le chiamate tra un utente in Skype for business e un altro utente in teams; alcune funzionalità avanzate potrebbero tuttavia non essere disponibili. (Vedi [interoperabilità](upgrade-to-teams-on-prem-coexistence.md#interoperability)) Inoltre, gli utenti invitati possono sempre partecipare a una riunione Skype for business o teams, ma devono usare un client che corrisponda al tipo di riunione. Per altre informazioni, vedere [riunioni](upgrade-to-teams-on-prem-coexistence.md#meetings).

Poiché gli utenti in una transizione di funzionalità di selezione non sono in genere in modalità isole, la presenza per un utente è coerente indipendentemente dal client usato dall'altro utente. Se l'utente si trova in una delle modalità Skype for business, tutti gli altri utenti vedranno la presenza in base alle attività dell'utente in Skype for business. Allo stesso modo, se un utente è in modalità TeamsOnly, tutti gli altri utenti vedranno la presenza in base alle attività dell'utente in teams. Per informazioni dettagliate, vedere [presenza](upgrade-to-teams-on-prem-coexistence.md#presence).

Per un'organizzazione che non ha ancora iniziato a usare teams, l'amministratore deve cambiare la modalità a livello di tenant da Islands a SfbWithTeamsCollab. (Per le organizzazioni che hanno già un certo utilizzo di teams, l'amministratore deve "nonno" gli utenti già attivi in teams per assicurarsi che questa modifica non sia applicabile. Per informazioni dettagliate, Vedi [un metodo di selezione delle funzionalità per un'organizzazione che usa già teams in modalità Islands](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode).

Quando la modalità cambia da Islands a SfbWithTeamsCollab, un utente che non ha mai usato teams vedrà nessuna differenza nel modo in cui usano Skype for business. Tuttavia, se l'utente inizia a usare teams, verrebbe esposto solo a funzionalità come team & canale e file. La chat, le chiamate e la pianificazione delle riunioni non sarebbero disponibili in teams, poiché l'amministratore ha (per ora) nominato Skype for business come client desiderato per tali funzioni.  

Nota: quando l'utente modifica le proprie isole in una delle modalità Skype for business, il client teams di qualsiasi altro utente che comunica con l'utente deve sapere che la modalità di un utente è cambiata in modo che possa instradare la comunicazione al client appropriato per l'utente A.  Per tutti gli utenti che hanno già creato chat di teams-to-teams native con l'utente A, possono essere necessarie fino a 36 ore per consentire ai clienti di questi altri utenti di essere a conoscenza della modalità di modifica delle isole in qualsiasi modalità Skype for business.   Al contrario, le modifiche apportate a un utente esistente in modalità TeamsOnly vengono scoperte da altri client entro 2 ore.

Quando gli amministratori sono pronti, possono spostare la chat, le chiamate e la pianificazione delle riunioni per un utente specifico in teams tutti insieme aggiornando la modalità dell'utente in TeamsOnly.  

In alternativa, l'amministratore può prima di tutto spostare solo la pianificazione della riunione in teams, lasciando le funzioni di chat e chiamate in Skype for business usando la modalità SfBWithTeamsCollabAndMeetings. Questa modalità consente alle organizzazioni di passare ai team per le riunioni, se gli utenti non sono ancora pronti per il passaggio alla modalità TeamsOnly (in genere perché potrebbe essere necessario più tempo per eseguire la migrazione delle funzionalità PSTN esistenti). Questo scenario di transizione viene indicato per [primo come riunioni](meetings-first.md).

La tabella seguente riepiloga i pro e i contro dell'uso delle modalità Skype for business come passaggio di transizione verso la modalità TeamsOnly.


| I professionisti     |       Contro |
| :------------------ | :---------------- |
| Routing prevedibile per l'utente finale.  Tutte le chiamate e le chat si atterrano in Skype for business o in teams (ma non entrambe), in base alla selezione dell'amministratore.  | Le conversazioni di interoperabilità mancano del supporto per RTF, condivisione di file e condivisione dello schermo.  Questo problema può essere risolto con riunioni su richiesta, ma non è così semplice.  |
| Eliminare la confusione degli utenti finali perché una determinata funzionalità è disponibile solo in un solo client.  | Gli utenti non possono provare entrambi i client affiancati per lo stesso set di funzionalità. Questo potrebbe essere un fattore particolare se gli utenti percepiscono il cambiamento da Skype for business a teams come un cambiamento di paradigma importante. |
| Consente l'introduzione incrementale di teams.  |  | |
| L'amministratore ha il pieno controllo della transizione da Skype for business a teams. |  | | 
| Consente a un'organizzazione di usare team per le riunioni, anche se non è ancora pronto per essere completamente in modalità TeamsOnly. |  | |
| La presenza di un utente specifico visualizzato da altri è la stessa, indipendentemente dal client che usano.  |  | |

## <a name="summary-of-upgrade-methods"></a>Riepilogo dei metodi di aggiornamento

Nella tabella seguente vengono riepilogati i metodi di aggiornamento:

| Funzionalità sovrapposte (con la modalità isole)     |      Selezionare funzionalità (con le modalità Skype for business) |
| :------------------ | :---------------- |
| Prima di eseguire l'aggiornamento a TeamsOnly, è necessario che gli utenti eseguano entrambi i client contemporaneamente, poiché le chat in arrivo e le chiamate possono atterrare in entrambi i client.   | Chat e chiamate solo terra in un solo client, in base alla modalità del destinatario. Gli utenti non aggiornati possono eseguire entrambi i client, ma non sono presenti sovrapposizioni funzionali (le chiamate e le chat non sono disponibili in teams).  Gli amministratori possono anche controllare se gli utenti pianificano riunioni in teams o Skype for business.   |
| Gli utenti possono usare Skype for business e team affiancati per la stessa funzionalità.   | Consente agli amministratori di introdurre nuove funzionalità nette di teams per gli utenti finali (team e canali), senza fornire le stesse funzionalità che esistono anche in Skype for business.   |
|L'interoperabilità tra Skype for business e teams non esiste mentre entrambi gli utenti sono in modalità isole. Dopo l'aggiornamento di alcuni utenti a TeamsOnly, la conversazione di interoperabilità può essere eseguita tra gli utenti e gli altri utenti ancora in modalità isole. Tuttavia, l'utente Islands può scegliere di usare teams ed evitare la conversazione di interoperabilità. | L'interoperabilità è necessaria per la comunicazione tra Skype for business e gli utenti teams.   |


## <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

