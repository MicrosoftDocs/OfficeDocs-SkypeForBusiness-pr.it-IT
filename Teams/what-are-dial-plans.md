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
description: "Informazioni sul tipo di piani per chiamate telefoniche (PSTN Calling dial plan) disponibili con teams e su come sceglierne uno per l'organizzazione.  "
ms.openlocfilehash: 3ca0848094e94ff302cfcdeaa80ddd72a3b86698
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836686"
---
# <a name="what-are-dial-plans"></a>Che cosa sono i piani di chiamata?

[] Un piano di chiamata è un insieme denominato di regole di normalizzazione che traducono i numeri di telefono composti da un singolo utente in un formato alternativo (in genere E.164) per l'autorizzazione delle chiamate e l'instradamento delle chiamate.

Un dial plan è costituito da una o più regole di normalizzazione che definiscono il modo in cui i numeri di telefono espressi in diversi formati vengono tradotti in un formato alternativo. La stessa stringa di chiamata può essere interpretata e tradotta in modo diverso nei diversi piani di chiamata, quindi, a seconda del tipo di dial plan assegnato a un utente specifico, lo stesso numero di telefono può essere tradotto e instradato in modo diverso. Può essere disponibile un massimo di piani di 1.000 tenant.

Per creare e gestire piani di chiamata di tenant, vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md) .

## <a name="tenant-dial-plan-scope"></a>Ambito tenant del piano di chiamata

L'ambito di un piano di chiamata determina il livello gerarchico in cui il piano di chiamata può essere applicato. I client ottengono il dial plan appropriato tramite le impostazioni di provisioning fornite automaticamente quando gli utenti accedono a teams. L'amministratore può gestire e assegnare livelli di ambito di dial plan usando l'interfaccia di amministrazione di Microsoft teams o Remote PowerShell.

In teams sono disponibili due tipi di dial plan: con ambito di servizio e a livello di tenant (ovvero per l'organizzazione). Viene definito un dial plan con ambito servizio per ogni paese o area geografica in cui è disponibile il sistema telefonico. A ogni utente viene assegnato automaticamente il dial plan del paese di servizio che corrisponde alla posizione di utilizzo assegnata all'utente. Non è possibile modificare il dial plan per il paese di servizio, ma si possono creare piani di dial con ambito tenant, che aumentano il dial plan paese di servizio. Man mano che i clienti hanno effettuato il provisioning, ottengono un "piano di chiamata efficace", che è una combinazione di dial plan del paese di servizio e il dial plan del tenant con ambito appropriato. Pertanto, non è necessario definire tutte le regole di normalizzazione nei piani di chiamata del tenant che potrebbero già esistere nel dial plan paese di servizio.

I piani di chiamata del tenant possono essere ulteriormente suddivisi in due ambiti: tenant-scope o User-scope. Se un tenant definisce e assegna un dial plan con ambito utente, verrà eseguito il provisioning di un utente con un piano di chiamata effettivo del dial plan del paese di servizio dell'utente e del dial plan utente assegnato. Se un tenant definisce un dial plan con ambito tenant ma non assegna un dial plan con ambito utente, verrà eseguito il provisioning di un utente con un piano di chiamata effettivo del dial plan del paese di servizio dell'utente e del dial plan del tenant.

Di seguito è riportato il modello di ereditarietà dei dial plan in teams.

![Come vengono ereditati i dial plan in teams](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Di seguito sono riportati i possibili piani di chiamata effettivi.

 **Paese di servizio** Se non si definisce un dial plan con ambito tenant e non viene assegnato un dial plan con ambito utente tenant all'utente con provisioning, l'utente riceverà un piano di chiamata effettivo mappato al paese del servizio associato alla posizione di utilizzo.

 **Paese del servizio globale tenant** Se un piano di chiamata utente del tenant è definito ma non è assegnato a un utente, l'utente provisioning riceverà un piano di chiamata effettivo costituito da un dial plan di tenant Unito e dal dial plan del paese di servizio associato alla posizione di utilizzo.

 **Paese del servizio utente del tenant** Se un piano di chiamata utente del tenant è definito e assegnato a un utente, l'utente provisioning riceverà un piano di chiamata effettivo costituito dal piano di dial User del tenant Unito e dal dial plan del paese di servizio associato alla posizione di utilizzo.

Vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md) per creare piani di chiamata del tenant.

## <a name="planning-for-tenant-dial-plans"></a>Pianificazione dei piani di chiamata tenant

Per pianificare piani di chiamata personalizzati, attenersi alla seguente procedura.

- **Passaggio 1** Decidere se è necessario un dial plan personalizzato per migliorare l'esperienza di chiamata degli utenti. In genere, la necessità di uno sarebbe quella di supportare la chiamata non E. 164, ad esempio le estensioni o la chiamata a livello nazionale abbreviato.

- **Passaggio 2** Determinare se i piani di dial con ambito dell'utente tenant Global o tenant sono necessari o entrambi. Sono necessari piani di chiamata di ambito utente se gli utenti hanno diversi requisiti di composizione locali.

- **Passo 3** Identificare i modelli di numerazione validi per ciascun piano di chiamata richiesto. Sono richiesti solo i modelli di numerazione che non sono definiti nel piano di chiamata di ambito di servizio del Paese.

- **Passo 4** Sviluppare un sistema a livello di organizzazione per la denominazione dei piani di chiamata. L'adozione di uno schema di denominazione standard assicura la coerenza in tutta l'organizzazione e rende più semplici la manutenzione e gli aggiornamenti.


## <a name="creating-your-new-tenant-dial-plan"></a>Creazione di un nuovo piano di chiamata di ambito tenant

Quando si crea un nuovo piano di chiamata, è necessario mettere le informazioni richieste.

### <a name="name-and-simple-name"></a>Nome e nome semplice

Per i piani di chiamata utente, devi specificare un nome descrittivo che identifichi gli utenti a cui verrà assegnato il dial plan. Il nome semplice dial plan viene prepopolato con una stringa derivata dal nome del dial plan. Il campo Nome semplice è modificabile, per creare una convenzione di denominazione più descrittiva per i piani di chiamata. Il valore Nome semplice non può essere vuoto e deve essere unico. L'approccio ideale è sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzare questa convenzione in modo coerente in tutte le sedi e per tutti gli utenti.

### <a name="description"></a>Descrizione

Consigliamo di digitare il nome comune riconoscibile della posizione geografica o del gruppo di utenti a cui si applica il piano di chiamata corrispondente.

### <a name="external-access-prefix"></a>Prefisso di accesso esterno
<a name="bkexternalprefix"> </a>

È possibile specificare un prefisso di accesso esterno di un massimo di quattro caratteri (#, * e 0-9), se gli utenti hanno bisogno di comporre una o più cifre iniziali (ad esempio 9) per accedere alla linea esterna.

> [!NOTE]
> Se si specifica un prefisso di accesso esterno, non è necessario creare un'ulteriore regola di normalizzazione che comprenda il prefisso.

Vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md) per creare piani di chiamata del tenant.

## <a name="normalization-rules"></a>Regole di normalizzazione
<a name="bknormalizationrule"> </a>

Le regole di normalizzazione definiscono come i numeri di telefono espressi in vari formati devono essere convertiti. La stessa stringa numerica può essere interpretata e tradotta in modo diverso, a seconda della posizione da cui viene composta. Le regole di normalizzazione possono essere necessarie se gli utenti devono essere in grado di comporre numeri interni o esterni abbreviati.

Devono essere assegnate una o più regole di normalizzazione al piano di chiamata. Le regole di normalizzazione vengono confrontate dall'alto verso il basso, quindi l'ordine in cui vengono visualizzate in un dial plan del tenant è importante. Ad esempio, se un piano di chiamata tenant ha 10 regole di normalizzazione, la logica di abbinamento del numero composto verrà applicata per prima cosa alla prima regola di normalizzazione; se non corrisponde, passerà alla seconda, e così via. Se si ottiene un abbinamento, viene utilizzata quella regola e non vengono controllate le corrispondenze con altre regole definite. Il numero massimo di regole di normalizzazione di 50 può essere consentito in un dial plan di tenant.

### <a name="determining-the-required-normalization-rules"></a>Determinare le regole di normalizzazione richieste

Dato che qualsiasi piano di dialing del tenant viene effettivamente Unito con un dial plan di paese di servizio di un determinato utente, è probabile che le regole di normalizzazione del piano di servizio dial plan debbano essere valutate per determinare quali regole di normalizzazione del piano di chiamata del tenant sono necessarie. Il cmdlet **Get-CsEffectiveTenantDialPlan** può essere utilizzato per questo scopo. Il cmdlet prende l'identità dell'utente come parametro di input e restituisce tutte le regole di normalizzazione applicabili per l'utente.

### <a name="creating-normalization-rules"></a>Creazione di regole di normalizzazione
<a name="createrule"> </a> <a name="regularexpression"> </a>

Le regole di normalizzazione usano le espressioni regolari di .NET Framework per specificare i modelli di corrispondenza numerica che il server usa per tradurre le stringhe di chiamata nel formato E. 164. Possono essere create regole di normalizzazione specificando l'espressione regolare per cercare l'abbinamento e la conversione da eseguire quando si trova l'abbinamento. Terminata l'operazione, è possibile immettere un numero di prova per verificare che la regola di normalizzazione funzioni come previsto.

Per informazioni dettagliate sull'uso delle espressioni regolari di .NET Framework, vedere [espressioni regolari di .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).

Per creare e gestire regole di normalizzazione per i piani di chiamata del tenant, vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md) .

### <a name="sample-normalization-rules"></a>Esempio di regole di normalizzazione

La tabella seguente mostra esempi di regole di normalizzazione scritte sotto forma di espressioni regolari .NET Framework. Si tratta solo di esempi, non di regole fisse di riferimento per la creazione di regole di normalizzazione.

 **Regole di normalizzazione con le espressioni regolari di .NET Framework**<a name="#regularexpression"> </a>

||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nome regola** <br/> |**Descrizione** <br/> |**Schema numerico** <br/> |**Conversione** <br/> |**Esempio** <br/> |
|4digitExtension  <br/> |Converte i numeri interni a 4 cifre.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 viene convertito in +14255550100  <br/> |
|5digitExtension  <br/> |Converte i numeri interni a 5 cifre.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 viene convertito in +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte i numeri a 7 cifre in numeri locali di Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 viene convertito in +14255550100  <br/>|
|RedmondOperator  <br/> |Converte 0 nel numero del centralino per Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 viene convertito in +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte i numeri con il prefisso in rete (6) e il codice di sede di Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 viene convertito in +14255550100  <br/> |
|5digitRange  <br/> |Converte i numeri interni a 5 cifre iniziando con l'intervallo di cifre da 3 a 7, limiti inclusi.  <br/> |^([3-7]\\d{4})$  <br/> |+ 142555 $1 <br/> |54567 viene convertito in +14255554567  <br/> |
|PrefixAdded  <br/> |Aggiunge un prefisso internazionale prima di un numero a 9 cifre, con limitazioni sulla prima e terza cifra.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 viene convertito in 14255554567  <br/> |
|NOTRANSLATION  <br/> |Abbinamento a 5 cifre senza conversione.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 viene convertito in 34567  <br/> |

 **Piano di chiamata Redmond basato sulle regole di normalizzazione sopra indicate.**

 La tabella seguente illustra un piano di chiamata di esempio per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione indicate nella tabella precedente.

| |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Piano di chiamata Redmond** <br/>                                                                                                                              |
| 5digitExtension <br/>                                                                                                                                    |
| 7digitcallingRedmond <br/>                                                                                                                               |
| RedmondSitePrefix <br/>                                                                                                                                  |
| RedmondOperator <br/>                                                                                                                                    |

> [!NOTE]
> I nomi delle regole di normalizzazione visualizzati nella tabella precedente non includono spazi, ma si tratta di una scelta. Il primo nome nella tabella, ad esempio, avrebbe potuto essere "5 digit extension" o "5-digit Extension" e sarebbe stato comunque valido.

## <a name="related-topics"></a>Argomenti correlati

[Creare e impostare piani di chiamata](create-and-manage-dial-plans.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

[Etichetta Disclaimer per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
