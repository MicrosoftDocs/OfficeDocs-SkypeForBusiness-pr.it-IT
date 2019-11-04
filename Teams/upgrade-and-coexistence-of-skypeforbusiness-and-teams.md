---
title: Aggiornamento di Microsoft Teams da Skype for business | Modalità, coesistenza
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen, bjwhalen
description: Informazioni dettagliate sulle opzioni e le modalità di coesistenza di Skype for business e Microsoft teams e l'aggiornamento dei viaggi ai team da Skype for business con scenari di esempio.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5de243402cd5694b2e4a498f7ff7650cd8f49f4a
ms.sourcegitcommit: 2e005b335b1566c99b93fc311498702838466324
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2019
ms.locfileid: "37931644"
---
![Aggiornare il diagramma di viaggio, enfatizzando la fase di definizione del progetto](media/upgrade-banner-project-definition.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di definizione del progetto")

Questo articolo fa parte della fase di definizione del progetto del viaggio di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Elenco delle parti interessate del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità intesa di Skype for business e teams](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Scegliere il viaggio di aggiornamento da Skype for business a teams

Come cliente esistente di Skype for business, la transizione completa ai team può richiedere del tempo. Puoi tuttavia iniziare a realizzare il valore dei teams oggi, consentendo agli utenti di usare teams insieme a Skype for business. Poiché esistono alcune funzionalità sovrapposte tra le due app, è consigliabile esaminare le modalità di coesistenza e di aggiornamento disponibili per determinare il percorso appropriato per l'organizzazione. Ad esempio, è possibile scegliere di abilitare tutti i carichi di lavoro su entrambe le soluzioni senza interoperabilità. In alternativa, potresti decidere di gestire l'esperienza utente, introducendo gradualmente le funzionalità dei team o puntando su gruppi di utenti per le funzionalità di selezione, finché l'organizzazione non è pronta per aggiornare tutti i team. Usa il risultato del tuo pilota per valutare il viaggio di aggiornamento giusto per l'organizzazione.

> [!IMPORTANT]
> Skype for business online verrà ritirato il 31 luglio 2021, dopodiché non sarà più accessibile o supportato. Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti invitiamo a iniziare subito il tuo viaggio in Microsoft teams.

In questo articolo vengono illustrate le varie modalità che consentono di gestire quali modalità in Skype for business e teams sono disponibili per gli utenti. Come per qualsiasi distribuzione, ti consigliamo vivamente di [pilotare il piano previsto](pilot-essentials.md) con un gruppo selezionato di utenti prima di aggiornare l'organizzazione a teams. Tenere presente che l'introduzione di una nuova tecnologia può essere di disturbo per gli utenti. Richiedere tempo per valutare la disponibilità degli utenti e implementare un piano di comunicazione e formazione prima di implementare una delle modalità descritte in questo documento.

> [!TIP]
> Unisciti a noi per laboratori interattivi e dinamici in cui condivideremo le linee guida, le procedure consigliate e le risorse progettate per avviare la pianificazione e l'implementazione dell'aggiornamento.
>
>Prima di tutto, partecipa al piano della sessione di [aggiornamento](https://aka.ms/SkypeToTeamsPlanning) per iniziare.


## <a name="upgrade-journey-building-blocks"></a>Aggiornare i blocchi predefiniti di viaggio

Per preparare formalmente l'organizzazione per il viaggio in teams, è necessario avviare la pianificazione per gli scenari di aggiornamento che consentiranno alla tua organizzazione di accettare completamente i team come unica soluzione di comunicazione e collaborazione.

Per aiutare a guidare il processo decisionale, familiarizzare con le varie modalità, i concetti e la terminologia pertinenti per l'aggiornamento da Skype for business a teams. Per altre informazioni, vedere [coesistenza e interoperabilità di Microsoft teams e Skype for business](https://aka.ms/SkypeToTeams-Coexist)

Un utente che è stato migrato a teams non usa più un client Skype for business tranne che per partecipare a una riunione ospitata in Skype for business. Tutte le chat in arrivo e le chiamate atterrano nel client Teams dell'utente, indipendentemente dal fatto che il mittente usi team o Skype for business. Tutte le nuove riunioni organizzate dall'utente aggiornato verranno programmate come riunioni teams. Se l'utente tenta di usare il client Skype for business, l'avvio delle chat e delle chiamate è bloccato<sup>1</sup>. Tuttavia, l'utente può (e deve) ancora usare il client Skype for business per partecipare alle riunioni a cui sono state invitate.

Gli amministratori gestiscono la transizione a teams usando il concetto di [modalità](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes), che è una proprietà di [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Un utente che è stato migrato in teams come descritto in precedenza è in modalità "TeamsOnly". Per un'organizzazione che sta migrando a teams, l'obiettivo finale è quello di trasferire tutti gli utenti alla modalità TeamsOnly.

Esistono due metodi per la migrazione di un'organizzazione esistente con Skype for business (sia online che locale) per i team:

- **Metodo di funzionalità sovrapposte** (usando la modalità isole): gli utenti di un'organizzazione Skype for business esistenti vengono introdotti in teams in modo che possano usare entrambi i client affiancati durante una fase transitoria. Durante questo periodo, la maggior parte--ma non tutte--la funzionalità dei team è disponibile. La modalità per questa configurazione è denominata isole e questa è la modalità predefinita per qualsiasi organizzazione esistente con Skype for business. Quando l'organizzazione è pronta, l'amministratore sposta gli utenti in modalità TeamsOnly.
- **Selezionare metodo di funzionalità** (usando una o più modalità di Skype for business): l'amministratore gestisce la transizione (da Skype for business a teams) della chat, delle chiamate e della funzionalità di pianificazione delle riunioni per gli utenti dell'organizzazione. Ognuna di queste funzioni è disponibile sia in Skype for business che in teams, ma non in entrambi. Gli amministratori usano TeamsUpgradePolicy per controllare quando spostare questa funzionalità in teams per gli utenti. Gli utenti che non sono ancora in modalità TeamsOnly continuano a usare Skype for business per la chat e le chiamate e i due set di utenti possono comunicare tramite la funzionalità di interoperabilità. Gli amministratori gestiscono la transizione migrando progressivamente più utenti in modalità TeamsOnly.

<sup>1</sup> I client Skype for business meno recenti forniti prima di 2017 non onorano TeamsUpgradePolicy. Verificare di usare il client Skype for business più recente disponibile nel canale di Office.

Di seguito sono riportati i fattori chiave per determinare il percorso appropriato per l'organizzazione. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Metodo di funzionalità sovrapposte (utilizzo della modalità isole)

Con il metodo di funzionalità sovrapposte, gli utenti possono usare sia i team che i client Skype for business per la chat, le chiamate VoIP e le riunioni. In questo metodo, le chiamate chat e VOIP in teams sono focalizzate all'interno dell'organizzazione, mentre Skype for business consente la chat e le chiamate VOIP/PSTN con organizzazioni esterne (se configurate). Le riunioni possono essere pianificate e frequentate in entrambi i prodotti.

Quando si usa il metodo di funzionalità sovrapposte, il traffico delle comunicazioni per Skype for business e teams rimane separato (anche per lo stesso utente) e i due diversi client non comunicano mai tra loro (per gli utenti all'interno della stessa organizzazione). Le esperienze degli utenti si basano sulla configurazione del destinatario. Supponiamo ad esempio che l'utente destinatario A usi questo metodo di aggiornamento:

- Le comunicazioni avviate dal client Skype for business di un altro utente verranno sempre atterrate nel client Skype for business dell'utente.
- Le comunicazioni avviate dal client Teams da un *utente della stessa organizzazione* sbarcheranno sempre nel client teams di un utente.
- Le comunicazioni avviate dal client Teams da un *utente di un'organizzazione esterna* verranno sempre atterrate nel client Skype for business di un utente.

Se è stata assegnata una licenza di Office 365 agli utenti, questa sarà l'esperienza di aggiornamento predefinita per l'organizzazione. Quando si assegna una licenza di Office 365, le licenze di Skype for business online vengono assegnate per impostazione predefinita. <sup>2</sup>

Affinché questo metodo funzioni efficacemente, tutti gli utenti devono eseguire entrambi i client contemporaneamente. Le chat in arrivo e le chiamate dall'interno dell'organizzazione a un utente in modalità isole possono atterrare nel client Skype for business o teams e questo non è sotto il controllo del destinatario. Dipende dal client usato dal mittente per avviare la comunicazione. Se il mittente e il destinatario si trovano in organizzazioni diverse, le chiamate in arrivo e le chat di un utente in modalità isole atterrano sempre nel client Skype for business.

Ad esempio, se un destinatario in modalità isole ha eseguito l'accesso a Skype for business, ma non a teams, e qualcuno li invia tramite teams, il destinatario della modalità isole non vedrà il messaggio (ma alla fine riceverà un messaggio di posta elettronica che indica che non è stato ricevuto un SMS in teams). Allo stesso modo, se un utente ha in uso teams, ma non Skype for business, e i messaggi inviati dall'utente da Skype for business, l'utente non vedrà quella chat. Il comportamento in ognuno di questi casi è simile per la chiamata. Se gli utenti non eseguono entrambi i client, può facilmente comportare frustrazione.

La presenza funziona anche in modo indipendente tra teams e Skype for business usando questo metodo di aggiornamento. Questo significa che gli altri utenti possono visualizzare stati di presenza diversi per l'utente A, a seconda del client che usano. Per altre informazioni, Vedi [presenza](upgrade-to-Teams-on-prem-overview.md#presence).

- Altri utenti, quando usano teams, vedranno la presenza in base alle attività dell'utente in teams.
- Altri utenti, quando usano Skype for business, vedranno la presenza in base alle attività dell'utente in Skype for business.

Quando si è pronti per aggiornare gli utenti alla modalità TeamsOnly, è possibile aggiornare gli utenti singolarmente oppure è possibile aggiornare l'intero tenant in una sola volta usando il criterio a livello di tenant<sup>3</sup>. Quando un utente viene aggiornato alla modalità TeamsOnly, riceve tutte le chat in arrivo e le chiamate in teams.

Tuttavia, i destinatari non aggiornati in modalità isole possono continuare a ricevere chat e chiamate da un utente di TeamsOnly nei client Skype for business o teams. Per le conversazioni esistenti, l'utente di TeamsOnly risponderà al client in cui il mittente ha avviato la chat o la chiamata. 

Per le nuove conversazioni dal punto di vista dell'utente di TeamsOnly, la chat o la chiamata andranno sempre al client teams Mode Islands Users. Questo perché il client teams mantiene i thread di conversazione separati per le comunicazioni team-to-teams e teams-to-Skype for business, anche per lo stesso utente. Per altre informazioni, vedere [conversazioni in teams-interoperabilità rispetto ai thread nativi](upgrade-to-Teams-on-prem-overview.md#teams-conversations---interop-versus-native-threads).

La tabella seguente riepiloga l'esperienza dei team per la modalità Islands e TeamsOnly:

| Esperienza Teams | In modalità Isole | In modalità TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chat in arrivo e chiamate ricevute in:|  Teams o Skype for business | Team |
| Chiamate PSTN ricevute in: | Skype for business <br>L'uso della funzionalità PSTN in teams non è supportato in modalità Islands.    | Team |   
 |Presenza  | La presenza in Skype for business e teams è indipendente. Gli utenti possono visualizzare stati diversi per gli stessi utenti delle isole, a seconda del client che usano. | La presenza si basa esclusivamente sulle attività dell'utente in teams. Tutti gli altri utenti, indipendentemente dal client che usano, vedono quella presenza. | 
 | Pianificazione delle riunioni   | Gli utenti possono pianificare le riunioni in teams o in Skype for business. Vedranno entrambi i componenti aggiuntivi in Outlook. |   Gli utenti pianificano solo riunioni in teams. Solo il componente aggiuntivo teams è disponibile in Outlook. | 

La tabella seguente riepiloga i pro e i contro dell'uso del metodo di funzionalità sovrapposte per eseguire la migrazione dell'organizzazione a teams.

| I professionisti     |       Contro |
| :------------------ | :---------------- |
| Consente l'adozione rapida all'interno di un'organizzazione.| Possibilità di confusione degli utenti finali perché esistono due client con funzionalità simili, ma interfacce utente diverse. Inoltre, non hanno alcun controllo su quale client le chat in arrivo/chiamate atterrano. |
| Consente agli utenti di acquisire familiarità con i team e di avere ancora accesso completo a Skype for business. | Potenziale per l'insoddisfazione degli utenti finali a causa di messaggi mancanti se l'utente non ha eseguito entrambi i client.|
| Sforzo di amministrazione minimo per iniziare in teams. | Può essere difficile "uscire dalle isole" e passa alla modalità TeamsOnly se gli utenti e coloro con cui comunicano regolarmente non usano attivamente team.|
|Consente agli utenti di sfruttare le funzionalità per migliorare il lavoro di gruppo che non sono disponibili in Skype for business.| Un utente che usa Skype for business in locale e in teams non sarà in grado di comunicare da teams con un altro utente che usa Skype for business in locale, ma non ha team.  |

<sup>2</sup> Questo vale anche se l'utente è ospitato in locale in Skype for Business Server. Se l'utente è ospitato in locale o online, lascia la licenza di Skype for business online abilitata, perché è attualmente necessaria per la funzionalità completa di teams.

<sup>3</sup> Tieni presente che la migrazione delle riunioni di Skype for business alle riunioni di teams viene attivata solo quando applichi TeamsUpgradePolicy a singoli utenti, non in base al tenant. Per informazioni dettagliate, vedere [migrazione delle riunioni](upgrade-to-Teams-on-prem-overview.md#meeting-migration) .

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Metodo di selezione delle funzionalità (utilizzo delle modalità Skype for business)

Alcune organizzazioni preferiscono offrire agli utenti finali un'esperienza più prevedibile per le transizioni dell'organizzazione da Skype for business a teams. In questo modello gli amministratori IT usano una delle modalità Skype for business in TeamsUpgradePolicy per specificare in modo esplicito quali funzionalità restano in Skype for business prima di eseguire la migrazione alla modalità TeamsOnly. Dato che sono pronti a spostare le funzionalità selezionate in modalità TeamsOnly, l'amministratore aggiorna la modalità per gli utenti a TeamsOnly. Durante questa transizione:

- Gli amministratori hanno opzioni per abilitare determinate funzionalità di teams per gli utenti mantenendo le funzionalità di chat e chiamate in Skype for business prima che gli utenti si trasferiscino in TeamsOnly Experience. L'amministrazione può abilitare le funzionalità di collaborazione di teams o le riunioni teams + Collaboration.
- Gli utenti ancora in Skype for Business ricevono tutte le chat in arrivo e le chiamate nel client Skype for business, indipendentemente dal fatto che la comunicazione sia stata originata dai team di altri utenti o dal client Skype for business. Inoltre, per questi utenti di Skype for business, le funzionalità di chiamata e chat nel client teams sono disabilitate per impedire la confusione degli utenti finali e garantire il routing e la presenza corretti.
- Gli utenti in modalità TeamsOnly ricevono tutte le chat in arrivo e le chiamate nel client teams e la presenza è fornita da teams, indipendentemente da dove la comunicazione ha avuto origine da: teams, Skype for business o qualsiasi tipo di utente federato.

Diversamente dal metodo delle funzionalità sovrapposte, nel metodo Select capabilities gli utenti che usano Skype for business possono comunicare con gli utenti che si trovano in TeamsOnly. La comunicazione tra un utente di Skype for business e un utente di teams è nota come [interoperabilità](upgrade-to-Teams-on-prem-overview.md#interoperability) o "Interop". Le comunicazioni di interoperabilità sono possibili su base uno-a-uno per le chat e le chiamate tra un utente in Skype for business e un altro utente in teams. Inoltre, gli utenti invitati possono sempre partecipare a una riunione Skype for business o teams, ma devono usare un client che corrisponda al tipo di riunione. Per altre informazioni, vedere [riunioni](upgrade-to-Teams-on-prem-overview.md#meetings).

Per gli utenti in un metodo di selezione delle funzionalità, la presenza per un utente è coerente indipendentemente dal client usato dall'altro utente. Se l'utente si trova in una delle modalità Skype for business, tutti gli altri utenti vedranno la presenza in base alle attività dell'utente in Skype for business. Allo stesso modo, se un utente è in modalità TeamsOnly, tutti gli altri utenti vedranno la presenza in base alle attività dell'utente in teams. Per informazioni dettagliate, vedere [presenza](upgrade-to-Teams-on-prem-overview.md#presence).

Per un'organizzazione che ha scelto di seguire il metodo di selezione delle funzionalità, l'amministratore deve cambiare la modalità a livello di tenant da Islands alla modalità di coesistenza Skype for business appropriata (SfbWithTeamsCollab o SfBWithTeamsCollabAndMeetings).  

Le esperienze degli utenti Guest si atterranno alla modalità di coesistenza assegnata al tenant. Se si imposta una modalità Skype for business a livello di tenant, gli utenti non possono chattare, chiamare o mostrare la propria presenza. Per altre informazioni, vedere [Accesso guest in Teams](guest-access.md).

Quando la modalità cambia da Islands a SfbWithTeamsCollab, un utente che non ha mai usato teams vedrà nessuna differenza nel modo in cui usano Skype for business. Tuttavia, se l'utente inizia a usare teams, verrebbe esposto solo a funzionalità come team & canale e file. La chat, le chiamate e la pianificazione delle riunioni non sarebbero disponibili in teams, poiché l'amministratore ha (per ora) nominato Skype for business come client desiderato per tali funzioni.

> [!NOTE]
> Quando l'utente modifica le proprie isole in una delle modalità Skype for business, il client teams di qualsiasi altro utente che comunica con l'utente deve sapere che la modalità di un utente è cambiata in modo che possa instradare la comunicazione al client appropriato per l'utente A. Per tutti gli utenti che hanno già stabilito le chat di teams-to-teams native con l'utente A, può richiedere del tempo per i client di questi altri utenti di essere a conoscenza della modalità di modifica delle isole in qualsiasi modalità Skype for business. Quando gli amministratori sono pronti, possono spostare la chat, le chiamate e la pianificazione delle riunioni per un utente specifico in teams tutti insieme aggiornando la modalità dell'utente in TeamsOnly.

In alternativa, l'amministratore può prima di tutto spostare solo la pianificazione della riunione in teams, lasciando le funzioni di chat e chiamate in Skype for business usando la modalità SfBWithTeamsCollabAndMeetings. Questa modalità consente alle organizzazioni di passare ai team per le riunioni, se gli utenti non sono ancora pronti per il passaggio alla modalità TeamsOnly, ad esempio non si è ancora pronti per eseguire la migrazione delle funzionalità PSTN esistenti. Questo scenario di transizione viene indicato per [primo come riunioni](meetings-first.md).


|Esperienza Teams  |In modalità SfBWithTeamsCollab |In modalità SfBWithTeamsCollabAndMeetings |In modalità TeamsOnly  |
|---------|---------|---------|---------|
|Chat in arrivo e chiamate VOIP dagli utenti dell'organizzazione ricevute in:     | Skype for business        | Skype for business       | Team        |
|Chiamate PSTN ricevute in:     | Skype for business        |Skype for business         | Team        |
|Presenza     | Skype for business        |Skype for business         | Team        |
|Pianificazione delle riunioni     | Skype for business         | Team        | Team        |


La tabella seguente riepiloga i pro e i contro dell'uso delle modalità Skype for business come passaggio di transizione verso la modalità TeamsOnly.

| I professionisti     |       Contro |
| :------------------ | :---------------- |
| Routing prevedibile per l'utente finale. Tutte le chiamate e le chat si atterrano in Skype for business o in teams (ma non entrambe), in base alla selezione dell'amministratore.|Le conversazioni di interoperabilità mancano del supporto per RTF, condivisione di file e condivisione dello schermo. Questo problema può essere risolto sfruttando la funzionalità incontra ora per avviare una riunione. |
|Può ridurre la confusione degli utenti finali perché una determinata funzionalità è disponibile solo in un solo client. | Gli utenti non hanno accesso ai team per le attività comuni eseguite in Skype for business, come la chat e la chiamata prima dell'aggiornamento a TeamsOnly.|
|L'amministratore ha aumentato il controllo del set di funzionalità disponibili per gli utenti durante la transizione da Skype for business a teams. | |
| Consente a un'organizzazione di usare team per le riunioni, anche se non è ancora pronto per essere completamente in modalità TeamsOnly.||
|La presenza di un utente specifico visualizzato da altri è la stessa, indipendentemente dal client che usano.||

## <a name="summary-of-upgrade-methods"></a>Riepilogo dei metodi di aggiornamento
Nella tabella seguente vengono riepilogati i metodi di aggiornamento:


|Funzionalità sovrapposte (con la modalità isole)  |Funzionalità selezionate (con le modalità Skype for business)  |
|---------|---------|
|Prima di eseguire l'aggiornamento a TeamsOnly, è necessario che gli utenti eseguano entrambi i client contemporaneamente, poiché le chat in arrivo e le chiamate possono atterrare in entrambi i client.     | Chat e chiamate solo terra in un solo client, in base alla modalità del destinatario. Gli utenti non aggiornati possono eseguire entrambi i client, ma non sono presenti sovrapposizioni funzionali (le chiamate e le chat non sono disponibili in teams).         |
|Consente agli amministratori di introdurre funzionalità sovrapposte (chat, riunioni, chiamate VOIP) sia in Skype for business che in teams per gli utenti finali, nonché nuove funzionalità (team e canali) in teams.     | Consente agli amministratori di introdurre le funzionalità di selezione dei team per gli utenti finali (team e canali), senza fornire le stesse funzionalità che esistono anche in Skype for business.        |
|L'interoperabilità tra Skype for business e teams non esiste mentre entrambi gli utenti sono in modalità isole.      |L'interoperabilità è necessaria per la comunicazione tra Skype for business e gli utenti teams.         |

> [!NOTE]
> Se non si riesce a seguire i metodi supportati per la migrazione degli utenti di Skype for Business Server a teams, è possibile eseguire la transizione degli utenti a teams rimuovendo Skype for Business Server e tutti gli attributi utente correlati in Active Directory. Dopo che gli attributi di Azure Active Directory sono stati eliminati dagli attributi di Skype for Business Server e i record DNS sono stati ripuntati su Office 365, è possibile concedere la licenza agli utenti di Office 365 e aggiornarli a teams. 

> [!IMPORTANT]
> Con la migrazione completa, i dati di contatto e le riunioni non verranno migrati dall'ambiente locale a Microsoft teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Punto decisionale</td><td><ul> Quale viaggio di aggiornamento è adatto ai requisiti aziendali dell'organizzazione?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Passaggio successivo</td><td><ul> L'identificazione del modello di distribuzione corrente, l'uso di scenari di casi e le considerazioni chiave per l'organizzazione informano il viaggio ai team più adatti per l'organizzazione.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Punto decisionale</td><td><ul> Quale scenario di aggiornamento è applicabile all'organizzazione?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul> Decidi la sequenza temporale del viaggio di aggiornamento dell'organizzazione in base a messaggi, riunioni e requisiti aziendali per le chiamate.<br><br> Decidere il lavoro aggiuntivo necessario per completare il viaggio di aggiornamento.<br><br></ul></td></tr>
</table>

Dopo aver scelto il viaggio di aggiornamento migliore per l'organizzazione, [eseguire l'aggiornamento a teams](https://aka.ms/SkypeToTeams-Upgrade).
