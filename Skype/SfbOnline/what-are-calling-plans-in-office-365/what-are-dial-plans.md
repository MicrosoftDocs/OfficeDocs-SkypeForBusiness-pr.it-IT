---
title: What are dial plans?
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Learn what type of dial calling plans (PSTN Calling dial plans) are available with Office 365 and how to choose one for your organization.  '
search.appverid:
- MED150
- MOE150
ms.openlocfilehash: c24727dec0a9d938b3b0e40ef6f47501944e70e1
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="what-are-dial-plans"></a>What are dial plans?

[] Un piano di chiamata è un insieme denominato di regole di normalizzazione che traducono i numeri di telefono composti da un singolo utente in un formato alternativo (in genere E.164) per l'autorizzazione delle chiamate e l'instradamento delle chiamate.
  
A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format. The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.
  
## <a name="tenant-dial-plan-scope"></a>Ambito tenant del piano di chiamata

L'ambito di un piano di chiamata determina il livello gerarchico in cui il piano di chiamata può essere applicato. The scopes are different than in a Skype for Business Server 2015 on-premises deployment. I clienti ottengono il piano di chiamata appropriato attraverso le impostazioni di provisioning che vengono fornite automaticamente quando gli utenti accedono a Skype for Business online. Come amministratore, puoi gestire e assegnare i livelli di ambito del piano di chiamata utilizzando PowerShell da remoto.
  
In Skype for Business Online, there are two types of dial plans - service scoped and tenant (which is for your organization) scoped. A service scoped dial plan is defined for every country/region where the Office 365 Phone System is available. Each user is automatically assigned the service country dial plan that matches the Office 365 Usage Location assigned to the user. You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan. As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan. Pertanto, non è necessario definire tutte le regole di normalizzazione nel piano di chiamata tenant, in quanto potrebbero già essere presenti nel piano di chiamata di servizio del Paese.
  
I piani di chiamata tenant si possono suddividere ulteriormente in due ambiti: l'ambito tenant e l'ambito utente. Se un tenant definisce e assegna un piano di chiamata con ambito utente, quell'utente riceverà in provisioning un piano di chiamata effettivo costituito dal piano di chiamata di servizio del Paese dell'utente e dal piano di chiamata assegnato all'utente. Se un tenant definisce un piano di chiamata con ambito tenant ma non assegna un piano di chiamata con ambito utente, quell'utente riceverà in provisioning un piano di chiamata effettivo costituito dal piano di chiamata di servizio del Paese e dal piano di chiamata tenant.
  
Quello che segue è il modello di ereditarietà dei piani di chiamata in Skype for Business online.
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
Di seguito sono riportati i possibili piani di chiamata effettivi.
  
 **Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their Office 365 Usage Location.
  
 **Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their Office 365 Usage Location.
  
 **Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their Office 365 Usage Location.
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.
  
## <a name="planning-for-tenant-dial-plans"></a>Pianificazione dei piani di chiamata tenant

Per pianificare piani di chiamata personalizzati, attenersi alla seguente procedura.
  
- **Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience. Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.
    
- **Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both. Sono necessari piani di chiamata di ambito utente se gli utenti hanno diversi requisiti di composizione locali.
    
- **Passo 3** Identificare i modelli di numerazione validi per ciascun piano di chiamata richiesto. Sono richiesti solo i modelli di numerazione che non sono definiti nel piano di chiamata di ambito di servizio del Paese.
    
- **Passo 4** Sviluppare un sistema a livello di organizzazione per la denominazione dei piani di chiamata. L'adozione di uno schema di denominazione standard assicura la coerenza in tutta l'organizzazione e rende più semplici la manutenzione e gli aggiornamenti.
    
The [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) has additional resources and partners that can assist you with implementing tenant dial plans.
  
## <a name="creating-your-new-tenant-dial-plan"></a>Creazione di un nuovo piano di chiamata di ambito tenant

Quando si crea un nuovo piano di chiamata, è necessario mettere le informazioni richieste.
  
### <a name="name-and-simple-name"></a>Nome e nome semplice

For user dial plans, you should specify a descriptive name that identifies to the users the dial plan will be assigned. Il nome semplice del piano di chiamata precompilato con una stringa derivata dal nome del piano di chiamata. Il campo Nome semplice è modificabile, per creare una convenzione di denominazione più descrittiva per i piani di chiamata. Il valore Nome semplice non può essere vuoto e deve essere unico. L'approccio ideale è sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzare questa convenzione in modo coerente in tutte le sedi e per tutti gli utenti.
  
### <a name="description"></a>Descrizione

Consigliamo di digitare il nome comune riconoscibile della posizione geografica o del gruppo di utenti a cui si applica il piano di chiamata corrispondente.
  
### <a name="external-access-prefix"></a>Prefisso di accesso esterno

> [!CAUTION]
> Il prefisso di accesso esterno non è supportato al momento. 
  
È possibile specificare un prefisso di accesso esterno di un massimo di quattro caratteri (#, * e 0-9), se gli utenti hanno bisogno di comporre una o più cifre iniziali (ad esempio 9) per accedere alla linea esterna.
  
> [!NOTE]
> Se si specifica un prefisso di accesso esterno, non è necessario creare un'ulteriore regola di normalizzazione che comprenda il prefisso. 
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.
  
## <a name="normalization-rules"></a>Regole di normalizzazione

Le regole di normalizzazione definiscono come i numeri di telefono espressi in vari formati devono essere convertiti. La stessa stringa numerica può essere interpretata e tradotta in modo diverso, a seconda della posizione da cui viene composta. Le regole di normalizzazione possono essere necessarie se gli utenti devono essere in grado di comporre numeri interni o esterni abbreviati.
  
Devono essere assegnate una o più regole di normalizzazione al piano di chiamata. Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important. Ad esempio, se un piano di chiamata tenant ha 10 regole di normalizzazione, la logica di abbinamento del numero composto verrà applicata per prima cosa alla prima regola di normalizzazione; se non corrisponde, passerà alla seconda, e così via. Se si ottiene un abbinamento, viene utilizzata quella regola e non vengono controllate le corrispondenze con altre regole definite. Possono essere definite al massimo 25 regole di normalizzazione in un determinato piano di chiamata tenant.
  
### <a name="determining-the-required-normalization-rules"></a>Determinare le regole di normalizzazione richieste

Dato che qualsiasi piano di chiamata tenant viene di fatto unito al piano di chiamata di servizio del Paese di un determinato utente, è probabile che le regole di normalizzazione del piano di chiamata di servizio di un Paese debbano essere valutate per determinare quali regole di normalizzazione sono necessarie nel piano di chiamata tenant. Il cmdlet **Get-CsEffectiveTenantDialPlan** può essere utilizzato per questo scopo. Il cmdlet prende l'identità dell'utente come parametro di input e restituisce tutte le regole di normalizzazione applicabili per l'utente.
  
### <a name="creating-normalization-rules"></a>Creazione di regole di normalizzazione

Le regole di normalizzazione usano le espressioni regolari .NET Framework per specificare modelli numerici di abbinamento che il server utilizza per tradurre le stringhe di composizione in formato E.164 allo scopo di eseguire la ricerca inversa. Possono essere create regole di normalizzazione specificando l'espressione regolare per cercare l'abbinamento e la conversione da eseguire quando si trova l'abbinamento. Terminata l'operazione, è possibile immettere un numero di prova per verificare che la regola di normalizzazione funzioni come previsto.
  
For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.
  
### <a name="sample-normalization-rules"></a>Esempio di regole di normalizzazione

La tabella seguente mostra esempi di regole di normalizzazione scritte sotto forma di espressioni regolari .NET Framework. Si tratta solo di esempi, non di regole fisse di riferimento per la creazione di regole di normalizzazione.
  
 **Normalization rules using .NET Framework regular expressions**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nome regola** <br/> |**Descrizione** <br/> |**Schema numerico** <br/> |**Conversione** <br/> |**Esempio** <br/> |
|4digitExtension  <br/> |Converte i numeri interni a 4 cifre.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 viene convertito in +14255550100  <br/> |
|5digitExtension  <br/> |Converte i numeri interni a 5 cifre.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 viene convertito in +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte i numeri a 7 cifre in numeri locali di Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 viene convertito in +14255550100  <br/>|
|RedmondOperator  <br/> |Converte 0 nel numero del centralino per Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 viene convertito in +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte i numeri con il prefisso in rete (6) e il codice di sede di Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 viene convertito in +14255550100  <br/> |
|5digitRange  <br/> |Converte i numeri interni a 5 cifre iniziando con l'intervallo di cifre da 3 a 7, limiti inclusi.  <br/> |^([3-7]\\d{4})$  <br/> |+142570$1  <br/> |54567 viene convertito in +14255554567  <br/> |
|PrefixAdded  <br/> |Aggiunge un prefisso internazionale prima di un numero a 9 cifre, con limitazioni sulla prima e terza cifra.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 viene convertito in 14255554567  <br/> |
|NoTranslation  <br/> |Abbinamento a 5 cifre senza conversione.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 viene convertito in 34567  <br/> |
   
 **Piano di chiamata Redmond basato sulle regole di normalizzazione sopra indicate.**
  
La tabella seguente illustra un piano di chiamata di esempio per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione indicate nella tabella precedente.
|:-----| |**Redmond dial plan** <br/> | |5digitExtension <br/> | |7digitcallingRedmond <br/> | |RedmondSitePrefix <br/> | |RedmondOperator <br/> |
   
> [!NOTE]
> I nomi delle regole di normalizzazione mostrati nella tabella precedente non includono spazi, ma questa è solo una scelta. Il primo nome nella tabella, ad esempio, avrebbe potuto essere "5 digit extension" o "5-digit Extension" e sarebbe stato comunque valido. 
  
## <a name="related-topics"></a>See also
[Creare e impostare piani di chiamata](create-and-manage-dial-plans.md)

[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

[Domande comuni sul trasferimento dei numeri di telefono](transferring-phone-numbers-common-questions.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 