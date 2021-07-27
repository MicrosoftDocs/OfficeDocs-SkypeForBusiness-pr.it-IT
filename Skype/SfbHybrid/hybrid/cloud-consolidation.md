---
title: Consolidamento cloud per Teams e Skype for Business
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
description: In questo articolo viene descritto come ottenere tale consolidamento per le organizzazioni con distribuzioni locali di Skype for Business (o Lync) che desiderano spostare il carico di lavoro uc a Teams e/o Skype for Business Online.
ms.openlocfilehash: 6a6d433be8b6be5519f1bf7576464603e29ee41b
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510727"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidamento del cloud per Teams e Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Molte grandi aziende hanno più di una foresta di Active Directory locale e, in alcuni casi, i clienti hanno più di una distribuzione di Exchange e/o Skype for Business Server (o Lync Server). Inoltre, anche le organizzazioni con una sola foresta locale potrebbero trovarsi nella stessa situazione con un'acquisizione o una fusione aziendale. Quando questi clienti passano al cloud, desiderano consolidare le più istanze di un determinato carico di lavoro locale nel cloud in una singola Microsoft 365 o Office 365 organizzazione. In questo articolo viene descritto come ottenere tale consolidamento per le organizzazioni con più distribuzioni locali di Skype for Business (o Lync) che desiderano spostare il carico di lavoro per le comunicazioni unificate nel cloud Microsoft, ad esempio, Microsoft Teams e/o Skype for Business Online.

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

In passato, sono state fornite indicazioni per i clienti che si trovavano in questa situazione che volevano consolidare le distribuzioni locali per poi passare al cloud. Sebbene questa sia ancora un'opzione, in questo articolo viene descritta una soluzione basata su nuove funzionalità che consente alle organizzazioni con più distribuzioni di Skype for Business di eseguire la migrazione di una distribuzione alla volta in una singola organizzazione di Microsoft 365 o Office 365, senza eseguire il consolidamento locale. Anche con questa nuova funzionalità, Skype for Business Online e Microsoft Teams non supportano più foreste di Skype for Business/Lync in modalità ibrida con una singola Microsoft 365 o Office 365 organizzazione. 

> [!Important]
> Prima di usare questa guida per la configurazione, assicurarsi di esaminare e comprendere le [limitazioni](#limitations), in quanto potrebbero influire sull'organizzazione.

## <a name="overview-of-cloud-consolidation"></a>Panoramica sul consolidamento del cloud

Il consolidamento di tutti gli utenti dall'ambiente locale al cloud in un'unica organizzazione Microsoft 365 o Office 365 può essere raggiunto per qualsiasi organizzazione con più distribuzioni di Skype for Business, purché siano soddisfatti i requisiti chiave seguenti:

- Deve essere coinvolta al massimo Microsoft 365 o Office 365'organizzazione. Il consolidamento in scenari con più organizzazioni non è supportato.
- In un determinato momento, solo una foresta di Skype for Business locale può essere in modalità ibrida (Spazio di indirizzi SIP condiviso). Tutte le altre foreste locali di Skype for Business devono rimanere locali (e presumibilmente federate tra loro). Si noti che queste altre  organizzazioni locali possono eseguire la sincronizzazione con AAD se lo si desidera con nuove funzionalità per disabilitare i domini [SIP online](/powershell/module/skype/disable-csonlinesipdomain) disponibili a partire da dicembre 2018.

I clienti con distribuzioni di Skype for Business in più foreste devono eseguire la migrazione completa di tutti gli utenti di una singola foresta di Skype for Business ibrida singolarmente nell'organizzazione di Microsoft 365 o Office 365 utilizzando la funzionalità Spazio indirizzi SIP condiviso e quindi disabilitare la distribuzione ibrida con quella distribuzione locale, prima di passare alla migrazione della successiva distribuzione di Skype for Business locale. Prima di essere migrati nel cloud, gli utenti locali rimangono in uno stato federato con tutti gli utenti non rappresentati nella directory locale dello stesso utente.  

## <a name="canonical-example-of-cloud-consolidation"></a>Esempio canonico di consolidamento cloud

Prendere in considerazione un'organizzazione con due distribuzioni locali federate separate di Skype for Business che desidera consolidarle online in Microsoft Teams o Skype for Business Online.


|Dettagli sullo stato originale |Dettagli sullo stato desiderato |
|---------|---------|
|<ul><li>2 distribuzioni Skype for Business locali in foreste AD separate<li>Al massimo 1 foresta è ibrida con Skype for Business Online <li> Le organizzazioni sono federate tra loro <li>Gli utenti non vengono sincronizzati tra queste foreste<li> L'organizzazione potrebbe avere un'Microsoft 365 o Office 365 e potrebbe sincronizzare la directory in Azure AD</ul>|<ul> <li>1 Microsoft 365 o Office 365 organizzazione<li>Non più distribuzioni locali, quindi nessuna distribuzione ibrida rimanente<li>Tutti gli utenti locali sono ospitati in Skype for Business Online e facoltativamente possono essere Teams solo utenti <li>Nessun footprint locale di Skype for Business ovunque <li>Gli utenti hanno ancora l'autenticazione locale</ul> |

![Consolidamento di due distribuzioni locali federate separate](../media/cloudconsolidationfig1.png)  

Di seguito sono riportati i passaggi di base da eseguire dallo stato originale allo stato finale desiderato.  Si noti che alcune organizzazioni potrebbero trovare che il punto di partenza si trova in un punto intermedio di questi passaggi. Vedere [Altri punti di partenza](#other-starting-points)più avanti in questo articolo. Infine, in alcuni casi l'ordine può essere modificato in base alle necessità. [I vincoli e le limitazioni chiave sono](#limitations) descritti più avanti.

1.  Ottenere un'Microsoft 365 o Office 365 organizzazione se non ne esiste ancora una.
2.  Assicurarsi che tutti i domini SIP pertinenti in entrambe le distribuzioni locali siano verificati Microsoft 365 o Office 365 domini.
3.  Selezionare una Skype for Business distribuzione ibrida con Microsoft 365 o Office 365. In questo esempio useremo OriginalCompany. <span> com.
4.  [Abilitare il Connessione AAD per la foresta](configure-azure-ad-connect.md) che diventerà prima ibrida (OriginalCompany. <span> com). 
5.  Se si introdurrà Teams nell'organizzazione, impostare i criteri a livello di tenant per [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy) su SfBWithTeamsCollab o su una delle altre modalità SfB (SfBOnly o SfBWithTeamsCollabAndMeetings). Questo è fondamentale per garantire l'instradamento di chiamate e chat da parte di utenti che si spostano a Teams Solo agli utenti che rimangono in locale.
6.  È consigliabile a questo punto (ma non ancora necessario fino al passaggio 11) abilitare [AAD Connessione per](cloud-consolidation-aad-connect.md) l'altra foresta (AcquiredCompany. <span> com). Presupponendo che la Connessione AAD sia abilitata in entrambe le foreste, l'organizzazione sarà simile alla figura **[A](#figure-a)**, che potrebbe essere un punto di partenza comune per alcune organizzazioni. 
7.  Per tutti i domini SIP ospitati da altre distribuzioni locali (in questo caso, AcquiredCompany. <span> com), [disabilitare questi domini SIP in Skype for Business Online](/powershell/module/skype/disable-csonlinesipdomain) tramite `Disable-CsOnlineSipDomain` PowerShell. Si tratta di una nuova funzionalità a partire da dicembre 2018.
8.  [Configurare Skype for Business ibrido](configure-federation-with-skype-for-business-online.md) per OriginalCompany. <span> com (la distribuzione che ha ancora abilitato i domini SIP online).
9.  Nella distribuzione ibrida (OriginalCompany. <span> com), iniziare a spostare gli utenti da Skype for Business locale al [cloud](move-users-between-on-premises-and-cloud.md) (solo Teams) in modo che l'account sia disponibile in Skype for Business Online. Ora l'organizzazione è simile **[alla figura B](#figure-b)**. Le modifiche principali della figura A sono:
    - Gli utenti di entrambe le directory locali sono ora in AAD.
    - AcquiredCompany. <span> com è un dominio SIP online disabilitato.
    - Alcuni utenti sono stati spostati online in Skype for Business Online o Teams. (Vedere utente viola A.)
10. Dopo aver spostato tutti gli utenti nel cloud, [disabilitare](cloud-consolidation-disabling-hybrid.md) l'ambiente ibrido Skype for Business distribuzione locale per OriginalCompany. <span> com from Office 365:  
    - Disabilitare il dominio diviso nell'Microsoft 365 o Office 365 organizzazione.
    - Disabilitare la possibilità di comunicare con Microsoft 365 o Office 365 in OriginalCompany. <span> com locale.
    - Aggiornare i record DNS per OriginalCompany. <span> com per puntare a Microsoft 365 o Office 365.
11. Se non è già stato fatto, abilitare [AAD Connessione](cloud-consolidation-aad-connect.md) per la foresta successiva che verrà ibrida (AcquiredCompany. <span> com). A questo punto, l'organizzazione è simile **[alla figura C](#figure-c)**. Questo può essere un altro punto di partenza comune per alcune organizzazioni. 
12. In PowerShell abilitare [i domini SIP per la](/powershell/module/skype/enable-csonlinesipdomain) successiva distribuzione locale che verrà ibrida, AcquiredCompany. <span> com. Questa operazione viene eseguita utilizzando `Enable-CsOnlineSipDomain` , che è una nuova funzionalità disponibile a partire da dicembre 2018.
13. Se si utilizza la federazione chiusa, è necessario aggiungere eventuali domini SIP (ad esclusione di .microsoftonline.com) del tenant online puro come Domini consentiti nello stesso Microsoft 365 o \* Office 365.  Tieni presente che può essere necessario del tempo prima che la modifica venga apportata e non vi è alcun danno nell'eseguire questa operazione in anticipo, quindi ti consigliamo di eseguire questa operazione con largo anticipo prima di passare al passaggio 14.
14. Aggiornare l'ambiente locale in modo che accetti eventuali domini SIP dal tenant online, in modo che corrispondano.
    - [Aggiornare la](cloud-consolidation-edge-certificates.md) san in tutti i certificati perimetrali in modo che sia lo stesso valore di prima, più i valori per tutti i domini SIP online esistenti (ad eccezione di *.microsoftonline.com), in questo caso Sip.OriginalCompany. <span> com.
    - Assicurati che OriginalCompany. <span> com è [un dominio consentito](/powershell/module/skype/new-csalloweddomain) nella distribuzione locale, AcquiredCompany. Aggiungere domini consentiti.
15. [Abilitare Skype for Business ibrido](configure-federation-with-skype-for-business-online.md) tra AcquiredCompany locale. <span> com e il cloud.
16. Come desiderato, [eseguire la migrazione degli utenti da locale al cloud](move-users-between-on-premises-and-cloud.md). È possibile eseguire la migrazione degli utenti direttamente in [modalità TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) oppure è possibile eseguirne prima la migrazione a Skype for Business Online. Durante questo stato, l'organizzazione è simile **[alla figura D](#figure-d)**.
17. Dopo aver eseguito la migrazione di tutti gli utenti, [disabilitare](cloud-consolidation-disabling-hybrid.md) l'ambiente ibrido con l'ambiente locale per *rendere l'organizzazione cloud pura.*

I diagrammi seguenti mostrano la configurazione in vari punti chiave durante questo processo.

##### <a name="figure-a"></a>Figura A:

- Entrambe le organizzazioni vengono sincronizzate tramite Connessione AAD, quindi AAD ora include tutti gli utenti di entrambe le distribuzioni locali.
- Tutti gli utenti ospitati in locale.  
- Skype for Business Hybrid *non è ancora* configurato.
- Se gli utenti in una delle due distribuzioni usano Teams, non saranno in grado di eseguire la federazione tra loro (o con qualsiasi organizzazione), né avranno interoperabilità con gli Skype for Business utenti. In questa fase, Microsoft consiglia di usare Teams solo per i canali.<br><br>
    ![Figura Diagramma](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figura B:

- AcquiredCompany. <span> com è un [dominio](/powershell/module/skype/disable-csonlinesipdomain) SIP online disabilitato. Tutti gli utenti sono locali. Se usano Teams non hanno federazione o interoperabilità. In questa fase, Microsoft consiglia di usare Teams solo per i canali.
- Skype for Business Hybrid è stato abilitato per una delle organizzazioni locali.
- Alcuni utenti nell'organizzazione ibrida sono stati spostati nel cloud (utente A come indicato dallo shading viola). Questi utenti possono essere utenti Skype for Business online o Teams solo utenti con supporto completo per l'interoperabilità e la federazione.<br><br>
    ![Figura B diagramma](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figura C:

- Tutti gli utenti di OriginalCompany. <span> com sono ora nel cloud (ospitati in Skype for Business Online). È consigliabile che siano anche Teams solo.
- Skype for Business configurazione ibrida con OriginalCompany. <span> la distribuzione com è stata disabilitata. La distribuzione locale non è più disponibile.
- Se AcquiredCompany. <span> com non era in precedenza sincronizzato con AAD, per continuare da qui deve essere sincronizzato ora. Tuttavia, non è ancora ibrido (spazio di indirizzi SIP condiviso) e fino a quando l'organizzazione non è pronta per passare alla distribuzione ibrida, il dominio SIP online per l'organizzazione locale pura (AcquiredCompany.com) deve rimanere disabilitato, in modo che gli utenti di Teams online possano comunicare con gli utenti locali.<br><br>
    ![Figura C diagramma](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figura D:

- AcquiredCompany. <span> com è ora abilitato come dominio SIP online.
- L'ambiente locale viene aggiornato per accettare OriginalCompany. <span> com. Vengono aggiornati sia il dominio consentito che i certificati perimetrali.
- Lo spazio di indirizzi SIP condiviso è abilitato tra AcquiredCompany. <span> com e Microsoft 365 o Office 365 organizzazione.
- Alcuni utenti dell'organizzazione ibrida potrebbero essere stati spostati nel cloud, ad esempio l'utente D di seguito (indicato da uno shading viola).<br><br>
    ![Figura D diagramma](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Altri punti di partenza

I passaggi nell'esempio canonico precedente presuppongono che l'organizzazione inizi con due distribuzioni locali federate senza presenza di Microsoft o Office 365 locale. Tuttavia, alcune organizzazioni potrebbero avere un footprint Microsoft 365 o Office 365 esistente e possono esserci diversi punti di ingresso nella sequenza precedente. Esistono quattro configurazioni tipiche:

- Più organizzazioni locali federate senza Microsoft 365 o Office 365 organizzazione. In questo caso, iniziare dal passaggio 1.
- Più organizzazioni locali federate che stanno già sincronizzando più foreste Skype for Business in un singolo tenant di Azure AD. Tale organizzazione è simile all'organizzazione ipotetica nella figura A, che ha completato i passaggi da 1 a 6 e deve iniziare dal passaggio 7.
- Un'organizzazione ibrida federata con 1 o più organizzazioni locali pure, nessuna delle quali viene sincronizzata con AAD. Tale organizzazione sarebbe simile all'organizzazione ipotetica nella **figura E**, illustrata di seguito.
    - Questa organizzazione è simile alla figura B, che ha completato i passaggi da 1 a 9, ad eccezione di:
        - Le distribuzioni Skype for Business non ibride *NON* sono ancora sincronizzate con Azure AD.
        -  I domini SIP online non sono ancora disabilitati. 
    - Queste organizzazioni devono:
        - Completare la migrazione dell'organizzazione ibrida esistente e immettere la sequenza precedente al passaggio 10.  OR,
        - Se si desidera sincronizzare qualsiasi altra foresta di Skype for Business in AAD prima di completare la migrazione dell'organizzazione ibrida, l'organizzazione deve eseguire il passaggio 7 (disabilitare tutti i domini SIP online in qualsiasi altra distribuzione di Skype for Business locale che verrà sincronizzata in AAD) e quindi abilitare AAD Connessione e procedere solo con il passaggio 10 (rimuovere la distribuzione ibrida originale).       
                **Figura E**<br>
                ![Figura E diagramma](../media/cloudconsolidationfige.png)
- Un'Skype for Business Online pura (che potrebbe o meno usare Teams) che si federata con un'organizzazione di Skype for Business locale separata. Una volta che l'organizzazione disabilita il dominio SIP online per l'organizzazione locale e abilita AAD Connessione per l'organizzazione Skype for Business locale, è simile all'organizzazione ipotetica illustrata nella figura **[C](#figure-c)** che ha completato i passaggi da 1 a 11.

## <a name="limitations"></a>Limitazioni

- Deve essere coinvolta al massimo Microsoft 365 o Office 365'organizzazione. Il consolidamento in scenari con più organizzazioni non è supportato.
- Solo una foresta Skype for Business locale può essere in modalità ibrida (spazio di indirizzi SIP condiviso) alla volta. Tutte le altre foreste Skype for Business locali devono rimanere puramente locali e devono essere federate tra loro e con l'organizzazione Microsoft 365 o Office 365 locale.
- Prima di essere migrati nel cloud, esiste un'esperienza asimmetrica per gli utenti in questa distribuzione, perché non tutti gli utenti online sono rappresentati in locale:
    - L'esperienza può essere riassunta come segue:
        - Tutti gli utenti ospitati online interagiranno con gli utenti locali nell'ambiente ibrido come se l'utente fosse ibrido.
        - Gli utenti locali nella distribuzione ibrida interagiranno con gli utenti online rappresentati nella directory locale come se fossero ibridi. 
        - Gli utenti locali nella distribuzione ibrida interagiranno con gli utenti online che non sono rappresentati in Active Directory locale come federati.
    - Nella **[figura D](#figure-d)** sopra, l'utente E è locale in AcquiredCompany. <span> com.  L'utente E interagirà con l'utente D (disponibile online) utilizzando l'esperienza ibrida standard, ma l'utente E avrà un'esperienza federata con gli utenti A, B e C perché non sono rappresentati nella directory locale. Tuttavia, gli utenti A, B e C interagiranno con l'utente E come se l'utente fosse ibrido.
    - Implicazioni dell'interazione tra ibrido e federazione:
        - La presenza non viene sottoscritta automaticamente per gli utenti federati a meno che l'utente non sia contrassegnato come contatto.
        - L'inoltro di chiamata non funziona tra domini federati.
        - Gli scenari di trasferimento delle chiamate sono più limitati.
        - La limitazione può essere applicata al traffico federato.
- Data questa esperienza asimmetrica, il supporto ufficiale per la funzionalità di chiamata in scenari cross-premise tra un utente locale e un utente cloud che non si trova nella directory locale è limitato al solo peer-to-peer. 
    - L'inoltro di chiamata, il trasferimento, le code di chiamata e così via tra questi utenti non è supportato.
    - Questi scenari di chiamata non supportati verranno comunque visualizzati abilitati, ma in molti casi avranno esito negativo in modi imprevedibili. 
    - Nella **[figura D](#figure-d)** precedente, l'utente E è locale e le chiamate con utenti A, B o C saranno supportate solo come peer-to-peer. Le chiamate con l'utente D non presentano limitazioni di supporto.  Tuttavia, dopo che l'utente locale E è stato spostato nel cloud, questa restrizione non si applica più.
- Se nell'ambiente sono presenti più distribuzioni di Skype for Business Server 2019, solo 1 di tali distribuzioni può essere configurata per l'utilizzo di Organizational Operatore automatico, poiché tale funzionalità richiede una configurazione ibrida Skype for Business Server. 
- L'ordine di alcuni dei passaggi precedenti può essere modificato. Il requisito fondamentale che deve essere soddisfatto è che, se tutte queste condizioni sono vere:
    - Più di una foresta locale Skype for Business sincronizzazione con un singolo tenant AAD
    - Il dominio diviso è abilitato con una foresta locale
    - Almeno un utente nell'organizzazione ibrida è stato migrato nel cloud<br>   È quindi *necessario disabilitare* tutti gli altri domini SIP online da qualsiasi altra foresta Skype for Business locale. In caso contrario, la federazione tra gli utenti online nell'organizzazione ibrida e gli utenti locali in altre organizzazioni si interromperà in una direzione.

## <a name="implications"></a>Implicazioni

- Poiché esistono limitazioni nel supporto per la funzionalità di chiamata avanzata come descritto in precedenza, le organizzazioni devono considerare questi stati asimmetrici come transitori come parte della migrazione e non perseguirli come **stato fisso.**  
- Le organizzazioni con più distribuzioni Skype for Business locali in genere devono iniziare con una distribuzione che può essere migrata completamente nel cloud, in modo che il consolidamento possa continuare. Si è compreso che in alcuni casi saranno presenti blocchi di determinati gruppi di utenti per i quali non è ancora possibile passare a Teams. Quando si tratta di una considerazione negli scenari che coinvolgono più foreste Skype for Business, iniziare la migrazione con un'altra foresta che non presenta queste limitazioni, se possibile.
- Quando si passa da locale al cloud, gli utenti che hanno relazioni di delega e/o sono in genere coinvolti in scenari di inoltro di chiamata devono essere spostati insieme come unità.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Considerazioni per il passaggio alla modalità TeamsOnly

Quando si spostano gli utenti dall'ambiente locale al cloud in un ambiente ibrido, è possibile spostarli in modalità Solo Skype for Business Teams o TeamsOnly. *Se si prevede di spostare gli utenti in modalità TeamsOnly, leggere prima questa sezione.*

- Quando assegni la modalità TeamsOnly a un utente, tutte le chat e le chiamate di qualsiasi altro utente verranno atterrato nel client Teams utente. 
- Se gli utenti con Skype for Business locale usano principalmente un client Skype for Business e non Teams, è consigliabile impostare TeamsUpgradePolicy in modo che il routing a tali utenti locali si snomenti sempre in Skype for Business anziché Teams. Per garantire un routing corretto delle chat e delle chiamate tra gli utenti che sono TeamsOnly e gli utenti che usano ancora Skype for Business in locale, gli utenti locali devono avere un valore effettivo di TeamsUpgradePolicy con una delle modalità SfB, anziché Islands (impostazione predefinita). 
    - A tale scopo, è necessario innanzitutto impostare l'istanza globale del *tenant di TeamsUpgradePolicy su uno dei valori seguenti:*
        - SfBWithTeamsCollab (scelta consigliata)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - È possibile concedere criteri a livello di tenant usando questo comando:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Nota: è necessario eseguire questa operazione a livello di tenant perché i criteri non possono essere assegnati a singoli utenti che non dispongono di un indirizzo SIP nella directory online. Anche se sono stati disabilitati i domini SIP online per le distribuzioni locali pure, gli utenti di tali domini non disentendono gli indirizzi SIP nella directory online in base alla progettazione. Di conseguenza, l'unico modo per applicare i criteri a tali utenti locali è l'assegnazione a livello di tenant. Al contrario, nella distribuzione ibrida gli utenti avranno un indirizzo SIP nella directory online in modo che possano essere assegnati in modo esplicito a un criterio se si desidera che abbia un valore diverso rispetto al criterio globale del tenant.
- L Teams'esperienza utente del client non rispetta ancora le modalità SfB di TeamsUpgradePolicy. Ad esempio, quando in queste modalità, l'avvio di chiamate e chat in Teams è attualmente possibile, anche se in futuro non sarà così. Ciò può causare confusione tra gli utenti, perché a volte le risposte possono Teams e a volte Skype for Business, a seconda delle circostanze. È consigliabile disabilitare separatamente le chiamate e le chat tramite TeamsMessagingPolicy e TeamsCallingPolicy per gli utenti ancora in locale.

## <a name="see-also"></a>Vedere anche

[Aggiornare il certificato perimetrale](cloud-consolidation-edge-certificates.md)

[Aggiornare AAD Connect per includere più di una foresta](cloud-consolidation-aad-connect.md)

[Disabilitare la soluzione ibrida per completare la migrazione al cloud](cloud-consolidation-disabling-hybrid.md)