---
title: Che cosa sono i piani di chiamata?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: "Informazioni su come scegliere un modello per l'organizzazione e il tipo di dial plan (chiamata PSTN dial plan) la chiamata sono disponibili con Office 365.  "
ms.openlocfilehash: 27e65cb0651171f7e0a5d0262db0072b4d620851
ms.sourcegitcommit: b45077dd1b5d366fa9a30698aa66ed4b13264eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "21145294"
---
# <a name="what-are-dial-plans"></a>Che cosa sono i piani di chiamata?

[] Un piano di chiamata è un insieme denominato di regole di normalizzazione che traducono i numeri di telefono composti da un singolo utente in un formato alternativo (in genere E.164) per l'autorizzazione delle chiamate e l'instradamento delle chiamate.
  
Un dial plan è costituita da uno o più regole di normalizzazione che definiscono la modalità di conversione dei numeri di telefono espressi in formati diversi per un formato alternativo. La stessa stringa di connessione può essere interpretata e convertita in modo diverso nel dial plan differenti, in modo che in base al quale plan di messaggistica unificata è assegnato a un determinato utente, lo stesso composto numero può essere convertito e inviato in modo diverso.
  
Vedere [creare e gestire i dial plan](create-and-manage-dial-plans.md) per creare e gestire i tenant dial plan.
  
## <a name="tenant-dial-plan-scope"></a>Ambito tenant del piano di chiamata

L'ambito di un piano di chiamata determina il livello gerarchico in cui il piano di chiamata può essere applicato. Gli ambiti sono diversi da quella in Skype per Business Server 2015 distribuzione locale. I clienti ottengono il piano di chiamata appropriato attraverso le impostazioni di provisioning che vengono fornite automaticamente quando gli utenti accedono a Skype for Business online. Come amministratore, puoi gestire e assegnare i livelli di ambito del piano di chiamata utilizzando PowerShell da remoto.
  
In Skype Business online, esistono due tipi di plan di messaggistica unificata-tenant, ovvero per l'organizzazione, l'ambito e nell'ambito del servizio. Un dial plan con ambito servizio è definito per ogni paese/area geografica in cui è disponibile il sistema telefonico di Office 365. Ogni utente viene automaticamente assegnato il dial plan paese servizio che genera una corrispondenza per il percorso di utilizzo Office 365 assegnati all'utente. Non è possibile modificare il dial plan paese servizio, ma è possibile creare i dial plan tenant con ambito, quale aggiungere il dial plan paese servizio. Come i client sono predisposti, ottengono un "efficace dial plan," che corrisponde a una combinazione di servizio paese dial plan e il dial plan tenant con ambito in modo appropriato. Pertanto, non è necessario definire tutte le regole di normalizzazione nel piano di chiamata tenant, in quanto potrebbero già essere presenti nel piano di chiamata di servizio del Paese.
  
I piani di chiamata tenant si possono suddividere ulteriormente in due ambiti: l'ambito tenant e l'ambito utente. Se un tenant definisce e assegna un piano di chiamata con ambito utente, quell'utente riceverà in provisioning un piano di chiamata effettivo costituito dal piano di chiamata di servizio del Paese dell'utente e dal piano di chiamata assegnato all'utente. Se un tenant definisce un piano di chiamata con ambito tenant ma non assegna un piano di chiamata con ambito utente, quell'utente riceverà in provisioning un piano di chiamata effettivo costituito dal piano di chiamata di servizio del Paese e dal piano di chiamata tenant.
  
Quello che segue è il modello di ereditarietà dei piani di chiamata in Skype for Business online.
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
Di seguito sono riportati i possibili piani di chiamata effettivi.
  
 **Paese del servizio** Se non è definito alcun dial plan tenant con ambito e alcun dial plan con ambito utente tenant non vengono assegnati all'utente fornita, l'utente riceverà un efficace dial plan mappati nel paese di servizio associato relativo percorso di utilizzo di Office 365.
  
 **Tenant globale - servizio paese** Se un dial plan utente tenant è definito ma non assegnati a un utente, l'utente fornita riceverà un'efficace plan di messaggistica unificata composta da un dial plan tenant unito e il servizio paese dial plan associato relativo percorso di utilizzo di Office 365.
  
 **Utente tenant - servizio paese** Se un dial plan utente tenant viene definito e assegnato a un utente, l'utente fornita riceverà un'efficace plan di messaggistica unificata costituito dal dial plan utente tenant unito e il servizio paese dial plan associato relativo percorso di utilizzo di Office 365.
  
Vedere [creare e gestire i dial plan](create-and-manage-dial-plans.md) per creare il tenant di dial plan.
  
## <a name="planning-for-tenant-dial-plans"></a>Pianificazione dei piani di chiamata tenant

Per pianificare piani di chiamata personalizzati, attenersi alla seguente procedura.
  
- **Passaggio 1** Decidere se un oggetto personalizzato dial plan è necessaria per migliorare l'esperienza di composizione di utente. In genere, la necessità di uno è per il supporto di composizione non e. 164, ad esempio le estensioni o abbreviato composizione nazionale.
    
- **Passaggio 2** Determinare se sono necessari tenant globale o tenant con ambito utente dial plan o entrambi. Sono necessari piani di chiamata di ambito utente se gli utenti hanno diversi requisiti di composizione locali.
    
- **Passo 3** Identificare i modelli di numerazione validi per ciascun piano di chiamata richiesto. Sono richiesti solo i modelli di numerazione che non sono definiti nel piano di chiamata di ambito di servizio del Paese.
    
- **Passo 4** Sviluppare un sistema a livello di organizzazione per la denominazione dei piani di chiamata. L'adozione di uno schema di denominazione standard assicura la coerenza in tutta l'organizzazione e rende più semplici la manutenzione e gli aggiornamenti.
    
Risorse aggiuntive e partner che possono facilitare l'implementazione di tenant dial plan [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) .
  
## <a name="creating-your-new-tenant-dial-plan"></a>Creazione di un nuovo piano di chiamata di ambito tenant

Quando si crea un nuovo piano di chiamata, è necessario mettere le informazioni richieste.
  
### <a name="name-and-simple-name"></a>Nome e nome semplice

Per i dial plan utente, è necessario specificare un nome descrittivo che identifica il dial plan agli utenti verrà assegnato. Il nome semplice del piano di chiamata precompilato con una stringa derivata dal nome del piano di chiamata. Il campo Nome semplice è modificabile, per creare una convenzione di denominazione più descrittiva per i piani di chiamata. Il valore Nome semplice non può essere vuoto e deve essere unico. L'approccio ideale è sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzare questa convenzione in modo coerente in tutte le sedi e per tutti gli utenti.
  
### <a name="description"></a>Descrizione

Consigliamo di digitare il nome comune riconoscibile della posizione geografica o del gruppo di utenti a cui si applica il piano di chiamata corrispondente.
  
### <a name="external-access-prefix"></a>Prefisso di accesso esterno

> [!CAUTION]
> Il prefisso di accesso esterno non è supportato al momento. 
  
È possibile specificare un prefisso di accesso esterno di un massimo di quattro caratteri (#, * e 0-9), se gli utenti hanno bisogno di comporre una o più cifre iniziali (ad esempio 9) per accedere alla linea esterna.
  
> [!NOTE]
> Se si specifica un prefisso di accesso esterno, non è necessario creare un'ulteriore regola di normalizzazione che comprenda il prefisso. 
  
Vedere [creare e gestire i dial plan](create-and-manage-dial-plans.md) per creare il tenant di dial plan.
  
## <a name="normalization-rules"></a>Regole di normalizzazione

Le regole di normalizzazione definiscono come i numeri di telefono espressi in vari formati devono essere convertiti. La stessa stringa numerica può essere interpretata e tradotta in modo diverso, a seconda della posizione da cui viene composta. Le regole di normalizzazione possono essere necessarie se gli utenti devono essere in grado di comporre numeri interni o esterni abbreviati.
  
Devono essere assegnate una o più regole di normalizzazione al piano di chiamata. Le regole di normalizzazione vengono eseguite dall'alto verso il basso, in modo che l'ordine in cui vengono visualizzati in un tenant dial plan è importante. Ad esempio, se un piano di chiamata tenant ha 10 regole di normalizzazione, la logica di abbinamento del numero composto verrà applicata per prima cosa alla prima regola di normalizzazione; se non corrisponde, passerà alla seconda, e così via. Se si ottiene un abbinamento, viene utilizzata quella regola e non vengono controllate le corrispondenze con altre regole definite. Possono essere definite al massimo 25 regole di normalizzazione in un determinato piano di chiamata tenant.
  
### <a name="determining-the-required-normalization-rules"></a>Determinare le regole di normalizzazione richieste

Dato che qualsiasi piano di chiamata tenant viene di fatto unito al piano di chiamata di servizio del Paese di un determinato utente, è probabile che le regole di normalizzazione del piano di chiamata di servizio di un Paese debbano essere valutate per determinare quali regole di normalizzazione sono necessarie nel piano di chiamata tenant. Il cmdlet **Get-CsEffectiveTenantDialPlan** può essere utilizzato per questo scopo. Il cmdlet prende l'identità dell'utente come parametro di input e restituisce tutte le regole di normalizzazione applicabili per l'utente.
  
### <a name="creating-normalization-rules"></a>Creazione di regole di normalizzazione

Le regole di normalizzazione usano le espressioni regolari .NET Framework per specificare modelli numerici di abbinamento che il server utilizza per tradurre le stringhe di composizione in formato E.164 allo scopo di eseguire la ricerca inversa. Possono essere create regole di normalizzazione specificando l'espressione regolare per cercare l'abbinamento e la conversione da eseguire quando si trova l'abbinamento. Terminata l'operazione, è possibile immettere un numero di prova per verificare che la regola di normalizzazione funzioni come previsto.
  
Per ulteriori informazioni sull'utilizzo di espressioni regolari di .NET Framework, vedere [Espressioni regolari di .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
Vedere [creare e gestire i dial plan](create-and-manage-dial-plans.md) per creare e gestire la normalizzazione regole per il tenant di dial plan.
  
### <a name="sample-normalization-rules"></a>Esempio di regole di normalizzazione

La tabella seguente mostra esempi di regole di normalizzazione scritte sotto forma di espressioni regolari .NET Framework. Si tratta solo di esempi, non di regole fisse di riferimento per la creazione di regole di normalizzazione.
  
 **Regole di normalizzazione tramite espressioni regolari di .NET Framework**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nome regola** <br/> |**Descrizione** <br/> |**Schema numerico** <br/> |**Conversione** <br/> |**Esempio** <br/> |
|4digitExtension  <br/> |Converte i numeri interni a 4 cifre.  <br/> |^ (\\g{4}) $  <br/> |+1425555$1  <br/> |0100 viene convertito in +14255550100  <br/> |
|5digitExtension  <br/> |Converte i numeri interni a 5 cifre.  <br/> |^ 5 (\\g{4}) $  <br/> |+1425555$1  <br/> |50100 viene convertito in +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte i numeri a 7 cifre in numeri locali di Redmond.  <br/> |^ (\\g{7}) $  <br/> |+1425$1  <br/> |5550100 viene convertito in +14255550100  <br/>|
|RedmondOperator  <br/> |Converte 0 nel numero del centralino per Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 viene convertito in +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte i numeri con il prefisso in rete (6) e il codice di sede di Redmond (222).  <br/> |^ 6222 (\\g{4}) $  <br/> |+1425555$1  <br/> |62220100 viene convertito in +14255550100  <br/> |
|5digitRange  <br/> |Converte i numeri interni a 5 cifre iniziando con l'intervallo di cifre da 3 a 7, limiti inclusi.  <br/> |^ ([3-7]\\g{4}) $  <br/> |+ 142555$ 1 <br/> |54567 viene convertito in +14255554567  <br/> |
|PrefixAdded  <br/> |Aggiunge un prefisso internazionale prima di un numero a 9 cifre, con limitazioni sulla prima e terza cifra.  <br/> |^ ([2-9]\\g\\g [2-9]\\g{6}) $  <br/> |1$1  <br/> |4255554567 viene convertito in 14255554567  <br/> |
|Non tradotto  <br/> |Abbinamento a 5 cifre senza conversione.  <br/> |^ (\\g{5}) $  <br/> |$1  <br/> |34567 viene convertito in 34567  <br/> |
   
 **Piano di chiamata Redmond basato sulle regole di normalizzazione sopra indicate.**
  
La tabella seguente illustra un piano di chiamata di esempio per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione indicate nella tabella precedente.
|:-----| | **Dial plan di Redmond** <br/> | | 5digitExtension <br/> | | 7digitcallingRedmond <br/> | | RedmondSitePrefix <br/> | | RedmondOperator <br/> |
   
> [!NOTE]
> I nomi delle regole di normalizzazione mostrati nella tabella precedente non includono spazi, ma questa è solo una scelta. Il primo nome nella tabella, ad esempio, avrebbe potuto essere "5 digit extension" o "5-digit Extension" e sarebbe stato comunque valido. 
  
## <a name="related-topics"></a>See also
[Creare e impostare piani di chiamata](create-and-manage-dial-plans.md)

[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

[Domande comuni sul trasferimento dei numeri di telefono](transferring-phone-numbers-common-questions.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
