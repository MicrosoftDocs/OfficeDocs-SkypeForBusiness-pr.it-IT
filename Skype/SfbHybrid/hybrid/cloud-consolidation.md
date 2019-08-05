---
title: Consolidamento cloud per Teams e Skype for business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questo articolo descrive come ottenere il consolidamento per le organizzazioni con distribuzioni locali di Skype for business (o Lync) che vogliono trasferirsi per trasferire il carico di lavoro UC in teams e/o Skype for business online.
ms.openlocfilehash: 46e84f9a65ec7626c5285196af83d63baa46c15e
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2019
ms.locfileid: "36185558"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidamento cloud per Teams e Skype for business

Molte aziende di grandi dimensioni hanno più di una foresta di annunci locale e, in alcuni casi, i clienti hanno più di una distribuzione di Exchange e/o Skype for Business Server (o Lync Server). Inoltre, anche le organizzazioni con una sola foresta locale potrebbero trovarsi in una situazione simile tramite una fusione o un'acquisizione aziendale. Dato che questi clienti si trasferiscono nel cloud, vogliono consolidare le istanze multiple di un carico di lavoro locale nel cloud in un unico tenant di Office 365. Questo articolo descrive come ottenere il consolidamento per le organizzazioni con più distribuzioni locali di Skype for business (o Lync) che vogliono trasferire il carico di lavoro UC al cloud Microsoft, ad esempio Microsoft teams e/o Skype for business online.

Storicamente, le linee guida per i clienti in questa situazione consolidano le distribuzioni locali e poi si muovono nel cloud. Anche se si tratta di un'opzione, questo articolo descrive una soluzione basata sulle nuove funzionalità che consente alle organizzazioni con più distribuzioni di Skype for business di eseguire la migrazione di una distribuzione alla volta in un unico tenant di Office 365, senza fare locale consolidamento. Tieni presente che, anche con questa nuova funzionalità, Skype for business online e Microsoft teams non supportano più foreste di Skype for business/Lync in modalità ibrida con un unico tenant di Office 365. 

> [!Important]
> Prima di usare questa guida per la configurazione, assicurati di rivedere e comprendere le [limitazioni](#limitations), perché potrebbero influire sull'organizzazione.

## <a name="overview-of-cloud-consolidation"></a>Panoramica del consolidamento del cloud

Il consolidamento di tutti gli utenti dal locale al cloud in un unico tenant di Office 365 può essere realizzato per qualsiasi organizzazione con più distribuzioni di Skype for business, a condizione che siano soddisfatti i requisiti chiave seguenti:

- È necessario che al massimo un tenant di Office 365 sia coinvolto. Il consolidamento in scenari con più di un tenant di Office 365 non è supportato.
- In qualsiasi momento, una sola foresta Skype for business locale può essere in modalità ibrida (spazio di indirizzi SIP condiviso). Tutte le altre foreste di Skype for business locali devono rimanere in locale (e presumibilmente federate tra loro). Tieni presente che queste altre organizzazioni locali *possono* eseguire la sincronizzazione con AAD, se necessario, con [nuove funzionalità per disabilitare i domini SIP online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps) disponibili a partire da dicembre 2018.

I clienti con distribuzioni di Skype for business in più foreste devono eseguire la migrazione completa di tutti gli utenti di una singola foresta ibrida di Skype for business individualmente nel tenant di Office 365 usando la funzionalità di spazio di indirizzi SIP condiviso e quindi disabilitare Hybrid con tale distribuzione locale, prima di passare alla migrazione della nuova distribuzione locale di Skype for business. Prima di essere migrati nel cloud, gli utenti locali restano in uno stato federato con tutti gli utenti che non sono rappresentati nella stessa directory locale dell'utente.  

## <a name="canonical-example-of-cloud-consolidation"></a>Esempio canonico di consolidamento del cloud

Si consideri un'organizzazione con due distribuzioni federate locali separate di Skype for business che vuole consolidarle online in Microsoft teams o Skype for business online.


|Dettagli dello stato originale |Dettagli dello stato desiderati |
|---------|---------|
|<ul><li>2 distribuzioni locali Skype for business indipendenti in foreste di annunci separate<li>Al massimo 1 Forest è in Hybrid con Skype for business online <li> Org sono federati tra loro <li>Gli utenti non vengono sincronizzati tra questi insiemi di foreste<li> L'organizzazione potrebbe avere un tenant di Office 365 e può sincronizzare la propria directory in Azure AD</ul>|<ul> <li>1 Office 365 tenant<li>Non più distribuzioni locali, quindi nessun ibrido rimanente<li>Tutti gli utenti provenienti da locale sono ospitati in Skype for business online e facoltativamente possono essere utenti solo Teams <li>Nessuna impronta locale di Skype for business ovunque <li>Gli utenti hanno ancora l'autenticazione locale</ul> |

![Consolidamento di due distribuzioni locali federate separate](../media/cloudconsolidationfig1.png)  

Di seguito vengono illustrati i passaggi di base per ottenere dallo stato originale allo stato finale desiderato.  Tieni presente che alcune organizzazioni potrebbero scoprire che il loro punto di partenza è da qualche parte nel mezzo di questi passaggi. Vedere [altri punti di partenza](#other-starting-points), più avanti in questo articolo. Infine, in alcuni casi l'ordine può essere regolato, a seconda delle esigenze. I [vincoli e le limitazioni principali](#limitations) vengono descritti in seguito.

1.  Ottenere un tenant di Office 365 se non ne esiste ancora uno.
2.  Verificare che tutti i domini SIP rilevanti in entrambe le distribuzioni locali vengano verificati i domini di Office 365.
3.  Selezionare una distribuzione Skype for business che sarà ibrida con Office 365. In questo esempio useremo OriginalCompany. <span>com.
4.  [Abilitare AAD Connect per la foresta](configure-azure-ad-connect.md) che prima o poi diventa ibrida (OriginalCompany<span> . com). 
5.  Se si introdurranno team nell'organizzazione, impostare i criteri a livello di tenant per [TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) in SfBWithTeamsCollab o in una delle altre modalità di SFB (SfBOnly o SfBWithTeamsCollabAndMeetings). Questo è fondamentale per garantire il routing delle chiamate e delle chat dagli utenti che si trasferiscono in teams solo agli utenti che rimangono in locale.
6.  A questo punto è consigliabile (ma non ancora richiesto fino al passaggio 11) per [abilitare la connessione AAD per l'altra foresta](cloud-consolidation-aad-connect.md) (AcquiredCompany<span> . com). Supponendo che AAD Connect sia abilitato in entrambe le foreste, l'organizzazione ha l'aspetto della **[Figura A](#figure-a)**, che può essere un punto di partenza comune per alcuni org. 
7.  Per tutti i domini SIP ospitati da altre distribuzioni locali (in questo caso, AcquiredCompany.<span> com), [Disabilita questi domini SIP in Skype for business online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) usando `Disable-CsOnlineSipDomain` in PowerShell. (Si tratta di nuove funzionalità del 2018 dicembre)
8.  [Configurare Skype for business Hybrid](configure-federation-with-skype-for-business-online.md) per OriginalCompany. <span>com (l'unica distribuzione che ha ancora attivato i domini SIP online).
9.  Nella distribuzione ibrida (OriginalCompany.<span> com), iniziare [a spostare gli utenti da Skype for business in locale al cloud](move-users-between-on-premises-and-cloud.md) (solo per i team o meno) in modo che l'account venga ospitato in Skype for business online. A questo punto l'organizzazione ha l'aspetto della **[Figura B](#figure-b)**. Le modifiche chiave della figura A sono:
    - Gli utenti di entrambe le directory locali si trovano ora in AAD.
    - AcquiredCompany. <span>com è un dominio SIP disabilitato online.
    - Alcuni utenti sono stati spostati online in Skype for business online o in teams. (Vedi l'utente viola A.)
10. Dopo aver spostato tutti gli utenti nel cloud, [disabilitare Hybrid con la distribuzione locale di Skype for business](cloud-consolidation-disabling-hybrid.md) per OriginalCompany. <span>com da Office 365:  
    - Disabilitare il dominio diviso nel tenant di Office 365.
    - Disabilitare la possibilità di comunicare con Office 365 in OriginalCompany. <span>com locale.
    - Aggiornare i record DNS per OriginalCompany. <span>com per puntare a Office 365.
11. Se non è già stato fatto, [abilitare AAD Connect per la foresta successiva](cloud-consolidation-aad-connect.md) che verrà ibrida (AcquiredCompany<span> . com). A questo punto, l'organizzazione ha un aspetto simile alla **[Figura C](#figure-c)**. Questo potrebbe essere un altro punto di partenza comune per alcune organizzazioni. 
12. In PowerShell [abilitare i domini SIP per la prossima distribuzione locale](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) che sarà ibrida, AcquiredCompany. <span>com. Questa operazione viene eseguita `Enable-CsOnlineSipDomain`con le nuove funzionalità disponibili al 2018 dicembre.
13. Se si usa la federazione chiusa, è necessario aggiungere tutti i domini SIP (ad eccezione *. microsoftonline.com) del tenant online puro come domini consentiti nello **stesso** Office 365. Tieni presente che può essere necessario un po' di tempo prima che la modifica abbia effetto e che non ci siano problemi a farlo in anticipo, quindi ti consigliamo di farlo prima di passare al passaggio 14.
14. Aggiornare l'ambiente locale per accettare qualsiasi dominio SIP dal tenant online, in modo che corrispondano.
    - [Aggiornare la San in tutti i certificati Edge](cloud-consolidation-edge-certificates.md) per avere lo stesso valore di prima, oltre ai valori per tutti i domini SIP esistenti online (eccetto *. microsoftonline.com), in questo caso SIP. OriginalCompany. <span>com.
    - Verificare che OriginalCompany. <span>com è un [dominio consentito](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain) nella distribuzione locale, AcquiredCompany. Aggiungere domini consentiti.
15. [Abilitare Skype for business Hybrid](configure-federation-with-skype-for-business-online.md) tra AcquiredCompany locale. <span>com e il cloud.
16. Come desiderato, [eseguire la migrazione degli utenti dal locale al cloud](move-users-between-on-premises-and-cloud.md). Puoi eseguire la migrazione degli utenti direttamente alla modalità [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) oppure puoi eseguire la migrazione prima a Skype for business online. Durante questo stato, l'organizzazione ha un aspetto simile a **[Figura D](#figure-d)**.
17. Dopo la migrazione di tutti gli utenti, [disabilitare Hybrid con l'ambiente locale](cloud-consolidation-disabling-hybrid.md) per *rendere l'organizzazione cloud puro*.

I diagrammi seguenti mostrano la configurazione in diversi punti chiave durante questo processo.

##### <a name="figure-a"></a>Figura A:

- Entrambe le organizzazioni vengono sincronizzate tramite AAD Connect, pertanto AAD include tutti gli utenti di entrambe le distribuzioni locali.
- Tutti gli utenti ospitati in locale.  
- Skype for business Hybrid *non* è ancora configurato.
- Se gli utenti di una distribuzione usano team, non saranno in grado di federarsi tra loro (o qualsiasi organizzazione), né avranno l'interoperabilità con gli utenti di Skype for business. In questa fase, Microsoft consiglia di usare teams solo per i canali.<br><br>
    ![Figura di un diagramma](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figura B:

- AcquiredCompany. <span>com è un [](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) dominio SIP disabilitato online. Tutti gli utenti sono locali. Se usano teams, non hanno la Federazione o l'interoperabilità. In questa fase, Microsoft consiglia di usare teams solo per i canali.
- Skype for business Hybrid è stato abilitato per una delle organizzazioni locali.
- Alcuni utenti dell'organizzazione ibrida sono stati spostati nel cloud (utente A come indicato da ombreggiatura viola). Questi utenti possono essere utenti di Skype for business online o solo teams con l'interoperabilità completa e il supporto federativo.<br><br>
    ![Figura B diagramma](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figura C:

- Tutti gli utenti di OriginalCompany. <span>com ora sono nel cloud (Homer in Skype for business online). È consigliabile che siano anche solo teams.
- Configurazione ibrida di Skype for business con OriginalCompany. <span>la distribuzione com è stata disattivata. La distribuzione locale non è più disponibile.
- Se AcquiredCompany. <span>com non è stata precedentemente sincronizzata con AAD, per continuare da qui è necessario sincronizzarla ora. Ma non è ancora ibrido (spazio di indirizzi SIP condiviso) e finché l'organizzazione non è pronta per il passaggio a Hybrid, il dominio SIP online per l'organizzazione locale pura (AcquiredCompany.com) deve rimanere disabilitato, in modo che gli utenti di Team online possano comunicare con utenti locali.<br><br>
    ![Figura C diagramma](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figura D:

- AcquiredCompany. <span>com è ora abilitato come dominio SIP online.
- La versione locale viene aggiornata per accettare OriginalCompany. <span>com. (Sia il dominio consentito che i certificati Edge vengono aggiornati).
- Lo spazio di indirizzi SIP condiviso è abilitato tra AcquiredCompany. <span>tenant di com e Office 365.
- Alcuni utenti dell'organizzazione ibrida potrebbero essere stati spostati nel cloud, ad esempio l'utente D seguente (indicato da ombreggiatura viola).<br><br>
    ![Figura D diagramma](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Altri punti di partenza

I passaggi dell'esempio canonico precedente presuppongono che l'organizzazione inizi con due distribuzioni locali federate senza presenza di Office 365. Alcune organizzazioni potrebbero tuttavia avere un'impronta di Office 365 esistente e possono essere presenti diversi punti di ingresso nella sequenza precedente. Sono disponibili quattro configurazioni tipiche:

- Più organizzazioni locali federate con nessun tenant di Office 365. In questo caso, iniziare dal passaggio 1.
- Più organizzazioni locali federate che stanno già sincronizzando più insiemi di strutture Skype for business in un unico tenant di Azure AD. Tale organizzazione è simile all'organizzazione ipotetica nella figura A, che ha completato i passaggi 1-6 e dovrebbe iniziare al passaggio 7.
- Un'organizzazione ibrida che federa con 1 o più altre organizzazioni locali pure, nessuna delle quali viene sincronizzata con AAD. Tale organizzazione assomiglierà all'organizzazione ipotetica nella **Figura E**, illustrata di seguito.
    - Questa organizzazione è simile alla figura B, che ha completato i passaggi 1-9, tranne:
        - Le distribuzioni non ibride di Skype for business *non* sono ancora state sincronizzate con Azure ad.
        -  I domini SIP online non sono ancora disabilitati. 
    - Queste organizzazioni devono essere:
        - Completare la migrazione dell'organizzazione ibrida esistente e immettere la sequenza precedente al passaggio 10.  O
        - Se si vuole sincronizzare tutti gli altri insiemi di strutture Skype for business in AAD prima di completare la migrazione dell'organizzazione ibrida, l'organizzazione deve eseguire il passaggio 7 (disabilitare tutti i domini SIP online in qualsiasi altra distribuzione Skype for business locale che verrà sincronizzarsi con AAD) e quindi abilitare AAD Connect e quindi continuare con il passaggio 10 (rimuovere la distribuzione ibrida originale).       
                **Figura E**<br>
                ![Figura E diagramma](../media/cloudconsolidationfige.png)
- Un'organizzazione pura di Skype for business online (che può o non può usare Teams) che federa con un'organizzazione separata di Skype for business locale. Dopo che l'organizzazione ha disabilitato il dominio SIP online per l'organizzazione locale e abilitato AAD Connect per l'organizzazione locale di Skype for business, è simile all'ipotetica organizzazione illustrata nella **[Figura C](#figure-c)** che contiene i passaggi completati 1-11.

## <a name="limitations"></a>Limitazioni

- È necessario che al massimo un tenant di Office 365 sia coinvolto. Il consolidamento in scenari con più di un tenant di Office 365 non è supportato.
- Una sola foresta Skype for business locale può essere in modalità ibrida (spazio di indirizzi SIP condiviso) alla volta. Tutte le altre foreste di Skype for business locali devono rimanere solo in locale e devono essere federate tra loro e il tenant di Office 365.
- Prima di essere migrati nel cloud, esiste un'esperienza asimmetrica per gli utenti in questa distribuzione, perché non tutti gli utenti in online sono rappresentati in locale:
    - L'esperienza può essere riassunta come segue:
        - Qualsiasi utente di Homer online interagirà con gli utenti locali nell'ambiente ibrido, come se l'utente fosse ibrido.
        - Gli utenti locali nella distribuzione ibrida interagiranno con gli utenti online rappresentati nella directory locale come se fossero ibridi. 
        - Gli utenti locali nella distribuzione ibrida interagiranno con gli utenti online che non sono rappresentati in un annuncio locale come federati.
    - Nella **[Figura D](#figure-d)** sopra, l'utente E è locale in AcquiredCompany. <span>com.  L'utente E interagirà con l'utente D (homed online) usando l'esperienza ibrida standard, ma l'utente E avrà un'esperienza federata con gli utenti A, B e C, perché non sono rappresentati nella directory locale. Tuttavia, gli utenti A, B e C interagiranno con l'utente E come se l'utente fosse in Hybrid.
    - Implicazioni dell'interazione tra ibridi e federazioni:
        - La presenza non viene sottoscritta automaticamente per gli utenti federati, a meno che l'utente non sia contrassegnato come contatto.
        - L'inoltro di chiamata non funziona tra domini federati.
        - Gli scenari di trasferimento delle chiamate sono più limitati.
        - La limitazione può essere applicata al traffico federativo.
- In base a questa esperienza asimmetrica, il supporto ufficiale per la funzionalità di chiamata in scenari interlocali tra un utente locale e un utente cloud che non si trova nella directory locale è limitato solo al peer to peer. 
    - L'inoltro di chiamata, il trasferimento, le code di chiamata e così via tra questi utenti non è supportato.
    - Questi scenari di chiamata non supportati continueranno a essere abilitati, ma in molti casi non saranno più disponibili in modo imprevedibile. 
    - Nella **[Figura D](#figure-d)** sopra, l'utente e è locale e le chiamate con gli utenti a, B o C saranno supportate solo come peer-to-peer. Le chiamate con l'utente D non avrebbero limitazioni di supporto.  Tuttavia, dopo che l'utente locale E viene spostato nel cloud, questa restrizione non si applica più.
- Se si hanno più distribuzioni di Skype for Business Server 2019 nell'ambiente, è possibile configurare solo una di queste distribuzioni per l'uso dell'operatore automatico aziendale, poiché tale funzionalità richiede la configurazione ibrida di Skype for Business Server. 
- L'ordine di alcuni passaggi precedenti può essere regolato. Il requisito chiave che deve essere soddisfatta è che, se tutte queste condizioni sono vere:
    - Più di una foresta Skype for business in locale che si sincronizza con un singolo tenant di AAD
    - Il dominio diviso è abilitato con una foresta locale
    - Almeno un utente nell'organizzazione ibrida è stato migrato nel cloud<br>   Devi quindi disabilitare ** tutti gli altri domini SIP online da qualsiasi altra foresta Skype for business locale. In caso contrario, la Federazione tra gli utenti online nell'organizzazione ibrida e gli utenti locali in altre organizzazioni si spezzerà in una direzione.

## <a name="implications"></a>Implicazioni

- Poiché esistono limitazioni nel supporto della funzionalità per le chiamate avanzate come descritto in precedenza, **le organizzazioni dovrebbero trattare questi stati asimmetrici come transitori come parte della migrazione e non perseguirli come stato stabile**.  
- Le organizzazioni con più distribuzioni di Skype for business locali dovrebbero in genere iniziare con una distribuzione che può essere completamente migrata nel cloud, in modo che il consolidamento possa continuare. Si comprende che in alcuni casi ci saranno holdouts di determinati gruppi di utenti per i quali non è ancora possibile trasferirsi in teams. Quando si tratta di una considerazione in scenari che coinvolgono più foreste Skype for business, iniziare a eseguire la migrazione con un'altra foresta che non ha queste limitazioni, se possibile.
- Quando si passa dal locale al cloud, gli utenti che hanno relazioni di delega e/o sono in genere coinvolti in scenari di inoltro di chiamata devono essere spostati insieme come unità.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Considerazioni per passare alla modalità TeamsOnly

Quando si spostano gli utenti dal locale al cloud in un ambiente ibrido, è possibile spostarli in modalità solo Skype for business o TeamsOnly. *Se si prevede di trasferire gli utenti in modalità TeamsOnly, assicurarsi di leggere prima di tutto questa sezione.*

- Quando si assegna la modalità TeamsOnly a un utente, tutte le chat e le chiamate di qualsiasi altro utente sbarcheranno nel client teams di tale utente. 
- Per garantire un corretto routing delle chat e delle chiamate tra gli utenti TeamsOnly e gli utenti che stanno ancora usando Skype for business in locale, devi assicurarti che gli utenti locali abbiano TeamsUpgradePolicy con una delle modalità di SfB, invece che con le isole (che è l'impostazione predefinita ). 
    - A questo scopo, *devi prima impostare l'istanza globale del tenant di TeamsUpgradePolicy su uno di questi valori*:
        - SfBWithTeamsCollab (scelta consigliata)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - È possibile concedere criteri a livello di tenant usando questo comando:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Nota: al momento, è necessario eseguire questa operazione a livello di tenant, perché i criteri non possono essere assegnati a singoli utenti che non hanno un indirizzo SIP nella directory online. Mentre sono stati disabilitati i domini SIP online per le distribuzioni locali, gli utenti di tali domini non avranno indirizzi SIP nella directory online in base alla progettazione. L'unico modo per applicare criteri agli utenti locali è quindi l'assegnazione a livello di tenant. Al contrario, nella distribuzione ibrida gli utenti avranno un indirizzo SIP nella directory online in modo che possano essere assegnati in modo esplicito a un criterio, se si vuole che abbiano un valore diverso rispetto al criterio globale del tenant.
- Il client teams UX non rispetta ancora le modalità SfB di TeamsUpgradePolicy. Ad esempio, quando in queste modalità, l'avvio delle chiamate e delle chat in team è attualmente possibile, anche se in futuro non sarà così. Ciò può causare confusione tra gli utenti perché le risposte possono talvolta atterrare in team e, a volte, Skype for business, a seconda delle circostanze. È consigliabile disabilitare separatamente la chiamata e la chat tramite TeamsMessagingPolicy e TeamsCallingPolicy per gli utenti che sono ancora in locale.

## <a name="see-also"></a>Vedere anche

[Aggiornare il certificato Edge](cloud-consolidation-edge-certificates.md)

[Aggiornare AAD Connect per includere più di una foresta](cloud-consolidation-aad-connect.md)

[Disabilitare l'ibrido per completare la migrazione al cloud](cloud-consolidation-disabling-hybrid.md)
