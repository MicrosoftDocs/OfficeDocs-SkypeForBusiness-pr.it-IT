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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: In questo articolo viene descritto come ottenere tale consolidamento per le organizzazioni con distribuzioni locali di Skype for business (o Lync) in cerca di spostamento per spostare il carico di lavoro UC nei team e/o in Skype for business online.
ms.openlocfilehash: 859a6f3809a653334f7ac43b591d9a067833e3d5
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780135"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidamento del cloud per Teams e Skype for Business

Molte grandi aziende hanno più di una foresta di Active Directory locale e, in alcuni casi, i clienti hanno più di una distribuzione di Exchange e/o Skype for Business Server (o Lync Server). Inoltre, anche le organizzazioni con una sola foresta locale potrebbero trovarsi nella stessa situazione con un'acquisizione o una fusione aziendale. Poiché questi clienti si spostano nel cloud, desiderano consolidare più istanze di un determinato carico di lavoro locale nel cloud in un'unica organizzazione di Office 365. In questo articolo viene descritto come ottenere tale consolidamento per le organizzazioni con più distribuzioni locali di Skype for business (o Lync) che desiderano spostare il carico di lavoro UC verso Microsoft Cloud, ad esempio Microsoft teams e/o Skype for business online.

In passato, sono state fornite indicazioni per i clienti che si trovavano in questa situazione che volevano consolidare le distribuzioni locali per poi passare al cloud. Anche se questa è un'opzione, in questo articolo viene descritta una soluzione basata su nuove funzionalità che consentono alle organizzazioni con più distribuzioni di Skype for business di migrare una distribuzione alla volta in un'unica organizzazione di Office 365 senza eseguire consolidamenti locali. Si noti che anche con questa nuova funzionalità, Skype for business online e Microsoft teams non supportano più foreste di Skype for business/Lync in modalità ibrida con una singola organizzazione di Office 365. 

> [!Important]
> Prima di utilizzare questa guida per la configurazione, assicurarsi di esaminare e comprendere le [limitazioni](#limitations), in quanto potrebbero influire sull'organizzazione.

## <a name="overview-of-cloud-consolidation"></a>Panoramica sul consolidamento del cloud

Il consolidamento di tutti gli utenti provenienti da locali nel cloud in un'unica organizzazione di Office 365 può essere raggiunto per qualsiasi organizzazione con più distribuzioni di Skype for business, purché vengano soddisfatti i requisiti chiave seguenti:

- La maggior parte dell'organizzazione di Office 365 deve essere coinvolta. Il consolidamento in scenari con più di un'organizzazione di Office 365 non è supportato.
- In un determinato momento, solo una foresta di Skype for Business locale può essere in modalità ibrida (Spazio di indirizzi SIP condiviso). Tutte le altre foreste locali di Skype for Business devono rimanere locali (e presumibilmente federate tra loro). Si noti che queste altre organizzazioni locali *possono* sincronizzarsi con AAD, se lo si desidera, con [nuove funzionalità per disabilitare i domini SIP online](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps) disponibili al 2018 dicembre.

I clienti con distribuzioni di Skype for business in più foreste devono migrare completamente tutti gli utenti di una singola foresta ibrida di Skype for business singolarmente nell'organizzazione di Office 365 utilizzando la funzionalità dello spazio di indirizzi SIP condiviso e quindi disabilitare la distribuzione ibrida con quella locale, prima di procedere alla migrazione della successiva distribuzione di Skype for business locale. Prima di essere migrati nel cloud, gli utenti locali restano in uno stato federato con tutti gli utenti che non sono rappresentati nella stessa directory locale dell'utente.  

## <a name="canonical-example-of-cloud-consolidation"></a>Esempio canonico di consolidamento del cloud

Si consideri un'organizzazione con due distribuzioni federate locali separate di Skype for business che voglia consolidarle online in Microsoft teams o Skype for business online.


|Dettagli sullo stato originali |Dettagli sullo stato desiderati |
|---------|---------|
|<ul><li>2 distribuzioni indipendenti di Skype for business locali in insiemi di strutture di Active Directory separati<li>Al massimo 1 la foresta è in ibrido con Skype for business online <li> Org sono federati tra loro <li>Gli utenti non vengono sincronizzati tra queste foreste<li> L'organizzazione può disporre di una società di Office 365 e può sincronizzare la directory in Azure AD</ul>|<ul> <li>1 organizzazione di Office 365<li>Non ci sono altre distribuzioni locali, quindi nessuna soluzione ibrida restante<li>Tutti gli utenti provenienti da locale sono ospitati in Skype for business online e, facoltativamente, possono essere utenti solo di Teams <li>Nessuna impronta locale di Skype for business via Internet <li>Gli utenti hanno ancora l'autenticazione locale</ul> |

![Consolidamento di due distribuzioni locali federate separate](../media/cloudconsolidationfig1.png)  

Di seguito sono riportati i passaggi di base da recuperare dallo stato originale allo stato finale desiderato.  Si noti che alcune organizzazioni potrebbero scoprire che il punto di partenza è da qualche parte nel mezzo di questi passaggi. Vedere [altri punti di partenza](#other-starting-points), più avanti in questo articolo. Infine, in alcuni casi, l'ordine può essere regolato, a seconda delle esigenze. I [vincoli e i limiti principali](#limitations) vengono descritti in un secondo momento.

1.  Ottenere un'organizzazione di Office 365, se non ne esiste ancora una.
2.  Verificare che tutti i domini SIP rilevanti nelle distribuzioni locali siano verificati come domini di Office 365.
3.  Scegliere una distribuzione Skype for business che sarà ibrida con Office 365. In questo esempio verrà utilizzato OriginalCompany. <span>com.
4.  [Abilitare AAD Connect per la foresta](configure-azure-ad-connect.md) che prima diventerà ibrida (OriginalCompany<span> . com). 
5.  Se si intende introdurre team nell'organizzazione, impostare il criterio a livello di tenant per [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy) su SfBWithTeamsCollab oppure su una delle altre modalità di questo (SfBOnly o SfBWithTeamsCollabAndMeetings). Questo è fondamentale per garantire il routing di chiamate e chat da parte di utenti che si spostano in team solo per gli utenti che rimangono in locale.
6.  È consigliabile, a questo punto, ma non ancora necessario fino al passaggio 11, per [abilitare AAD Connect per l'altra foresta](cloud-consolidation-aad-connect.md) (AcquiredCompany<span> . com). Presupponendo che AAD Connect sia abilitato in entrambe le foreste, l'organizzazione ha l'aspetto di **[una figura a](#figure-a)**, che può essere un punto di partenza comune per alcuni org. 
7.  Per tutti i domini SIP ospitati da altre distribuzioni locali (in questo caso, AcquiredCompany.<span> com), [disabilitare questi domini SIP in Skype for business online](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) utilizzando `Disable-CsOnlineSipDomain` in PowerShell. (Questa è una nuova funzionalità del 2018 dicembre).
8.  [Configurare Skype for business ibrido](configure-federation-with-skype-for-business-online.md) per OriginalCompany. <span>com (la distribuzione che ha ancora abilitato i domini SIP online).
9.  Nella distribuzione ibrida (OriginalCompany.<span> com), avviare [lo spostamento degli utenti da Skype for business in locale al cloud](move-users-between-on-premises-and-cloud.md) (solo se solo team o meno) in modo che account sia ospitato in Skype for business online. A questo punto l'organizzazione ha l'aspetto di **[Figura B](#figure-b)**. Le modifiche alla chiave della figura A sono le seguenti:
    - Gli utenti di entrambe le directory locali sono ora presenti in AAD.
    - AcquiredCompany. <span>com è un dominio SIP disabilitato in linea.
    - Alcuni utenti sono stati spostati online in Skype for business online o in teams. (Vedere l'utente viola A.)
10. Dopo che tutti gli utenti sono stati spostati nel cloud, [disabilitare l'ambiente ibrido con la distribuzione locale di Skype for business](cloud-consolidation-disabling-hybrid.md) per OriginalCompany. <span>com da Office 365:  
    - Disabilitare il dominio diviso nell'organizzazione di Office 365.
    - Disabilitare la possibilità di comunicare con Office 365 in OriginalCompany. <span>com locale.
    - Aggiornare i record DNS per OriginalCompany. <span>com per puntare a Office 365.
11. Se non è già stato fatto, [abilitare AAD Connect per la foresta successiva](cloud-consolidation-aad-connect.md) che passerà a un<span> ambiente ibrido (AcquiredCompany. com). A questo punto, l'organizzazione ha l'aspetto di **[Figura C](#figure-c)**. Può trattarsi di un altro punto di partenza comune per alcune organizzazioni. 
12. In PowerShell, [abilitare i domini SIP per la successiva distribuzione locale](https://docs.microsoft.com/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) che andrà a un ambiente ibrido, AcquiredCompany. <span>com. Questa operazione viene fatta `Enable-CsOnlineSipDomain`usando, che è una nuova funzionalità disponibile al 2018 dicembre.
13. Se si utilizza la federazione chiusa, è necessario aggiungere qualsiasi dominio SIP (escluso *. microsoftonline.com) del tenant puro online come domini consentiti nello **stesso** Ufficio 365. Si noti che è possibile richiedere un certo tempo prima che la modifica abbia effetto e che non vi siano danni in questo modo in anticipo, quindi si consiglia di procedere bene prima di passare al passaggio 14.
14. Aggiornare l'ambiente locale per accettare qualsiasi dominio SIP dal tenant online, in modo che corrispondano.
    - [Aggiornare la rete San in tutti i certificati Edge](cloud-consolidation-edge-certificates.md) in modo che corrisponda allo stesso valore di prima, oltre ai valori per i domini SIP esistenti in linea (eccetto *. microsoftonline.com), in questo caso SIP. OriginalCompany. <span>com.
    - Assicurarsi che OriginalCompany. <span>com è un [dominio consentito](https://docs.microsoft.com/powershell/module/skype/new-csalloweddomain) nella distribuzione locale, AcquiredCompany. Aggiungere domini consentiti.
15. [Abilitare l'ambiente ibrido Skype for business](configure-federation-with-skype-for-business-online.md) tra AcquiredCompany locale. <span>com e il cloud.
16. Come desiderato, [eseguire la migrazione degli utenti da locale al cloud](move-users-between-on-premises-and-cloud.md). È possibile eseguire la migrazione degli utenti direttamente alla modalità [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) oppure è possibile eseguirne la migrazione prima a Skype for business online. Durante questo stato, l'organizzazione ha l'aspetto di **[Figura D](#figure-d)**.
17. Dopo la migrazione di tutti gli utenti, disabilitare la modalità [ibrida con l'ambiente locale](cloud-consolidation-disabling-hybrid.md) per *rendere l'organizzazione cloud puro*.

Nei diagrammi riportati di seguito viene illustrata la configurazione in vari punti chiave durante questo processo.

##### <a name="figure-a"></a>Figura A:

- Entrambe le organizzazioni eseguono la sincronizzazione tramite AAD Connect, pertanto AAD ha tutti gli utenti da entrambe le distribuzioni locali.
- Tutti gli utenti ospitati in locale.  
- L'ambiente ibrido di Skype for business *non* è stato ancora configurato.
- Se gli utenti di entrambe le distribuzioni utilizzano i team, non saranno in grado di eseguire la Federazione tra loro (o qualsiasi organizzazione), né avranno interoperabilità con gli utenti di Skype for business. Anche se in questa fase, Microsoft consiglia di utilizzare Team solo per i canali.<br><br>
    ![Figura A diagramma](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figura B:

- AcquiredCompany. <span>com è un dominio SIP [disabilitato](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) in linea. Tutti gli utenti sono in locale. Se utilizzano Team non dispongono di una federazione o di un'interoperabilità. Anche se in questa fase, Microsoft consiglia di utilizzare Team solo per i canali.
- Skype for business ibrido è stato abilitato per una delle organizzazioni locali.
- Alcuni utenti nell'organizzazione ibrida sono stati spostati nel cloud (utente A come indicato dall'ombreggiatura viola). Questi utenti possono essere utenti di Skype for business online o solo per i team che dispongono di un supporto di interoperabilità completo e federativo.<br><br>
    ![Figura B diagramma](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figura C:

- Tutti gli utenti di OriginalCompany. <span>com sono ora presenti nel cloud (in Skype for business online). È consigliabile che siano anche solo squadre.
- Configurazione ibrida di Skype for business con OriginalCompany. <span>la distribuzione com è stata disattivata. La distribuzione locale è andata.
- Se AcquiredCompany. <span>com non è stata precedentemente sincronizzata con AAD, per continuare da qui è necessario sincronizzarla adesso. Tuttavia, non è ancora ibrido (spazio di indirizzi SIP condiviso) e finché l'organizzazione non è pronta per il passaggio a un ambiente ibrido, il dominio SIP online per l'organizzazione pura locale (AcquiredCompany.com) deve rimanere disabilitato, in modo che gli utenti di Team online possano comunicare con gli utenti locali.<br><br>
    ![Figura C diagramma](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figura D:

- AcquiredCompany. <span>com è ora abilitato come dominio SIP online.
- L'ambiente locale viene aggiornato per accettare OriginalCompany. <span>com. (Entrambi i domini consentiti e i certificati Edge vengono aggiornati).
- Lo spazio degli indirizzi SIP condiviso è abilitato tra AcquiredCompany. <span>organizzazione com e Office 365.
- Alcuni utenti nell'organizzazione ibrida potrebbero essere stati spostati nel cloud, ad esempio l'utente D seguente (indicato da ombreggiatura viola).<br><br>
    ![Figura D diagramma](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Altri punti di partenza

La procedura descritta nell'esempio canonico precedente presuppone che l'organizzazione inizi con due distribuzioni locali federate senza presenza di Office 365. Tuttavia, alcune organizzazioni possono disporre di un footprint di Office 365 esistente e possono essere presenti diversi punti di ingresso nella sequenza precedente. Sono disponibili quattro configurazioni tipiche:

- Più organizzazioni locali federate con nessuna organizzazione di Office 365. In questo caso, iniziare dal passaggio 1.
- Più organizzazioni locali federate che già eseguono la sincronizzazione di più foreste Skype for business in un unico tenant Azure AD. Tale organizzazione assomiglia all'organizzazione ipotetica nella figura A, che ha completato i passaggi 1-6 e deve iniziare al passaggio 7.
- Un'organizzazione ibrida che federa una o più organizzazioni locali pure, nessuna delle quali è sincronizzata con AAD. Tale organizzazione assomiglierà all'ipotetica organizzazione della **Figura E**, illustrata di seguito.
    - Questa organizzazione è simile alla figura B, che ha completato i passaggi 1-9, tranne:
        - Le distribuzioni non ibride di Skype for business *non* sono ancora sincronizzate con Azure ad.
        -  I domini SIP online non sono ancora disabilitati. 
    - Queste organizzazioni dovrebbero:
        - Completare la migrazione dell'organizzazione ibrida esistente e immettere la sequenza di cui sopra al passaggio 10.  O
        - Se si desidera sincronizzare tutti gli altri insiemi di strutture Skype for business in AAD prima del completamento della migrazione dell'organizzazione ibrida, l'organizzazione deve eseguire il passaggio 7 (disabilitare tutti i domini SIP online in qualsiasi altra distribuzione Skype for business locale che verrà sincronizzata in AAD) e quindi abilitare AAD Connect e quindi continuare con il passaggio 10 (rimuovere la distribuzione ibrida originale).       
                **Figura E**<br>
                ![Figura E diagramma](../media/cloudconsolidationfige.png)
- Un'organizzazione di Skype for business online pura (che può o meno usare Teams) che viene federata con un'organizzazione di Skype for business locale separata. Una volta che l'organizzazione disattiva il dominio SIP online per l'organizzazione locale e Abilita AAD Connect per l'organizzazione di Skype for business locale, assomiglia all'organizzazione ipotetica illustrata nella **[Figura C](#figure-c)** che ha completato i passaggi 1-11.

## <a name="limitations"></a>Limitazioni

- La maggior parte dell'organizzazione di Office 365 deve essere coinvolta. Il consolidamento in scenari con più di un'organizzazione di Office 365 non è supportato.
- Solo una foresta Skype for business locale può essere in modalità ibrida (spazio di indirizzi SIP condiviso) alla volta. Tutte le altre foreste di Skype for business locali devono rimanere solo in locale e devono essere federate tra loro e con l'organizzazione di Office 365.
- Prima di eseguire la migrazione nel cloud, è presente un'esperienza asimmetrica per gli utenti in questa distribuzione, perché non tutti gli utenti in linea sono rappresentati in locale:
    - L'esperienza può essere riassunta come indicato di seguito:
        - Qualsiasi utente ospitato online interagirà con gli utenti locali nell'ambiente ibrido come se l'utente fosse ibrido.
        - Gli utenti locali nella distribuzione ibrida interagiscono con gli utenti online che sono rappresentati nella loro directory locale come se fossero ibridi. 
        - Gli utenti locali nella distribuzione ibrida interagiscono con gli utenti online che non sono rappresentati in un annuncio locale come federato.
    - Nella **[Figura D](#figure-d)** sopra, l'utente E è in locale in AcquiredCompany. <span>com.  L'utente E interagirà con l'utente D (Homes online) utilizzando l'esperienza ibrida standard, ma l'utente E avrà un'esperienza federata con gli utenti A, B e C, perché non sono rappresentati nella directory locale. Tuttavia, gli utenti A, B e C interagiscono con l'utente E come se si trattasse di un utente ibrido.
    - Implicazioni dell'interazione tra ibrido e Federazione:
        - La presenza non viene sottoscritta automaticamente per gli utenti federati, a meno che l'utente non sia contrassegnato come contatto.
        - L'inoltro di chiamata non funziona tra i domini federati.
        - Gli scenari di trasferimento delle chiamate sono più limitati.
        - La limitazione può essere applicata al traffico federato.
- Data questa esperienza asimmetrica, il supporto ufficiale per la funzionalità di chiamata in scenari cross-premise tra un utente locale e un utente cloud che non si trova nella directory locale è limitato al solo peer-to-peer. 
    - L'inoltro di chiamata, il trasferimento, le code di chiamata e così via tra questi utenti non è supportato.
    - Questi scenari di chiamata non supportati continueranno a essere attivati, ma in molti casi avranno esito negativo in modi imprevedibili. 
    - Nella **[Figura D](#figure-d)** sopra, l'utente e è in locale e le chiamate con gli utenti a, B o C saranno supportate solo come peer to peer. Le chiamate con l'utente D non avrebbero limitazioni di supporto.  Tuttavia, dopo che l'utente locale E viene spostato nel cloud, questa restrizione non si applica più.
- Se si dispone di più di una distribuzione di Skype for Business Server 2019 nell'ambiente, solo 1 di tali distribuzioni può essere configurata per l'utilizzo dell'operatore automatico aziendale, poiché tale caratteristica richiede la configurazione ibrida di Skype for Business Server. 
- È possibile modificare l'ordine di alcuni dei passaggi precedenti. Il requisito fondamentale che deve soddisfare è che se tutti questi sono veri:
    - Più di una foresta di Skype for business in locale per la sincronizzazione con un singolo tenant di AAD
    - Il dominio diviso è abilitato con una foresta locale
    - Almeno un utente nell'organizzazione ibrida è stato migrato nel cloud<br>   Successivamente, è *necessario* disabilitare tutti gli altri domini SIP online da qualsiasi altra foresta Skype for business locale. In caso contrario, la Federazione tra gli utenti online nell'organizzazione ibrida e gli utenti locali in altre organizzazioni si romperà in una direzione.

## <a name="implications"></a>Implicazioni

- Poiché vi sono limitazioni del supporto per la funzionalità di chiamata avanzata, come descritto in alto, **le organizzazioni devono considerare tali Stati asimmetrici come transitori come parte della migrazione e non inseguirli come stato stabile**.  
- Le organizzazioni con più distribuzioni di Skype for business locali dovrebbero in genere iniziare con una distribuzione che può essere completamente migrata nel cloud, in modo che il consolidamento possa continuare. Si capisce che in alcuni casi vi sarà holdouts di alcuni gruppi di utenti per i quali non è ancora possibile passare ai team. Quando si tratta di una considerazione negli scenari che coinvolgono più foreste Skype for business, avviare la migrazione con un'altra foresta che non dispone di queste limitazioni, se possibile.
- Quando si passa da un ambiente locale al cloud, gli utenti che dispongono di relazioni di delega e/o sono in genere coinvolti in scenari di inoltro di chiamata devono essere spostati insieme come unità.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Considerazioni su come passare alla modalità TeamsOnly

Quando si spostano gli utenti da locale al cloud in un ambiente ibrido, è possibile spostarli in modalità solo Skype for business o TeamsOnly. *Se si prevede di spostare gli utenti in modalità TeamsOnly, assicurarsi di leggere prima questa sezione.*

- Quando si assegna la modalità TeamsOnly a un utente, tutte le chat e le chiamate provenienti da qualsiasi altro utente sbarcheranno nel client teams di tale utente. 
- Se gli utenti di Skype for business in locale utilizzano principalmente client Skype for business e non team, è consigliabile impostare TeamsUpgradePolicy in modo che il routing per gli utenti locali sia sempre in Skype for business invece che in teams. Per garantire il corretto routing delle chat e delle chiamate tra gli utenti che sono TeamsOnly e gli utenti che continuano a usare Skype for business in locale, gli utenti locali devono avere un valore effettivo di TeamsUpgradePolicy con una delle modalità di questo, anziché le isole (impostazione predefinita). 
    - A tale scopo, *è necessario prima di tutto impostare l'istanza globale del tenant di TeamsUpgradePolicy su uno dei valori seguenti*:
        - SfBWithTeamsCollab (scelta consigliata)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - È possibile concedere criteri a livello di tenant utilizzando il comando seguente:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Nota: è necessario eseguire questa operazione a livello di tenant, perché non è possibile assegnare il criterio a singoli utenti che non dispongono di un indirizzo SIP nella directory online. Anche se sono stati disabilitati i domini SIP online per le distribuzioni locali, gli utenti di tali domini non avranno indirizzi SIP nella directory online in base alla progettazione. Di conseguenza, l'unico modo per applicare i criteri agli utenti locali è l'assegnazione a livello di tenant. Al contrario, nella distribuzione ibrida gli utenti avranno un indirizzo SIP nella directory online in modo che possano essere assegnati in modo esplicito a un criterio, se si desidera che dispongano di un valore diverso da quello del tenant Global.
- Il client teams UX non rispetta ancora le modalità di questo di TeamsUpgradePolicy. Ad esempio, quando in queste modalità, l'avvio di chiamate e chat nei team è attualmente possibile, anche se in futuro non sarà così. Ciò può causare confusione tra gli utenti, perché le risposte a volte possono atterrare in team e, a volte, Skype for business, a seconda delle circostanze. Si consiglia di disabilitare separatamente le chiamate e le chat tramite TeamsMessagingPolicy e TeamsCallingPolicy per gli utenti che sono ancora in locale.

## <a name="see-also"></a>Vedere anche

[Aggiornare il certificato perimetrale](cloud-consolidation-edge-certificates.md)

[Aggiornare AAD Connect per includere più di una foresta](cloud-consolidation-aad-connect.md)

[Disabilitare la soluzione ibrida per completare la migrazione al cloud](cloud-consolidation-disabling-hybrid.md)
