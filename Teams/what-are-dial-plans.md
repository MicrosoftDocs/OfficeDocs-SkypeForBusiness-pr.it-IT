---
title: Che cosa sono i piani di chiamata?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: "Informazioni sul tipo di piani per chiamate telefoniche (piani di chiamata PSTN) disponibili con Teams e su come sceglierne uno per l'organizzazione.  "
ms.openlocfilehash: adb5f46296423b6339c62029d27111345c2fd646
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460816"
---
# <a name="what-are-dial-plans"></a>Che cosa sono i piani di chiamata?

[] Un piano di chiamata è un insieme denominato di regole di normalizzazione che traducono i numeri di telefono composti da un singolo utente in un formato alternativo (in genere E.164) per l'autorizzazione delle chiamate e l'instradamento delle chiamate.

Un piano di chiamata è costituito da una o più regole di normalizzazione che definiscono come i numeri di telefono espressi in vari formati vengono convertiti in un formato alternativo. La stessa stringa di composizione può essere interpretata e tradotta in modo diverso in piani di chiamata diversi, quindi a seconda del piano di chiamata assegnato a un determinato utente, lo stesso numero composto può essere tradotto e instradato in modo diverso. Possono essere disponibili al massimo 1.000 piani di chiamata tenant.

Vedere [Creare e gestire piani di chiamata per](create-and-manage-dial-plans.md) creare e gestire piani di chiamata tenant.

## <a name="tenant-dial-plan-scope"></a>Ambito tenant del piano di chiamata

L'ambito di un piano di chiamata determina il livello gerarchico in cui il piano di chiamata può essere applicato. I clienti ottengono il piano di chiamata appropriato tramite le impostazioni di provisioning che vengono fornite automaticamente quando gli utenti aprono Teams. Gli amministratori possono gestire e assegnare i livelli di ambito del piano di chiamata utilizzando l'interfaccia di amministrazione di Microsoft Teams o una sessione remota di PowerShell.

In Teams ci sono due tipi di piani di chiamata: con ambito di servizio e ambito tenant (che è per l'organizzazione). Un piano di chiamata di ambito di servizio è definito per ogni paese o area geografica in cui il Sistema telefonico è disponibile. A ogni utente viene assegnato automaticamente il piano di chiamata di servizio del Paese corrispondente alla località di utilizzo assegnata all'utente. Non puoi modificare il piano di chiamata di servizio del Paese, ma puoi creare piani di chiamata di ambito tenant, che ampino il piano di chiamata di servizio del Paese. Durante il provisioning, i clienti ottengono un "piano di chiamata effettivo", che è una combinazione del piano di chiamata di servizio del Paese e del piano di chiamata di ambito tenant appropriato. Pertanto, non è necessario definire tutte le regole di normalizzazione nel piano di chiamata tenant, in quanto potrebbero già essere presenti nel piano di chiamata di servizio del Paese.

I piani di chiamata tenant possono essere ulteriormente suddivisi in due ambiti: ambito tenant o ambito utente. Se un tenant definisce e assegna un piano di chiamata di ambito utente, all'utente viene assegnato un piano di chiamata effettivo del piano di chiamata di servizio del Paese e del piano di chiamata utente assegnato. Se un tenant definisce un piano di chiamata di ambito tenant ma non assegna un piano di chiamata di ambito utente, all'utente verrà assegnato un piano di chiamata effettivo del piano di chiamata di servizio del Paese e del piano di chiamata tenant.

Di seguito è riportato il modello di ereditarietà dei piani di chiamata in Teams.

![Ereditarietà dei piani di chiamata in Teams](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Di seguito sono riportati i possibili piani di chiamata effettivi.

 **Servizio Paese** Se non è definito alcun piano di chiamata di ambito tenant e non viene assegnato alcun piano di chiamata di ambito tenant utente di ambito tenant all'utente di cui è stato eseguito il provisioning, l'utente riceverà un piano di chiamata effettivo mappato al Paese di servizio associato alla sua posizione di utilizzo.

 **Tenant globale - Servizio Paese** Se è definito un piano di chiamata utente tenant, ma non è assegnato a un utente, l'utente di cui è stato eseguito il provisioning riceverà un piano di chiamata effettivo costituito da un piano di chiamata di tenant unito al piano di chiamata di servizio del Paese associato alla sua posizione di utilizzo.

 **Tenant utente - Servizio Paese** Se è definito e assegnato un piano di chiamata utente tenant a un utente, l'utente di cui è stato eseguito il provisioning riceverà un piano di chiamata effettivo costituito dal piano di chiamata utente di tenant unito al piano di chiamata di servizio del Paese associato alla sua posizione di utilizzo.

Per [creare piani di chiamata di tenant,](create-and-manage-dial-plans.md) vedere Creare e gestire piani di chiamata.

> [!NOTE]
> Nello scenario in cui nessuna regola di normalizzazione del piano di chiamata si applica a un numero composto, la stringa chiamata è ancora normalizzata anteponendo "+CC" dove CC è il codice paese della posizione di utilizzo dell'utente che compone il numero. Ciò vale per i Piani per chiamate, l'instradamento diretto e gli scenari di chiamata in uscita di conferenze PSTN.

## <a name="planning-for-tenant-dial-plans"></a>Pianificazione dei piani di chiamata tenant

Per pianificare piani di chiamata personalizzati, attenersi alla seguente procedura.

- **Passaggio 1** Decidere se è necessario un piano di chiamata personalizzato per migliorare l'esperienza di composizione dell'utente. In genere, è necessario supportare la composizione non E.164, ad esempio numeri interni o composizione nazionale abbreviata.

- **Passaggio 2** Determinare se è necessario un piano di chiamata di ambito tenant globale o tenant di ambito utente o entrambi. Sono necessari piani di chiamata di ambito utente se gli utenti hanno diversi requisiti di composizione locali.

- **Passo 3** Identificare i modelli di numerazione validi per ciascun piano di chiamata richiesto. Sono richiesti solo i modelli di numerazione che non sono definiti nel piano di chiamata di ambito di servizio del Paese.

- **Passo 4** Sviluppare un sistema a livello di organizzazione per la denominazione dei piani di chiamata. L'adozione di uno schema di denominazione standard assicura la coerenza in tutta l'organizzazione e rende più semplici la manutenzione e gli aggiornamenti.


## <a name="creating-your-new-dial-plan"></a>Creazione del nuovo piano di chiamata

Quando si crea un nuovo piano di chiamata, è necessario mettere le informazioni richieste.

### <a name="name-and-simple-name"></a>Nome e nome semplice

Per i piani di chiamata utente, è necessario specificare un nome descrittivo che identifichi gli utenti a cui verrà assegnato il piano di chiamata. Il nome semplice del piano di chiamata viene precompilato con una stringa derivata dal nome del piano di chiamata. Il campo Nome semplice è modificabile, per creare una convenzione di denominazione più descrittiva per i piani di chiamata. Il valore Nome semplice non può essere vuoto e deve essere unico. L'approccio ideale è sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzare questa convenzione in modo coerente in tutte le sedi e per tutti gli utenti.

### <a name="description"></a>Descrizione

Consigliamo di digitare il nome comune riconoscibile della posizione geografica o del gruppo di utenti a cui si applica il piano di chiamata corrispondente.

### <a name="external-access-prefix"></a>Prefisso di accesso esterno
<a name="bkexternalprefix"> </a>

È possibile specificare un prefisso di accesso esterno di un massimo di quattro caratteri (#, * e 0-9), se gli utenti hanno bisogno di comporre una o più cifre iniziali (ad esempio 9) per accedere alla linea esterna.

> [!NOTE]
> Se si specifica un prefisso di accesso esterno, non è necessario creare un'ulteriore regola di normalizzazione che comprenda il prefisso.

Per [creare piani di chiamata di tenant,](create-and-manage-dial-plans.md) vedere Creare e gestire piani di chiamata.

## <a name="normalization-rules"></a>Regole di normalizzazione
<a name="bknormalizationrule"> </a>

Le regole di normalizzazione definiscono come i numeri di telefono espressi in vari formati devono essere convertiti. La stessa stringa numerica può essere interpretata e tradotta in modo diverso, a seconda della posizione da cui viene composta. Le regole di normalizzazione possono essere necessarie se gli utenti devono essere in grado di comporre numeri interni o esterni abbreviati.

Devono essere assegnate una o più regole di normalizzazione al piano di chiamata. Le regole di normalizzazione vengono abbinate dall'alto verso il basso, quindi l'ordine in cui vengono visualizzate in un piano di chiamata tenant è importante. Ad esempio, se un piano di chiamata tenant ha 10 regole di normalizzazione, la logica di abbinamento del numero composto verrà applicata per prima cosa alla prima regola di normalizzazione; se non corrisponde, passerà alla seconda, e così via. Se si ottiene un abbinamento, viene utilizzata quella regola e non vengono controllate le corrispondenze con altre regole definite. Un dato piano di chiamata tenant può contenere al massimo 50 regole di normalizzazione.

### <a name="determining-the-required-normalization-rules"></a>Determinare le regole di normalizzazione richieste

Poiché qualsiasi piano di chiamata tenant è di fatto unito al piano di chiamata di servizio del Paese di un determinato utente, è probabile che le regole di normalizzazione del piano di chiamata di servizio del Paese siano necessarie per determinare quali regole di normalizzazione sono necessarie. Il cmdlet **Get-CsEffectiveTenantDialPlan** può essere utilizzato per questo scopo. Il cmdlet prende l'identità dell'utente come parametro di input e restituisce tutte le regole di normalizzazione applicabili per l'utente.

### <a name="creating-normalization-rules"></a>Creazione di regole di normalizzazione
<a name="createrule"> </a>

Le regole di normalizzazione .NET Framework espressioni regolari per specificare schemi numerici corrispondenti che il server usa per tradurre le stringhe di composizione in formato E.164. Possono essere create regole di normalizzazione specificando l'espressione regolare per cercare l'abbinamento e la conversione da eseguire quando si trova l'abbinamento. Terminata l'operazione, è possibile immettere un numero di prova per verificare che la regola di normalizzazione funzioni come previsto.

Per informazioni dettagliate sull'.NET Framework espressioni regolari, vedere .NET Framework [espressioni regolari.](https://go.microsoft.com/fwlink/p/?linkId=140927)

Vedi [Creare e gestire piani di chiamata](create-and-manage-dial-plans.md) per creare e gestire regole di normalizzazione per i piani di chiamata tenant.

> [!NOTE]
> Le regole di normalizzazione con il primo token come facoltativo non sono attualmente supportate nei dispositivi a 3pip (ad esempio, modello Polycom VVX 601). Se si vogliono applicare regole di normalizzazione facoltative su dispositivi con 3pip, è consigliabile creare due regole di normalizzazione anziché una. Ad esempio, la regola ^0? (999)$ dovrà essere sostituito dalle due regole seguenti: (999)$ (Traduzione:$1) e ^0(999)$ (Traduzione:$1).


### <a name="sample-normalization-rules"></a>Esempio di regole di normalizzazione

La tabella seguente mostra esempi di regole di normalizzazione scritte sotto forma di espressioni regolari .NET Framework. Si tratta solo di esempi, non di regole fisse di riferimento per la creazione di regole di normalizzazione.

<a name="regularexpression"> </a> 
 **Regole di normalizzazione con .NET Framework espressioni regolari**

| Nome regola<br/> | Descrizione<br/> | Schema numerico<br/> | Conversione<br/> | Esempio<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Converte i numeri interni a 4 cifre.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 viene convertito in +14255550100  <br/> |
|5digitExtension  <br/> |Converte i numeri interni a 5 cifre.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 viene convertito in +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte i numeri a 7 cifre in numeri locali di Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 viene convertito in +14255550100  <br/>|
|RedmondOperator  <br/> |Converte 0 nel numero del centralino per Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 viene convertito in +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte i numeri con il prefisso in rete (6) e il codice di sede di Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 viene convertito in +14255550100  <br/> |
|5digitRange  <br/> |Converte i numeri interni a 5 cifre iniziando con l'intervallo di cifre da 3 a 7, limiti inclusi.  <br/> |^([3-7]\\d{4})$  <br/> |+142555$1 <br/> |54567 viene convertito in +14255554567  <br/> |
|PrefixAdded  <br/> |Aggiunge un prefisso internazionale prima di un numero a 9 cifre, con limitazioni sulla prima e terza cifra.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 viene convertito in 14255554567  <br/> |
|NoTranslation  <br/> |Abbinamento a 5 cifre senza conversione.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 viene convertito in 34567  <br/> |

 **Piano di chiamata Redmond basato sulle regole di normalizzazione sopra indicate.**

 La tabella seguente illustra un piano di chiamata di esempio per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione indicate nella tabella precedente.

| Piano di chiamata Redmond<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> I nomi delle regole di normalizzazione mostrati nella tabella precedente non includono spazi, ma questa è solo una scelta. Il primo nome nella tabella, ad esempio, avrebbe potuto essere "5 digit extension" o "5-digit Extension" e sarebbe stato comunque valido.

## <a name="related-topics"></a>Argomenti correlati

[Creare e impostare piani di chiamata](create-and-manage-dial-plans.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

[Etichetta della dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
