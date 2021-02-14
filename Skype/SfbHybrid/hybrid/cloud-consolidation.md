---
title: Consolidamento del cloud per Teams e Skype for Business
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
description: In questo articolo viene descritto come raggiungere tale consolidamento per le organizzazioni con distribuzioni locali di Skype for Business (o Lync) che desiderano spostare il carico di lavoro per le comunicazioni unificate in Teams e/o Skype for Business online.
ms.openlocfilehash: d2733ffacf8b56a5cfe4217553f533950eb82e36
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221490"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidamento del cloud per Teams e Skype for Business

Molte grandi aziende hanno più di una foresta di Active Directory locale e, in alcuni casi, i clienti hanno più di una distribuzione di Exchange e/o Skype for Business Server (o Lync Server). Inoltre, anche le organizzazioni con una sola foresta locale potrebbero trovarsi nella stessa situazione con un'acquisizione o una fusione aziendale. Quando questi clienti passano al cloud, desiderano consolidare le più istanze di un determinato carico di lavoro locale nel cloud in una singola organizzazione di Microsoft 365 o Office 365. Questo articolo descrive come raggiungere tale consolidamento per le organizzazioni con più distribuzioni locali di Skype for Business (o Lync) che desiderano spostare il carico di lavoro uc nel cloud Microsoft, ad esempio Microsoft Teams e/o Skype for Business online.

In passato, sono state fornite indicazioni per i clienti che si trovavano in questa situazione che volevano consolidare le distribuzioni locali per poi passare al cloud. Anche se questa è ancora un'opzione, questo articolo descrive una soluzione basata su una nuova funzionalità che consente alle organizzazioni con più distribuzioni Skype for Business di eseguire la migrazione di una distribuzione alla volta in una singola organizzazione di Microsoft 365 o Office 365, senza eseguire il consolidamento locale. Anche con questa nuova funzionalità, Skype for Business Online e Microsoft Teams non supportano più foreste Skype for Business/Lync in modalità ibrida con una singola organizzazione di Microsoft 365 o Office 365. 

> [!Important]
> Prima di utilizzare questa guida per la configurazione, assicurarsi di esaminare e comprendere le [limitazioni,](#limitations)in quanto potrebbero influire sull'organizzazione.

## <a name="overview-of-cloud-consolidation"></a>Panoramica sul consolidamento del cloud

Il consolidamento di tutti gli utenti dall'ambiente locale al cloud in una singola organizzazione di Microsoft 365 o Office 365 può essere raggiunto per qualsiasi organizzazione con più distribuzioni di Skype for Business, purché siano soddisfatti i requisiti chiave seguenti:

- Deve essere coinvolta al massimo un'organizzazione di Microsoft 365 o Office 365. Il consolidamento in scenari con più organizzazioni non è supportato.
- In un determinato momento, solo una foresta di Skype for Business locale può essere in modalità ibrida (Spazio di indirizzi SIP condiviso). Tutte le altre foreste locali di Skype for Business devono rimanere locali (e presumibilmente federate tra loro). Si noti che queste altre  organizzazioni locali possono eseguire la sincronizzazione con AAD, se lo si desidera, con nuove funzionalità per disabilitare i domini [SIP online](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) disponibili a partire da dicembre 2018.

I clienti con distribuzioni di Skype for Business in più foreste devono eseguire la migrazione completa di tutti gli utenti di una singola foresta ibrida di Skype for Business singolarmente nell'organizzazione di Microsoft 365 o Office 365 utilizzando la funzionalità spazio di indirizzi SIP condiviso, quindi disabilitare la distribuzione ibrida con quella distribuzione locale, prima di passare alla migrazione della successiva distribuzione locale di Skype for Business. Prima di essere migrati nel cloud, gli utenti locali rimangono in uno stato federato con tutti gli utenti non rappresentati nella directory locale dello stesso utente.  

## <a name="canonical-example-of-cloud-consolidation"></a>Esempio canonico di consolidamento del cloud

Considerare un'organizzazione con due distribuzioni locali federate separate di Skype for Business che desidera consolidarle online in Microsoft Teams o Skype for Business online.


|Dettagli sullo stato originale |Dettagli sullo stato desiderato |
|---------|---------|
|<ul><li>2 distribuzioni locali di Skype for Business indipendenti in foreste AD separate<li>Al massimo una foresta è ibrida con Skype for Business online <li> Le organizzazioni sono federate tra loro <li>Gli utenti non vengono sincronizzati tra queste foreste<li> L'organizzazione potrebbe avere un'organizzazione di Microsoft 365 o Office 365 e potrebbe sincronizzare la directory con Azure AD</ul>|<ul> <li>1 organizzazione di Microsoft 365 o Office 365<li>Non ci sono più distribuzioni locali, quindi nessuna distribuzione ibrida rimanente<li>Tutti gli utenti locali sono ospitati in Skype for Business online e facoltativamente possono essere solo utenti di Teams <li>Nessun footprint locale di Skype for Business ovunque <li>Gli utenti hanno ancora l'autenticazione locale</ul> |

![Consolidamento di due distribuzioni locali federate separate](../media/cloudconsolidationfig1.png)  

I passaggi di base per andare dallo stato originale allo stato finale desiderato sono riportati di seguito.  Si noti che alcune organizzazioni potrebbero trovare che il punto di partenza si trova al centro di questi passaggi. Vedere [Altri punti di partenza](#other-starting-points)più avanti in questo articolo. Infine, in alcuni casi l'ordine può essere modificato in base alle necessità. [I vincoli chiave e le limitazioni](#limitations) sono descritti più avanti.

1.  Ottenere un'organizzazione di Microsoft 365 o Office 365, se non ne esiste ancora una.
2.  Assicurarsi che tutti i domini SIP pertinenti in entrambe le distribuzioni locali siano verificati nei domini di Microsoft 365 o Office 365.
3.  Scegliere una distribuzione di Skype for Business che sarà ibrida con Microsoft 365 o Office 365. In questo esempio verrà utilizzato OriginalCompany. <span> com.
4.  [Abilitare AAD Connect per la foresta che](configure-azure-ad-connect.md) diventerà ibrida (OriginalCompany. <span> com). 
5.  Se si introdurrà Teams nell'organizzazione, impostare i criteri a livello di tenant per [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy) su SfBWithTeamsCollab o una delle altre modalità SfB (SfBOnly o SfBWithTeamsCollabAndMeetings). Questo è fondamentale per garantire il routing delle chiamate e delle chat degli utenti che passano a Teams solo agli utenti che rimangono in locale.
6.  È consigliabile a questo punto (ma non ancora necessario fino al passaggio 11) abilitare [AAD Connect](cloud-consolidation-aad-connect.md) per l'altra foresta (AcquiredCompany. <span> com). Presupponendo che AAD Connect sia abilitato in entrambe le foreste, l'organizzazione sarà simile alla figura **[A,](#figure-a)** che potrebbe essere un punto di partenza comune per alcune organizzazioni. 
7.  Per tutti i domini SIP ospitati da altre distribuzioni locali (in questo caso, AcquiredCompany. <span> com), [disabilitare questi domini SIP in Skype for Business online](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) tramite `Disable-CsOnlineSipDomain` PowerShell. Si tratta di una nuova funzionalità a partire da dicembre 2018.
8.  [Configurare Skype for Business ibrido](configure-federation-with-skype-for-business-online.md) per OriginalCompany. <span> com (la distribuzione che ha ancora abilitato i domini SIP online).
9.  Nella distribuzione ibrida (OriginalCompany. <span> com), [iniziare a spostare](move-users-between-on-premises-and-cloud.md) gli utenti da Skype for Business locale al cloud (solo Teams) in modo che l'account sia disponibile in Skype for Business online. Ora l'organizzazione ha **[l'aspetto della figura B.](#figure-b)** Le modifiche principali rispetto alla figura A sono:
    - Gli utenti di entrambe le directory locali sono ora in AAD.
    - AcquiredCompany. <span> com è un dominio SIP online disabilitato.
    - Alcuni utenti sono stati spostati online in Skype for Business online o Teams. Vedere l'utente viola A.
10. Dopo aver spostato tutti gli utenti nel cloud, [disabilitare](cloud-consolidation-disabling-hybrid.md) l'ambiente ibrido con la distribuzione locale di Skype for Business per OriginalCompany. <span> com da Office 365:  
    - Disabilitare il dominio diviso nell'organizzazione di Microsoft 365 o Office 365.
    - Disabilitare la possibilità di comunicare con Microsoft 365 o Office 365 in OriginalCompany. <span> com locale.
    - Aggiornare i record DNS per OriginalCompany. <span> com per puntare a Microsoft 365 o Office 365.
11. Se non è già stato fatto, [abilitare AAD Connect per la](cloud-consolidation-aad-connect.md) foresta successiva che verrà ibrida (AcquiredCompany. <span> com). A questo punto, l'organizzazione è simile **[alla figura C.](#figure-c)** Questo può essere un altro punto di partenza comune per alcune organizzazioni. 
12. In PowerShell abilitare [i domini SIP](https://docs.microsoft.com/powershell/module/skype/enable-csonlinesipdomain) per la successiva distribuzione locale che verrà ibrida, AcquiredCompany. <span> com. Questa operazione viene eseguita utilizzando `Enable-CsOnlineSipDomain` , una nuova funzionalità disponibile a partire da dicembre 2018.
13. Se si utilizza la federazione chiusa, è necessario aggiungere eventuali domini SIP (ad esclusione di .microsoftonline.com) del tenant online puro come Domini consentiti nello stesso \* Microsoft 365 o Office 365.  Si noti che può richiedere del tempo prima che la modifica venga apportata e non vi sono danni nell'eseguire questa operazione in anticipo, quindi è consigliabile eseguire questa operazione con largo anticipo prima di passare al passaggio 14.
14. Aggiornare l'ambiente locale in modo che accetti eventuali domini SIP dal tenant online, in modo che corrispondano.
    - [Aggiornare](cloud-consolidation-edge-certificates.md) il nome di rete san in tutti i certificati perimetrali in modo che sia lo stesso valore di prima, più i valori per tutti i domini SIP online esistenti (ad eccezione di *.microsoftonline.com), in questo caso, Sip.OriginalCompany. <span> com.
    - Assicurarsi che OriginalCompany. <span> com è [un dominio consentito](https://docs.microsoft.com/powershell/module/skype/new-csalloweddomain) nella distribuzione locale, AcquiredCompany. Aggiungere domini consentiti.
15. [Abilitare Skype for Business ibrido](configure-federation-with-skype-for-business-online.md) tra AcquiredCompany locale. <span> com e il cloud.
16. Come desiderato, eseguire la migrazione degli utenti [dall'ambiente locale al cloud.](move-users-between-on-premises-and-cloud.md) È possibile eseguire la migrazione degli utenti direttamente in [modalità Solo Teams](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) oppure è possibile eseguirne prima la migrazione in Skype for Business online. Durante questo stato, l'organizzazione è simile **[alla figura D.](#figure-d)**
17. Dopo aver eseguito la migrazione di tutti gli utenti, [disabilitare](cloud-consolidation-disabling-hybrid.md) l'ambiente ibrido con l'ambiente locale per *rendere l'organizzazione cloud pura.*

I diagrammi seguenti mostrano la configurazione in vari punti chiave durante questo processo.

##### <a name="figure-a"></a>Figura A:

- Entrambe le organizzazioni vengono sincronizzate tramite AAD Connect, quindi AAD ora include tutti gli utenti di entrambe le distribuzioni locali.
- Tutti gli utenti ospitati in locale.  
- Skype for Business Ibrido *non è* ancora configurato.
- Se gli utenti in entrambe le distribuzioni usano Teams, non potranno attuare la federazione tra loro (o con alcuna organizzazione) né avranno interoperabilità con gli utenti di Skype for Business. In questa fase, Microsoft consiglia di usare Teams solo per i canali.<br><br>
    ![Figura A diagramma](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figura B:

- AcquiredCompany. <span> com è un [dominio](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) SIP online disabilitato. Tutti gli utenti sono locali. Se usano Teams, non hanno federazione o interoperabilità. In questa fase, Microsoft consiglia di usare Teams solo per i canali.
- Skype for Business Ibrido è stato abilitato per una delle organizzazioni locali.
- Alcuni utenti nell'organizzazione ibrida sono stati spostati nel cloud (come indicato dall'ombreggiatura viola). Questi utenti possono essere utenti di Skype for Business online o solo utenti di Teams con supporto completo per l'interoperabilità e la federazione.<br><br>
    ![Diagramma della figura B](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figura C:

- Tutti gli utenti di OriginalCompany. <span> com sono ora nel cloud (disponibile in Skype for Business online). È consigliabile che siano anche solo Teams.
- Configurazione ibrida di Skype for Business con OriginalCompany. <span> la distribuzione com è stata disabilitata. La distribuzione locale non è più disponibile.
- Se AcquiredCompany. <span> com non era precedentemente sincronizzato con AAD, per continuare da qui deve essere sincronizzato ora. Tuttavia, non è ancora ibrido (spazio di indirizzi SIP condiviso) e fino a quando l'organizzazione non è pronta per passare alla distribuzione ibrida, il dominio SIP online per l'organizzazione locale pura (AcquiredCompany.com) deve rimanere disabilitato, in modo che gli utenti di Teams online possano comunicare con gli utenti locali.<br><br>
    ![Figura C](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figura D:

- AcquiredCompany. <span> com è ora abilitato come dominio SIP online.
- L'ambiente locale viene aggiornato per accettare OriginalCompany. <span> com. Vengono aggiornati sia i certificati di dominio consentito che i certificati perimetrali.
- Lo spazio di indirizzi SIP condiviso è abilitato tra AcquiredCompany. <span> com e l'organizzazione di Microsoft 365 o Office 365.
- Alcuni utenti nell'organizzazione ibrida potrebbero essere stati spostati nel cloud, ad esempio l'utente D di seguito (indicato da un'ombreggiatura viola).<br><br>
    ![Diagramma della figura D](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Altri punti di partenza

I passaggi nell'esempio canonico precedente presuppongono che l'organizzazione inizi con due distribuzioni locali federate senza presenza di Microsoft o Office 365. Tuttavia, alcune organizzazioni potrebbero avere un footprint di Microsoft 365 o Office 365 esistente e possono esserci punti di ingresso diversi nella sequenza precedente. Esistono quattro configurazioni tipiche:

- Più organizzazioni locali federate senza organizzazione di Microsoft 365 o Office 365. In questo caso, iniziare dal passaggio 1.
- Più organizzazioni locali federate che stanno già sincronizzando più foreste di Skype for Business in un singolo tenant di Azure AD. Tale organizzazione è simile all'ipotetica organizzazione nella figura A, che ha completato i passaggi da 1 a 6 e deve iniziare dal passaggio 7.
- Un'organizzazione ibrida che esegue la federazione con 1 o più organizzazioni locali pure, nessuna delle quali viene sincronizzata con AAD. Tale organizzazione sarebbe simile all'ipotetica organizzazione nella **figura E,** illustrata di seguito.
    - Questa organizzazione è simile alla figura B, che ha completato i passaggi da 1 a 9, ad eccezione di:
        - Le distribuzioni non ibride di Skype for Business *NON* sono ancora sincronizzate con Azure AD.
        -  I domini SIP online non sono ancora disabilitati. 
    - Queste organizzazioni devono:
        - Completare la migrazione dell'organizzazione ibrida esistente e immettere la sequenza precedente al passaggio 10.  OPPURE
        - Se si desidera sincronizzare qualsiasi altra foresta Skype for Business in AAD prima di completare la migrazione dell'organizzazione ibrida, l'organizzazione deve eseguire il passaggio 7 (disabilitare tutti i domini SIP online in qualsiasi altra distribuzione locale di Skype for Business che verrà sincronizzata in AAD) e quindi abilitare AAD Connect e procedere solo con il passaggio 10 (rimuovere le autorizzazioni per la distribuzione ibrida originale).       
                **Figura E**<br>
                ![Figura E](../media/cloudconsolidationfige.png)
- Un'organizzazione Skype for Business online pura (che potrebbe o meno usare Teams) che federata con un'organizzazione Skype for Business locale separata. Una volta che questa organizzazione disabilita il dominio SIP online per l'organizzazione locale e abilita AAD Connect per l'organizzazione Skype for Business locale, è simile all'ipotetica organizzazione illustrata nella figura **[C](#figure-c)** che ha completato i passaggi da 1 a 11.

## <a name="limitations"></a>Limitazioni

- Deve essere coinvolta al massimo un'organizzazione di Microsoft 365 o Office 365. Il consolidamento in scenari con più organizzazioni non è supportato.
- Solo una foresta di Skype for Business locale può essere in modalità ibrida (spazio di indirizzi SIP condiviso) alla volta. Tutte le altre foreste di Skype for Business locali devono rimanere esclusivamente locali e devono essere federate tra loro e con l'organizzazione di Microsoft 365 o Office 365.
- Prima di essere migrati nel cloud, esiste un'esperienza asimmetrica per gli utenti in questa distribuzione, perché non tutti gli utenti online sono rappresentati in locale:
    - L'esperienza può essere sommata come segue:
        - Tutti gli utenti ospitati online interagiranno con gli utenti locali nell'ambiente ibrido come se l'utente fosse ibrido.
        - Gli utenti locali nella distribuzione ibrida interagiranno con gli utenti online rappresentati nella directory locale come se fossero ibridi. 
        - Gli utenti locali nella distribuzione ibrida interagiranno con gli utenti online che non sono rappresentati in Active Directory locale come federati.
    - Nella **[figura D](#figure-d)** sopra, l'utente E è locale in AcquiredCompany. <span> com.  L'utente E interagirà con l'utente D (disponibile online) utilizzando l'esperienza ibrida standard, ma l'utente E avrà un'esperienza federata con gli utenti A, B e C perché non sono rappresentati nella directory locale. Tuttavia, gli utenti A, B e C interagiranno con l'utente E come se l'utente fosse in ambiente ibrido.
    - Implicazioni dell'interazione tra ibrido e federazione:
        - La presenza non viene sottoscritta automaticamente per gli utenti federati, a meno che l'utente non sia contrassegnato come contatto.
        - L'inoltro di chiamata non funziona tra domini federati.
        - Gli scenari di trasferimento delle chiamate sono più limitati.
        - La limitazione può essere applicata al traffico federato.
- Data questa esperienza asimmetrica, il supporto ufficiale per la funzionalità di chiamata in scenari cross-premise tra un utente locale e un utente cloud che non si trova nella directory locale è limitato al solo peer-to-peer. 
    - L'inoltro di chiamata, il trasferimento, le code di chiamata e così via tra questi utenti non è supportato.
    - Questi scenari di chiamata non supportati verranno comunque visualizzati abilitati, ma in molti casi avranno esito negativo in modi imprevedibili. 
    - Nella **[figura D](#figure-d)** precedente, l'utente E è locale e le chiamate con utenti A, B o C saranno supportate solo come peer-to-peer. Le chiamate con l'utente D non presentano limitazioni di supporto.  Tuttavia, dopo che l'utente locale E è stato spostato nel cloud, questa restrizione non si applica più.
- Se nell'ambiente sono presenti più distribuzioni di Skype for Business Server 2019, solo 1 di queste distribuzioni può essere configurata per l'uso di Organizational Operatore automatico, poiché tale funzionalità richiede la configurazione ibrida di Skype for Business Server. 
- È possibile modificare l'ordine di alcuni dei passaggi precedenti. Il requisito fondamentale che deve essere soddisfatto è che, se tutte queste condizioni sono vere:
    - Più di una foresta di Skype for Business locale sincronizzata con un singolo tenant AAD
    - Il dominio diviso è abilitato con una foresta locale
    - Almeno un utente nell'organizzazione ibrida è stato migrato nel cloud<br>   Quindi, *è necessario* disabilitare tutti gli altri domini SIP online da qualsiasi altra foresta di Skype for Business locale. In caso contrario, la federazione tra gli utenti online nell'organizzazione ibrida e gli utenti locali in altre organizzazioni si interromperà in una direzione.

## <a name="implications"></a>Implicazioni

- Poiché esistono limitazioni nel supporto per la funzionalità di chiamata avanzata come descritto in precedenza, le organizzazioni devono considerare questi stati asimmetrici come transitori come parte della migrazione e non perseguirli come **stato stabile.**  
- Le organizzazioni con più distribuzioni locali di Skype for Business devono in genere iniziare con una distribuzione che può essere completamente migrata nel cloud, in modo che il consolidamento possa continuare. Si è compreso che in alcuni casi saranno presenti blocchi di determinati gruppi di utenti per i quali non è ancora possibile passare a Teams. Quando si tratta di una considerazione in scenari che coinvolgono più foreste skype for Business, iniziare la migrazione con un'altra foresta che non presenta queste limitazioni, se possibile.
- Quando si passa dall'ambiente locale al cloud, gli utenti che dispongono di relazioni di delega e/o sono in genere coinvolti in scenari di inoltro di chiamata devono essere spostati insieme come un'unità.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Considerazioni per il passaggio alla modalità Solo Teams

Quando si spostano gli utenti dall'ambiente locale al cloud in un ambiente ibrido, è possibile spostarli in modalità Solo Skype for Business o TeamsOnly. *Se si prevede di spostare gli utenti in modalità Solo Teams, leggere prima questa sezione.*

- Quando si assegna la modalità Solo Teams a un utente, tutte le chat e le chiamate di qualsiasi altro utente verranno atterrerà nel client Teams dell'utente. 
- Se gli utenti con Skype for Business locale usano principalmente il client Skype for Business e non Teams, prendere in considerazione l'impostazione di TeamsUpgradePolicy in modo che il routing a tali utenti locali sia sempre in Skype for Business invece che in Teams. Per garantire un routing corretto delle chat e delle chiamate tra utenti che sono solo Teams e utenti che usano ancora Skype for Business in locale, gli utenti locali devono avere un valore effettivo di TeamsUpgradePolicy con una delle modalità SfB, anziché Islands (impostazione predefinita). 
    - A tale scopo, è necessario innanzitutto impostare l'istanza globale del *tenant di TeamsUpgradePolicy su uno di questi valori:*
        - SfBWithTeamsCollab (scelta consigliata)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - È possibile concedere criteri a livello di tenant usando questo comando:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Nota: è necessario eseguire questa operazione a livello di tenant perché i criteri non possono essere assegnati a singoli utenti che non dispongono di un indirizzo SIP nella directory online. Anche se sono stati disabilitati i domini SIP online per le distribuzioni locali pure, gli utenti di tali domini non diservino indirizzi SIP nella directory online da progettazione. Di conseguenza, l'unico modo per applicare i criteri agli utenti locali è l'assegnazione a livello di tenant. Al contrario, nella distribuzione ibrida gli utenti avranno un indirizzo SIP nella directory online in modo che possano essere assegnati esplicitamente a un criterio se si desidera che abbia un valore diverso rispetto al criterio globale del tenant.
- L'esperienza utente client di Teams non rispetta ancora le modalità SfB di TeamsUpgradePolicy. Ad esempio, in queste modalità, l'avvio di chiamate e chat in Teams è attualmente possibile, anche se in futuro non sarà così. Questo può causare confusione tra gli utenti, perché a volte le risposte possono attersi in Teams e a volte Skype for Business, a seconda delle circostanze. È consigliabile disabilitare separatamente le chiamate e le chat tramite TeamsMessagingPolicy e TeamsCallingPolicy per gli utenti ancora in locale.

## <a name="see-also"></a>Vedere anche

[Aggiornare il certificato perimetrale](cloud-consolidation-edge-certificates.md)

[Aggiornare AAD Connect per includere più di una foresta](cloud-consolidation-aad-connect.md)

[Disabilitare la soluzione ibrida per completare la migrazione al cloud](cloud-consolidation-disabling-hybrid.md)
