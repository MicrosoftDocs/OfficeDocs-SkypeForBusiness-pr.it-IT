---
title: Pianificare il routing vocale in uscita in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: Informazioni sul routing vocale in uscita in Skype for Business Server VoIP aziendale, incluse le impostazioni di routing delle chiamate, i dial plan, le regole di normalizzazione, i criteri vocali, i record di utilizzo PSTN e le route vocali.
ms.openlocfilehash: 75fcefae34cfcb100a095dd83a162fec1baac1d4b17f5077611cf88635ce9ed5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349958"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Pianificare il routing vocale in uscita in Skype for Business Server
 
Informazioni sul routing vocale in uscita in Skype for Business Server VoIP aziendale, incluse le impostazioni di routing delle chiamate, i dial plan, le regole di normalizzazione, i criteri vocali, i record di utilizzo PSTN e le route vocali.
  
Il routing delle chiamate in uscita si applica VoIP aziendale chiamate destinate a un gateway PSTN (Public Switched Telephone Network), un trunk o un PBX (Private Branch Exchange). Quando un Skype for Business esegue una chiamata, il server normalizza il numero di telefono nel formato E.164, se necessario, e tenta di associarlo a un URI SIP. Se il server non riesce a trovare una corrispondenza, applica la logica di routing delle chiamate in uscita in base alla stringa di composizione fornita. È possibile definire tale logica configurando le impostazioni del server descritte nella tabella seguente.
  
**Skype for Business Server Routing delle chiamate in uscita Impostazioni**

|**Oggetto**|**Descrizione**|
|:-----|:-----|
|Dial plan  <br/> |Per dial plan si intende un set denominato di regole di normalizzazione che consente di convertire i numeri di telefono relativi a una località, a un utente o a un oggetto contatto specifico in un unico formato standard (E.164) ai fini dell'autorizzazione del telefono e del routing della chiamata.  <br/> |
|Regola di normalizzazione  <br/> |Le regole di normalizzazione definiscono come devono essere instradati numeri di telefono espressi in formati diversi per ogni località, utente oppure oggetto contatto specificato. La stessa stringa di composizione può essere interpretata e convertita in modo diverso a seconda della località da cui viene composta e della persona o dell'oggetto contatto che effettua la chiamata. Un insieme di regole di normalizzazione associate a una determinata località costituisce un dial plan.  <br/> |
|Criterio vocale  <br/> |Un criterio vocale associa uno o più record di utilizzo PSTN a un utente o a un gruppo di utenti. Un criterio vocale fornisce inoltre un elenco di funzionalità di chiamata che è possibile abilitare o disabilitare.  <br/> |
|Record di utilizzo PSTN  <br/> |Un record di utilizzo PSTN specifica un tipo di chiamata (ad esempio interna, locale o interurbana) che può essere effettuata da diversi utenti o gruppi di utenti di un'organizzazione.  <br/> |
|Route di chiamata  <br/> |Una route di chiamata associa i numeri di telefono di destinazione a trunk e record di utilizzo PSTN specifici. Un gateway PSTN viene considerato un trunk.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Dial plan e regole di normalizzazione

Per dial plan si intende un set denominato di regole di normalizzazione che consente di convertire i numeri di telefono relativi a una località, a un utente o a un oggetto contatto specifico in un unico formato standard (E.164) ai fini dell'autorizzazione del telefono e del routing della chiamata. 
  
Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi nei vari formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato. La stessa stringa di composizione può essere interpretata e tradotta in modo diverso, a seconda della località da cui viene composto e della persona o dell'oggetto contatto che effettua la chiamata.
  
### <a name="dial-plan-scope"></a>Ambito del dial plan

L'ambito di un dial plan determina il livello gerarchico a cui è possibile applicare il dial plan. In Skype for Business Server, a un utente può essere assegnato un dial plan specifico per utente. Se non viene assegnato un dial plan utente, viene applicato il dial plan del pool Front End. Se non è presente alcun dial plan del pool Front End, viene applicato il dial plan del sito. Infine, se non è presente alcun altro dial plan applicabile all'utente, viene applicato il dial plan globale.
  
I client ottengono livelli di ambito del dial plan tramite le impostazioni di provisioning in banda fornite quando gli utenti a questo Skype for Business. L'amministratore può gestire e assegnare livelli di ambito del dial plan utilizzando il Skype for Business Server Di controllo.
  
> [!NOTE]
> Il dial plan del gateway PSTN (Public Switched Telephone Network) a livello di servizio viene applicato alle chiamate in arrivo da un determinato gateway. 
  
I livelli di ambito del dial plan sono definiti come segue:
  
- **Dial plan utente**: può essere assegnato a singoli utenti, gruppi o oggetti contatto. Le applicazioni vocali possono cercare un dial plan per utente quando si riceve una chiamata con il contesto telefonico impostato su user-default. Ai fini dell'assegnazione di un dial plan, un oggetto contatto viene considerato un singolo utente.
    
- **Dial plan pool**: può essere creato a livello di servizio per qualsiasi gateway PSTN o pool di registrazione nella topologia. Per definire un dial plan pool, è necessario specificare un particolare servizio (gateway PSTN o pool di registrazione) a cui applicare il dial plan. 
    
- **Dial plan del sito**: può essere creato per un intero sito, ad eccezione di tutti gli utenti, i gruppi o gli oggetti contatto a cui è assegnato un dial plan del pool o un dial plan utente. Per definire un dial plan sito, è necessario specificare il sito a cui applicare il dial plan.
    
- **Dial plan globale**: Dial plan predefinito installato con il prodotto. È possibile modificare il dial plan globale, ma non eliminarlo. Questo dial plan si applica a tutti VoIP aziendale utenti, gruppi e oggetti contatto nella distribuzione, a meno che non si configura e si assegna un dial plan con un ambito più specifico.
    
### <a name="planning-for-dial-plans"></a>Pianificazione di dial plan

Per pianificare un dial plan, attenersi alla seguente procedura:
  
- Elencare tutte le impostazioni locali in cui l'organizzazione ha un ufficio.
    
    L'elenco deve essere aggiornato e completo. Dovrà essere rivisto con l'evolversi della società. In una società multinazionale di grandi dimensioni con numerose succursali di piccole dimensioni, questa operazione può richiedere molto tempo.
    
- Identificare i modelli di numero validi per ogni sito.
    
    La parte della pianificazione dei dial plan che richiede più tempo è l'identificazione dei formati di numeri validi per ogni sito. In alcuni casi, può essere possibile copiare negli altri dial plan le regole di normalizzazione scritte per un dial plan, in particolare se i siti corrispondenti si trovano nello stesso paese, nella stessa area geografica o anche nello stesso continente. In altri casi, possono essere sufficienti piccole modifiche dei numeri in un dial plan per utilizzarli in altri dial plan.
    
- Sviluppare uno schema a livello di organizzazione per la denominazione dei dial plan.
    
    L'adozione di uno schema di denominazione standard assicura la coerenza all'interno dell'organizzazione e agevola la manutenzione e gli aggiornamenti.
    
- Decidere se sono necessari più dial plan per una singola località. 
    
    Se l'organizzazione gestisce un singolo dial plan in più posizioni, potrebbe essere comunque necessario creare un dial plan separato per gli utenti di VoIP aziendale che esereranno la migrazione da un PBX (Private Branch Exchange) e che dovranno conservare gli interni esistenti.
    
- Decidere se sono necessari dial plan per utente. Ad esempio, se in un sito di succursale sono presenti utenti registrati nel sito centrale o utenti registrati in un Survivable Branch Appliance, è possibile prendere in considerazione scenari di composizione speciali per tali utenti che utilizzano dial plan e regole di normalizzazione per utente. Per informazioni dettagliate, vedere [Plan for VoIP aziendale resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
    
- Determinare l'ambito del dial plan (come descritto in precedenza in questo argomento).
    
Per creare un dial plan, specificare i valori nei campi seguenti, se necessario, utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
#### <a name="name-and-simple-name"></a>Nome e nome semplice

Per i dial plan utente, è necessario specificare un nome descrittivo che identifichi gli utenti, i gruppi o gli oggetti contatto a cui verrà assegnato il dial plan. Per i dial plan del sito, il campo Nome è precompilato con il nome del sito e non può essere modificato. Per i dial plan del pool, il campo Nome è precompilato con il gateway PSTN o il nome di dominio completo (FQDN) del pool Front End e non può essere modificato.
  
Il nome semplice del dial plan è precompilato con una stringa derivata dal nome del dial plan. Il campo Nome semplice è modificabile, che consente di creare una convenzione di denominazione più descrittiva per i dial plan. Il valore Nomesimple non può essere vuoto e deve essere univoco. È consigliabile sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzarla in modo coerente in tutti i siti e gli utenti.
  
#### <a name="description"></a>Descrizione

Si consiglia di digitare il nome comune e riconoscibile della località geografica a cui si applica il dial plan corrispondente. Se ad esempio il nome del dial plan è Londra.Contoso.com, la descrizione consigliabile è Londra. 
  
#### <a name="dial-in-conferencing-region"></a>Area conferenza telefonica con accesso esterno

Se si distribuisce la funzionalità di conferenza telefonica con accesso esterno, è necessario specificare un'area della conferenza telefonica con accesso esterno per associare i numeri di accesso relativi a un dial plan. 
  
#### <a name="external-access-prefix"></a>Prefisso accesso esterno

È possibile specificare un prefisso di accesso esterno di un massimo di quattro caratteri (#, e 0-9) se gli utenti devono comporre una o più cifre iniziali \* aggiuntive (ad esempio, 9) per ottenere una linea esterna.
  
> [!NOTE]
> Se si specifica un prefisso di accesso esterno, non è necessario creare una regola di normalizzazione aggiuntiva per regolare il prefisso. 
  
### <a name="normalization-rules"></a>Regole di normalizzazione

Le regole di normalizzazione definiscono la modalità di routing di numeri di telefono espressi in formati diversi per la località specifica. La stessa stringa numerica può essere interpretata e tradotta in modo diverso, a seconda delle impostazioni locali da cui viene composto. Sono necessarie per il routing delle chiamate, perché gli utenti possono utilizzare vari formati quando immettono i numeri di telefono nei rispettivi elenchi contatti.
  
La normalizzazione dei numeri di telefono forniti dall'utente offre un formato coerente che facilita le attività seguenti:
  
- Associare un numero composto all'URI SIP del destinatario previsto.
    
- Applicare le regole di autorizzazione di composizione alla parte chiamante.
    
Di seguito sono riportati alcuni campi numerici che può essere necessario includere nelle regole di normalizzazione:
  
- Dial plan
    
- Codice paese
    
- Indicativo di località
    
- Lunghezza numero di interno
    
- Prefisso sito
    
#### <a name="creating-normalization-rules"></a>Creazione di regole di normalizzazione

Le regole di normalizzazione utilizzano le espressioni regolari di .NET Framework per specificare formati di corrispondenza numerica che il server utilizza per convertire le stringhe di composizione nel formato E.164 allo scopo di eseguire la ricerca inversa dei numeri. È possibile creare regole di normalizzazione nel Pannello di controllo di Skype for Business Server immettendo manualmente le espressioni oppure immettendo le cifre iniziale e la lunghezza delle stringhe di composizione da associare e consentendo al Pannello di controllo di Skype for Business Server di generare automaticamente l'espressione regolare corrispondente. In ogni caso, al termine è possibile immettere un numero di test per verificare che la regola di normalizzazione funzioni come previsto.
  
Per informazioni dettagliate sull'.NET Framework espressioni regolari, vedere [".NET Framework regolari".](/dotnet/standard/base-types/regular-expressions)
  
#### <a name="sample-normalization-rules"></a>Regole di normalizzazione di esempio
<a name="BKMK_SampleNormalizationRules"> </a>

Nella tabella seguente sono illustrati alcuni esempi di regole di normalizzazione scritte come espressioni regolari di .NET Framework. Si tratta di esempi puramente indicativi che non devono essere intesi come riferimenti obbligatori per la creazione di regole di normalizzazione.
  
**Tabella 1. Regole di normalizzazione tramite espressioni regolari di .NET Framework**

|**Nome regola**|**Descrizione**|**Formato numero**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Converte i numeri di interno a 4 cifre  <br/> |^(\d{4})$  <br/> |+1425555$1  <br/> |0100 viene convertito in +14255550100  <br/> |
|5digitExtension  <br/> |Converte i numeri di interno a 5 cifre  <br/> |^5(\d {4} )$  <br/> |+1425555$1  <br/> |50100 viene convertito in +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte i numeri a 7 cifre in numeri locali di Redmond  <br/> |^(\d{7})$  <br/> |+1425$1  <br/> |5550100 viene convertito in +14255550100  <br/> |
|7digitcallingDallas  <br/> |Converte i numeri a 7 cifre in numeri locali di Dallas  <br/> |^(\d{7})$  <br/> |+1972$1  <br/> |5550100 viene convertito in +19725550100  <br/> |
|10digitcallingUS  <br/> |Converte i numeri a 10 cifre in numeri degli Stati Uniti  <br/> |^(\d{10})$  <br/> |+1$1  <br/> |2065550100 viene convertito in +12065550100  <br/> |
|LDCallingUS  <br/> |Converte i numeri con prefissi interurbani in numeri degli Stati Uniti  <br/> |^1(\d {10} )$  <br/> |+$1  <br/> |12145550100 viene convertito in +2145550100  <br/> |
|IntlCallingUS  <br/> |Converte i numeri con prefissi internazionali in numeri degli Stati Uniti  <br/> |^011(\d \* )$  <br/> |+$1  <br/> |01191445550100 viene convertito in +91445550100  <br/> |
|RedmondOperator  <br/> |Converte il numero 0 nel numero dell'operatore di Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 viene convertito in +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte i numeri con prefisso on-net (6) e il codice sito di Redmond (222)  <br/> |^6222(\d {4} )$  <br/> |+1425555$1  <br/> |62220100 viene convertito in +14255550100  <br/> |
|NYSitePrefix  <br/> |Converte i numeri con prefisso on-net (6) e il codice sito di NY (333)  <br/> |^6333(\d {4} )$  <br/> |+1202555$1  <br/> |63330100 viene convertito in +12025550100  <br/> |
|DallasSitePrefix  <br/> |Converte i numeri con prefisso on-net (6) e il codice sito di Dallas (444)  <br/> |^6444(\d {4} )$  <br/> |+1972555$1  <br/> |64440100 viene convertito in +19725550100  <br/> |
   
Nella tabella seguente viene illustrato un esempio di dial plan per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione riportate nella tabella precedente.
  
**Tabella 2. Dial plan di Redmond basato sulle regole di normalizzazione riportate nella tabella 1**

|**Redmond.forestFQDN**|
|:-----|
|5digitExtension  <br/> |
|7digitcallingRedmond  <br/> |
|10digitcallingUS  <br/> |
|IntlCallingUS  <br/> |
|RedmondSitePrefix  <br/> |
|NYSitePrefix  <br/> |
|DallasSitePrefix  <br/> |
|RedmondOperator  <br/> |
   
> [!NOTE]
> I nomi delle regole di normalizzazione illustrate nella tabella precedente non includono spazi, ma si tratta di una scelta. Il primo nome della tabella, ad esempio, potrebbe essere "5 digit extension" o "5-digit Extension" ed essere comunque valido. 
  
## <a name="voice-policies"></a>Criteri vocali

Skype for Business Server criteri vocali definiscono quanto segue per ogni utente, sito o organizzazione a cui è assegnato il criterio:
  
- Set di funzionalità di chiamata che possono essere abilitate o disabilitate per determinare VoIP aziendale funzionalità disponibili per gli utenti.
    
- Un set di record di utilizzo PSTN (Public Switched Telephone Network) che definiscono i tipi di chiamate autorizzati. 
    
I passaggi seguenti consentono di pianificare i criteri vocali necessari per la VoIP aziendale distribuzione:
  
- Stabilire come verrà configurato il criterio vocale globale, ovvero il criterio vocale predefinito installato con il prodotto). Questo criterio verrà applicato a tutti VoIP aziendale utenti a cui non è stato esplicitamente assegnato un criterio a livello di sito o per utente.
    
- Identificare eventuali criteri vocali a livello di sito che potrebbero essere necessari.
    
- Identificare eventuali criteri vocali per utente che potrebbero essere necessari.
    
- Decidere quali funzionalità di chiamata abilitare per ogni criterio vocale.
    
- Stabilire quali record di utilizzo PSTN configurare per ogni criterio vocale.
    
### <a name="voice-policy-scope"></a>Ambito dei criteri vocali

L'ambito dei criteri vocali determina il livello gerarchico a cui è possibile applicare il criterio. In Skype for Business Server, è possibile configurare i criteri vocali con i livelli di ambito seguenti (elencati dai più specifici ai più generici).
  
- Il **criterio vocale utente** può essere assegnato a singoli utenti, gruppi o oggetti contatto. Questo è il criterio di livello più basso. È possibile distribuire criteri vocali utente per abilitare le funzionalità per determinati utenti o gruppi in un sito, ma non per altri nello stesso sito. Si potrebbe decidere ad esempio di disabilitare le chiamate interurbane per alcuni dipendenti. Ai fini dell'assegnazione di un criterio vocale, un oggetto contatto viene considerato un singolo utente.
    
    > [!NOTE]
    > È consigliabile distribuire criteri vocali utente per gli utenti del sito di succursale VoIP aziendale registrati nella distribuzione del sito centrale o per gli utenti registrati in un Survivable Branch Appliance. 
  
- Il **criterio vocale di sito** si applica a un intero sito, con l'eccezione degli utenti, gruppi o oggetti contatto a cui è stato assegnato un criterio vocale utente. Per definire un criterio vocale di sito, è necessario specificare il sito a cui si applica il criterio. Se non viene assegnato un criterio vocale utente, viene utilizzato il criterio vocale di sito.
    
- **I criteri vocali globali** sono i criteri vocali predefiniti installati con il prodotto. È possibile modificare il criterio vocale globale per soddisfare le esigenze specifiche dell'organizzazione, ma non è possibile rinominarlo o eliminarlo. Questo criterio vocale si applica a tutti VoIP aziendale utenti, gruppi e oggetti contatto nella distribuzione, a meno che non si configura e si assegna un criterio vocale con ambito più specifico. Se si desidera disabilitare completamente questo criterio, assicurarsi che a tutti i siti e a tutti gli utenti siano assegnati criteri personalizzati.
    
### <a name="call-features"></a>Funzionalità di chiamata

È possibile abilitare o disabilitare le funzionalità di chiamata seguenti per ogni criterio vocale:
  
- L'**inoltro di chiamata** consente agli utenti di inoltrare chiamate ad altri telefoni e dispositivi client. Funzionalità abilitata per impostazione predefinita.
    
- La **delega** consente agli utenti di specificare altri utenti per l'invio e la ricezione delle chiamate per loro conto. Funzionalità abilitata per impostazione predefinita.
    
- Il **trasferimento di chiamata** consente agli utenti di trasferire chiamate ad altri utenti. Funzionalità abilitata per impostazione predefinita.
    
- Il **parcheggio di chiamata** consente agli utenti di parcheggiare le chiamate e quindi di rispondere da un telefono o client diverso. Funzionalità disabilitata per impostazione predefinita.
    
- Lo **squillo simultaneo** consente lo squillo su un telefono aggiuntivo (ad esempio, un cellulare) o altri dispositivi endpoint per le chiamate in arrivo. Funzionalità abilitata per impostazione predefinita.
    
- L'**intercettazione team** consente agli utenti in uno team specificato di rispondere alle chiamate per gli altri membri del team. Funzionalità abilitata per impostazione predefinita.
    
- Il **reindirizzamento PSTN** consente di reindirizzare le chiamate effettuate dagli utenti assegnati a questo criterio ad altri utenti dell'organizzazione sulla rete PSTN, in caso di congestione o non disponibilità della rete WAN. Funzionalità abilitata per impostazione predefinita.
    
- L'**override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni per i criteri di controllo di ammissione di chiamata per un particolare utente. Funzionalità disabilitata per impostazione predefinita.
    
- **L'analisi delle chiamate** dannose consente agli utenti di segnalare chiamate dannose utilizzando il client Skype for Business e quindi contrassegna tali chiamate nei record dettagli chiamata. Questa funzionalità è disabilitata per impostazione predefinita.
    
- **L'escape** della segreteria telefonica impedisce che le chiamate vengano instradati immediatamente al sistema di segreteria telefonica del telefono cellulare dell'utente quando è configurato lo squillo simultaneo e il telefono è spento, fuori batteria o fuori portata ed è basato su un valore timer. Questa impostazione abilita e disabilita il timer e imposta il valore del timer. Può essere configurato solo utilizzando Skype for Business Server Management Shell. Questa funzionalità è disabilitata per impostazione predefinita.
    
- L'inoltro di chiamata e gli utilizzi **PSTN** di squillo simultaneo consentono agli amministratori di specificare lo stesso utilizzo PSTN del criterio vocale per l'inoltro di chiamata e lo squillo simultaneo, limitare l'inoltro di chiamata e lo squillo simultaneo solo agli utenti Skype for Business interni oppure specificare un utilizzo PSTN personalizzato diverso dall'utilizzo PSTN del criterio vocale. Il comportamento predefinito prevede l'applicazione di un utilizzo PSTN uguale al criterio vocale per l'inoltro di chiamata e lo squillo simultaneo.
    
### <a name="pstn-usage-records"></a>Record di utilizzo PSTN

A ogni criterio vocale dovrebbero essere associati uno o più record di utilizzo PSTN. Gli utilizzi PSTN possono essere associati a un criterio vocale solo ai fini dello squillo simultaneo e dell'inoltro di chiamata. 
  
> [!NOTE]
> L'ordine degli utilizzi PSTN è fondamentale perché, in fase di abbinamento degli utenti alle route, la funzionalità di routing in uscita confronta gli utilizzi PSTN in ordine, dall'alto verso il basso. Se il primo utilizzo corrisponde alla route della chiamata, viene utilizzata tale route. In caso contrario, la funzionalità di routing in uscita cerca l'utilizzo PSTN successivo nell'elenco e continua fino a trovare una corrispondenza. In effetti, gli utilizzi PSTN successivi rappresentano un backup nel caso il primo nell'elenco non sia disponibile. 
  
## <a name="pstn-usage-records"></a>Record utilizzo PSTN

La pianificazione dei record utilizzo PSTN consiste principalmente nell'elencare tutte le autorizzazioni per le chiamate attualmente in vigore nell'organizzazione, dal CEO fino ai dipendenti a tempo determinato, ai consulenti e al personale contingente. Questo processo offre anche la possibilità di riesaminare le autorizzazioni esistenti per le chiamate e modificarle. È possibile creare record utilizzo PSTN solo per le autorizzazioni per le chiamate applicabili agli utenti previsti di VoIP aziendale, ma potrebbe essere una soluzione a lungo termine più efficace creare record utilizzo PSTN per tutte le autorizzazioni per le chiamate, anche se alcune potrebbero non essere al momento applicabili al gruppo di utenti da abilitare per VoIP aziendale. In questo modo, se le autorizzazioni per le chiamate subiscono modifiche o vengono aggiunti nuovi utenti con autorizzazioni diverse per le chiamate, saranno già stati creati i record utilizzo PSTN necessari.
  
Nella tabella seguente viene illustrata una tipica tabella di record di utilizzo PSTN:
  
**Record di utilizzo PSTN**

|**Attributo telefono**|**Descrizione**|
|:-----|:-----|
|Locale  <br/> |Chiamate locali  <br/> |
|Long-Distance  <br/> |Chiamate interurbane  <br/> |
|Internazionale  <br/> |Chiamate internazionali  <br/> |
|Delhi  <br/> |Dipendenti a tempo pieno di Delhi  <br/> |
|Redmond  <br/> |Dipendenti a tempo pieno di Redmond  <br/> |
|RedmondTemps  <br/> |Dipendenti a tempo determinato di Redmond  <br/> |
|Zurich  <br/> |Dipendenti a tempo pieno di Zurigo  <br/> |
   
I record di utilizzo PSTN non svolgono di per sé alcuna funzione. Per utilizzarli, è necessario associarli agli elementi seguenti:
  
- Criteri vocali, assegnati agli utenti.
    
- Route, assegnate ai numeri di telefono.
    
## <a name="voice-routes"></a>Route vocali

Le route di chiamata specificano Skype for Business Server le chiamate in uscita effettuate da VoIP aziendale utenti. Quando un utente compone un numero, il Front End Server normalizza la stringa di composizione nel formato E.164, se necessario, e tenta di associarlo a un URI SIP. Se il server non riesce a effettuare l'associazione, applica la logica di routing delle chiamate in uscita in base al numero. Il passaggio finale della definizione della logica consiste nel creare una route di chiamata denominata separata per ogni insieme di numeri di telefono di destinazione elencati in ogni dial plan.
  
Prima di definire le route delle chiamate in uscita, è necessario completare le operazioni seguenti:
  
- Distribuire uno o più trunk.
    
- Creare dial plan in base alle necessità per siti, individui e oggetti contatto.
    
- Creare record di utilizzo PSTN (Public Switched Telephone Network).
    
Per abilitare il routing delle chiamate in uscita, è inoltre necessario creare e assegnare uno o più criteri vocali. È possibile eseguire questa attività prima o dopo avere definito le route delle chiamate in uscita.
  
Per ogni route, è necessario specificare:
  
- Un nome in base al quale la route possa essere facilmente identificata.
    
- Una descrizione facoltativa per i casi in cui il nome da solo potrebbe non essere sufficiente per descrivere la route.
    
- Il formato di corrispondenza dell'espressione regolare per l'identificazione dei numeri di telefono di destinazione a cui è applicata la route e le eccezioni a cui il formato di corrispondenza non deve essere applicato.
    
- Uno o più trunk che si desidera assegnare alla route.
    
- I record di utilizzo PSTN di cui gli utenti devono disporre per chiamare i numeri corrispondenti all'espressione regolare dei numeri di telefono di destinazione.
    
È possibile specificare le route di chiamata nel Skype for Business Server pannello di controllo. Queste route di chiamata popolano la tabella di routing del server, che Skype for Business Server per instradare le chiamate destinate alla rete PSTN.
  
### <a name="mn-trunk-support"></a>Supporto dei trunk M:N

Skype for Business Server offre flessibilità nel modo in cui le chiamate vengono instradati alla rete PSTN. Una route vocale specifica un insieme di trunk alla rete PSTN che possono essere utilizzati per una determinata chiamata vocale. Un trunk associa un Mediation Server e un numero di porta a un gateway PSTN e a un numero di porta di attesa. Questa associazione logica consente a un Mediation Server di essere associato a più gateway e di avere più connessioni allo stesso gateway. Quando si definisce una route di chiamata, si specificano i trunk associati a tale route, ma non si specificano quali Mediation Server sono associati alla route. Per creare trunk definendo le relazioni tra Mediation Server e gateway PSTN, IP-PBX e session border controller (SBC), utilizzare il Generatore di topologie.
  
### <a name="least-cost-routing"></a>Least Cost Routing

La possibilità di specificare i trunk verso cui vengono instradati diversi numeri consente di determinare quali route comportano i costi minori e di implementarle di conseguenza. In generale, per ridurre i costi delle chiamate interurbane, è consigliabile scegliere il trunk con il gateway più vicino alla località del numero di destinazione. Se ad esempio ci si trova a New York e si sta chiamando un numero a Roma, è possibile trasmettere la chiamata tramite la rete IP al trunk con il gateway nell'ufficio di Roma, sostenendo in questo modo solo i costi di una chiamata locale.
  
Per un esempio dell'utilizzo del routing meno costose, tenere presente quanto segue: Fabrikam decide di consentire agli utenti tedeschi di comporre numeri statunitensi utilizzando il trunk statunitense. Fabrikam desidera inoltre configurare il sistema in modo che tutte le chiamate degli utenti di Skype for Business Server statunitensi verso la Germania e i paesi/aree geografiche adiacenti terminino nel trunk con il gateway in Germania. Questo instradamento consente di risparmiare, perché una chiamata dalla Germania all'Austria, ad esempio, è meno costosa di una chiamata dagli Stati Uniti all'Austria.
  
### <a name="translating-outbound-dial-strings"></a>Conversione delle stringhe di composizione in uscita

Skype for Business Server tutte le stringhe di composizione devono essere normalizzate nel formato E.164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Per i trunk con gateway o IX (Private Branch Exchange) che richiedono numeri convertiti in formati di composizione locali, Skype for Business Server consente di creare una o più regole che consentono di modificare il numero chiamato (ad esempio, URI di richiesta) prima di instradarlo al trunk. È ad esempio possibile scrivere una regola per rimuovere il prefisso +44 all'inizio di una stringa di composizione e sostituirlo con 0144.
  
Con Skype for Business Server, è possibile creare una o più regole che assistono nella modifica del numero chiamante prima di instradarlo al trunk.
  
Nella pianificazione dei trunk che associano coppie gateway:porta a coppie Mediation Server:porta, può essere utile raggruppare i trunk con requisiti di composizione locali simili e quindi ridurre il numero di regole di conversione necessarie e il tempo necessario per scriverli.
  
### <a name="configuring-caller-id"></a>Configurazione dell'ID chiamante

Skype for Business Server consente di modificare l'ID chiamante per le chiamate in uscita. Ad esempio, se un'organizzazione desidera mascherare gli interni di chiamata diretta dei dipendenti e sostituirli con il numero aziendale o di reparto generico, un amministratore può farlo utilizzando il Pannello di controllo di Skype for Business Server per eliminare l'ID chiamante e sostituirlo con un ID chiamante alternativo specificato. Nella pianificazione della logica di instradamento, prendere in considerazione i singoli utenti, i gruppi e i siti per i quali si desidera utilizzare questa opzione, ad esempio anche per tutti i dipendenti.
  
> [!NOTE]
> Per le chiamate reinoltrate tramite PSTN, verrà visualizzato l'ID chiamante generico anziché quello originario. La chiamata potrebbe quindi ignorare eventuali impostazioni Non disturbare o di privacy configurate dal destinatario. 
  
### <a name="additional-routing-logic"></a>Logica di routing aggiuntiva

Durante la creazione delle route delle chiamate in uscita, tenere presente i fattori seguenti che influiscono sulla logica di routing:
  
- Nelle situazioni in cui viene effettuata una chiamata attraverso un confine federato, la parte dell'URI relativa al dominio viene utilizzata per instradare la chiamata all'azienda responsabile dell'applicazione della logica di routing in uscita.
    
- Se la parte dell'URI della richiesta relativa al dominio non contiene un dominio supportato per l'azienda, il componente di routing in uscita nel server non elabora la chiamata.
    
- Se un utente non è abilitato per VoIP aziendale, il server applica un'altra logica di routing, come appropriato.
    
- Se una chiamata viene instradata a un gateway completamente occupato (tutte le linee di trunk sono occupate), il gateway rifiuta la chiamata e la logica di routing in uscita la reindirizza alla successiva route Least Cost Routing. È necessario valutare con attenzione questo aspetto perché un gateway adatto nelle dimensioni a una piccola sede all'estero, ad esempio Zurigo, potrebbe in realtà trasportare una quantità significativa di traffico non locale per le chiamate internazionali dirette in Svizzera. Se il gateway non presenta dimensioni adeguate a questo traffico aggiuntivo, le chiamate dirette in Svizzera potrebbero essere instradate mediante un gateway in Germania, con conseguenti tariffe più alte.
