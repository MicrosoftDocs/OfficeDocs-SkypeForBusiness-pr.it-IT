---
title: Pianificare il routing vocale in uscita in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: Informazioni sul routing vocale in uscita in Skype for Business Server VoIP aziendale, incluse le impostazioni di routing delle chiamate, i dial plan, le regole di normalizzazione, i criteri vocali, i record di utilizzo PSTN e le route vocali.
ms.openlocfilehash: bb57d824d9d44886973f60b3061b2e86e949f071
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187586"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Pianificare il routing vocale in uscita in Skype for Business Server
 
Informazioni sul routing vocale in uscita in Skype for Business Server VoIP aziendale, incluse le impostazioni di routing delle chiamate, i dial plan, le regole di normalizzazione, i criteri vocali, i record di utilizzo PSTN e le route vocali.
  
Il routing delle chiamate in uscita si applica alle chiamate vocali aziendali destinate a un gateway PSTN (Public Switched Telephone Network), trunk o PBX (Private Branch Exchange). Quando un utente di Skype for business effettua una chiamata, il server normalizza il numero di telefono in formato E. 164, se necessario, e cerca di confrontarlo con un URI SIP. Se il server non riesce a eseguire la corrispondenza, applica la logica di routing delle chiamate in uscita in base alla stringa di chiamata fornita. La logica viene definita configurando le impostazioni del server descritte nella tabella seguente.
  
**Impostazioni di routing delle chiamate in uscita di Skype for Business Server**

|**Oggetto**|**Descrizione**|
|:-----|:-----|
|Dial plan  <br/> |Un dial plan è un set denominato di regole di normalizzazione che converte i numeri di telefono per una posizione denominata, un singolo utente o un oggetto contatto in un unico formato standard (E. 164) per scopi di autorizzazione del telefono e routing delle chiamate.  <br/> |
|Regola di normalizzazione  <br/> |Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi in diversi formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato. La stessa stringa di chiamata può essere interpretata e tradotta in modo diverso, a seconda della posizione in cui è stata chiamata e della persona o dell'oggetto contatto che effettua la chiamata. Un set di regole di normalizzazione associato a una determinata posizione costituisce un dial plan.  <br/> |
|Criteri vocali  <br/> |Un criterio vocale associa uno o più record di utilizzo PSTN a un utente o a un gruppo di utenti. Un criterio vocale offre anche un elenco delle funzionalità di chiamata che è possibile abilitare o disabilitare.  <br/> |
|Record utilizzo PSTN  <br/> |Un record di utilizzo PSTN specifica una classe di chiamata, ad esempio Internal, local o Long Distance, che può essere eseguita da vari utenti o gruppi di utenti in un'organizzazione.  <br/> |
|Route chiamata  <br/> |Una route di chiamata associa i numeri di telefono di destinazione con tronchi particolari e record di utilizzo PSTN. Un gateway PSTN è considerato un trunk.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Dial plan e regole di normalizzazione

Un dial plan è un set denominato di regole di normalizzazione che converte i numeri di telefono per una posizione denominata, un singolo utente o un oggetto contatto in un unico formato standard (E. 164) per scopi di autorizzazione del telefono e routing delle chiamate. 
  
Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi in diversi formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato. La stessa stringa di chiamata può essere interpretata e tradotta in modo diverso, a seconda della posizione in cui viene chiamata e della persona o dell'oggetto contatto che effettua la chiamata.
  
### <a name="dial-plan-scope"></a>Ambito di dial plan

L'ambito di un piano di chiamata determina il livello gerarchico in cui il piano di chiamata può essere applicato. In Skype for Business Server è possibile assegnare un utente a un dial plan specifico per utente. Se non è assegnato un piano di chiamata, viene applicato il dial plan del pool Front-end. Se non è disponibile un dial plan per pool Front-End, viene applicato il dial plan del sito. Infine, se non è disponibile un altro dial plan per l'utente, viene applicato il dial plan globale.
  
I client ottengono i livelli di ambito dei dial plan tramite le impostazioni di provisioning in banda fornite quando gli utenti accedono a Skype for business. L'amministratore può gestire e assegnare livelli di ambito di dial plan usando il pannello di controllo di Skype for Business Server.
  
> [!NOTE]
> Il dial plan di gateway PSTN (Public Switched Telephone Network) a livello di servizio viene applicato alle chiamate in arrivo da un determinato gateway. 
  
I livelli di ambito dei dial plan sono definiti come segue:
  
- **Dial plan utente**: può essere assegnato a singoli utenti, gruppi o oggetti contatto. Le applicazioni vocali possono cercare un dial plan per utente quando viene ricevuta una chiamata con il set di impostazioni del telefono-impostazione predefinita per l'utente. Ai fini dell'assegnazione di un dial plan, un oggetto contatto viene considerato come singolo utente.
    
- **Dial plan per pool**: può essere creato a livello di servizio per qualsiasi gateway o registrar PSTN nella topologia. Per definire un dial plan per pool, è necessario specificare il servizio specifico (gateway PSTN o pool di registrar) a cui si applica il dial plan. 
    
- **Dial plan**: può essere creato per un intero sito, fatta eccezione per gli utenti, i gruppi o gli oggetti contatto assegnati a un dial plan di pool o a un dial plan utente. Per definire un dial plan di sito, è necessario specificare il sito a cui si applica il dial plan.
    
- **Dial plan globale**: il dial plan predefinito installato con il prodotto. È possibile modificare il dial plan globale, ma non è possibile eliminarlo. Questo dial plan si applica a tutti gli utenti di VoIP aziendale, ai gruppi e agli oggetti contatto nella distribuzione, a meno che non si configuri e assegni un dial plan con un ambito più specifico.
    
### <a name="planning-for-dial-plans"></a>Pianificazione per i dial plan

Per pianificare un dial plan, eseguire le operazioni seguenti:
  
- Elencare tutte le impostazioni locali in cui l'organizzazione ha un ufficio.
    
    L'elenco deve essere aggiornato e completo. Sarà necessario rivedere l'evoluzione dell'organizzazione aziendale. In un'azienda di grandi dimensioni multinazionali con numerose piccole filiali, può essere un'attività che richiede tempo.
    
- Identificare i modelli di numero validi per ogni sito.
    
    La parte più lunga della pianificazione dei dial plan sta identificando i modelli di numero validi per ogni sito. In alcuni casi, è possibile copiare le regole di normalizzazione scritte per un dial plan ad altri piani di chiamata, in particolare se i siti corrispondenti si trovano all'interno dello stesso paese/area geografica o addirittura in un continente. In altri casi, le piccole modifiche ai numeri in un dial plan possono essere sufficienti per usarle in altri piani di chiamata.
    
- Sviluppare uno schema a livello di organizzazione per la denominazione dei dial plan.
    
    L'adozione di uno schema di denominazione standard assicura la coerenza in tutta l'organizzazione e rende più semplici la manutenzione e gli aggiornamenti.
    
- Decidere se è necessario disporre di più piani di chiamata per una singola posizione. 
    
    Se l'organizzazione mantiene un singolo dial plan in più posizioni, potrebbe essere comunque necessario creare un dial plan separato per gli utenti di VoIP aziendale che eseguono la migrazione da un PBX (Private Branch Exchange) e che devono mantenere le proprie estensioni esistenti.
    
- Decidere se i piani di chiamata per utente sono obbligatori. Se ad esempio sono presenti utenti in un sito di succursale registrati con il sito centrale o se si hanno utenti registrati in un Survivable Branch Appliance, è possibile prendere in considerazione scenari di Dialing speciali per tali utenti che usano i piani di chiamata per utente e le regole di normalizzazione . Per informazioni dettagliate, vedere [pianificare la resilienza di VoIP aziendale in Skype for Business Server](enterprise-voice-resiliency.md).
    
- Determinare l'ambito di dial plan (come descritto in precedenza in questo argomento).
    
Per creare un dial plan, specificare i valori nei campi seguenti, in base alle esigenze, usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
#### <a name="name-and-simple-name"></a>Nome e nome semplice

Per i piani di chiamata utente, devi specificare un nome descrittivo che identifichi gli utenti, i gruppi o gli oggetti contatto a cui verrà assegnato il dial plan. Per i piani di chiamata del sito, il campo nome viene prepopolato con il nome del sito e non può essere modificato. Per i piani di chiamata in pool, il campo nome viene prepopolato con il gateway PSTN o con il nome di dominio completo (FQDN) del pool Front end e non può essere modificato.
  
Il nome semplice dial plan viene prepopolato con una stringa derivata dal nome del dial plan. Il campo Nome semplice è modificabile, per creare una convenzione di denominazione più descrittiva per i piani di chiamata. Il valore del nome TheSimple non può essere vuoto e deve essere univoco. L'approccio ideale è sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzare questa convenzione in modo coerente in tutte le sedi e per tutti gli utenti.
  
#### <a name="description"></a>Descrizione

È consigliabile digitare il nome comune e riconoscibile della posizione geografica in cui si applica il piano di chiamata corrispondente. Ad esempio, se il nome del dial plan è London.Contoso.com, la descrizione consigliata sarà Londra. 
  
#### <a name="dial-in-conferencing-region"></a>Area servizi di conferenza telefonica con accesso esterno

Se si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario specificare un'area per i servizi di conferenza telefonica con chiamata in ingresso per associare i numeri per i servizi di conferenza telefonica con dial plan. 
  
#### <a name="external-access-prefix"></a>Prefisso di accesso esterno

È possibile specificare un prefisso di accesso esterno composto da un massimo di quattro caratteri \*(#, e 0-9) se gli utenti devono chiamare una o più cifre iniziali aggiuntive (ad esempio, 9) per ottenere una linea esterna.
  
> [!NOTE]
> Se si specifica un prefisso di accesso esterno, non è necessario creare una regola di normalizzazione aggiuntiva per includere il prefisso. 
  
### <a name="normalization-rules"></a>Regole di normalizzazione

Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi in diversi formati devono essere instradati per la posizione denominata. La stessa stringa numerica può essere interpretata e tradotta in modo diverso, a seconda della posizione da cui viene composta. Le regole di normalizzazione sono necessarie per il routing delle chiamate perché gli utenti possono usare vari formati per l'immissione di numeri di telefono nei rispettivi elenchi di contatti.
  
La normalizzazione dei numeri di telefono forniti dall'utente fornisce un formato coerente che facilita le attività seguenti:
  
- Corrisponde a un numero composto al SIP-URI del destinatario previsto.
    
- Applicare le regole di autorizzazione di chiamata alla parte chiamante.
    
I campi numero seguenti sono tra quelli che potrebbero essere necessari per le regole di normalizzazione:
  
- Dial plan
    
- Codice paese
    
- Prefisso
    
- Lunghezza dell'estensione
    
- Prefisso del sito
    
#### <a name="creating-normalization-rules"></a>Creazione di regole di normalizzazione

Le regole di normalizzazione usano le espressioni regolari .NET Framework per specificare modelli numerici di abbinamento che il server utilizza per tradurre le stringhe di composizione in formato E.164 allo scopo di eseguire la ricerca inversa. È possibile creare regole di normalizzazione nel pannello di controllo di Skype for Business Server immettendo le espressioni manualmente oppure immettendo le cifre iniziali e la lunghezza delle stringhe di chiamata da abbinare e lasciando il pannello di controllo di Skype for Business Server genera l'espressione regolare corrispondente. In entrambi i casi, al termine, è possibile immettere un numero di test per verificare che la regola di normalizzazione funzioni come previsto.
  
Per informazioni dettagliate sull'uso delle espressioni regolari di .NET Framework, vedere ["espressioni regolari di .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
#### <a name="sample-normalization-rules"></a>Esempio di regole di normalizzazione
<a name="BKMK_SampleNormalizationRules"> </a>

La tabella seguente mostra esempi di regole di normalizzazione scritte sotto forma di espressioni regolari .NET Framework. Si tratta solo di esempi, non di regole fisse di riferimento per la creazione di regole di normalizzazione.
  
**Tabella 1. regole di normalizzazione con le espressioni regolari di .NET Framework**

|**Nome regola**|**Descrizione**|**Schema numerico**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Converte le estensioni a 4 cifre  <br/> |^ (\d{4}) $  <br/> |+1425555$1  <br/> |0100 viene convertito in +14255550100  <br/> |
|5digitExtension  <br/> |Converte le estensioni a 5 cifre  <br/> |^ 5 (\d{4}) $  <br/> |+1425555$1  <br/> |50100 viene convertito in +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte i numeri a 7 cifre in numeri locali di Redmond  <br/> |^ (\d{7}) $  <br/> |+1425$1  <br/> |5550100 viene convertito in +14255550100  <br/> |
|7digitcallingDallas  <br/> |Converte i numeri a 7 cifre in numeri locali di Dallas  <br/> |^ (\d{7}) $  <br/> |+ 1972 $1  <br/> |5550100 viene convertito in + 19725550100  <br/> |
|10digitcallingUS  <br/> |Converte i numeri a 10 cifre negli Stati Uniti  <br/> |^ (\d{10}) $  <br/> |+ 1 $1  <br/> |2065550100 viene convertito in + 12065550100  <br/> |
|LDCallingUS  <br/> |Converte i numeri con i prefissi a lunga distanza negli Stati Uniti  <br/> |^ 1 (\d{10}) $  <br/> |+ $1  <br/> |12145550100 viene convertito in + 2145550100  <br/> |
|IntlCallingUS  <br/> |Converte i numeri con i prefissi internazionali negli Stati Uniti  <br/> |^ 011 (\d\*) $  <br/> |+ $1  <br/> |01191445550100 viene convertito in + 91445550100  <br/> |
|RedmondOperator  <br/> |Converte 0 in operatore Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 viene convertito in +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte i numeri con il prefisso on-net (6) e il codice del sito Redmond (222)  <br/> |^ 6222 (\d{4}) $  <br/> |+1425555$1  <br/> |62220100 viene convertito in +14255550100  <br/> |
|NYSitePrefix  <br/> |Converte i numeri con il prefisso on-net (6) e il codice del sito NY (333)  <br/> |^ 6333 (\d{4}) $  <br/> |+ 1202555 $1  <br/> |63330100 viene convertito in + 12025550100  <br/> |
|DallasSitePrefix  <br/> |Converte i numeri con il prefisso on-net (6) e il codice del sito di Dallas (444)  <br/> |^ 6444 (\d{4}) $  <br/> |+ 1972555 $1  <br/> |64440100 viene convertito in + 19725550100  <br/> |
   
La tabella seguente illustra un piano di chiamata di esempio per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione indicate nella tabella precedente.
  
**Tabella 2. Dial plan Redmond basato sulle regole di normalizzazione visualizzate nella tabella 1**

|**Redmond. FQDNforesta**|
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
> I nomi delle regole di normalizzazione mostrati nella tabella precedente non includono spazi, ma questa è solo una scelta. Il primo nome nella tabella, ad esempio, avrebbe potuto essere "5 digit extension" o "5-digit Extension" e sarebbe stato comunque valido. 
  
## <a name="voice-policies"></a>Criteri vocali

I criteri vocali di Skype for Business Server definiscono quanto segue per ogni utente, sito o organizzazione a cui è assegnato il criterio:
  
- Un set di funzionalità di chiamata che possono essere abilitate o disabilitate per determinare la funzionalità VoIP aziendale disponibile per gli utenti.
    
- Un set di record di utilizzo PSTN (Public Switched Telephone Network) che definiscono i tipi di chiamate autorizzate. 
    
La procedura seguente consente di pianificare i criteri vocali necessari per la distribuzione di VoIP aziendale:
  
- Determinare come configurare il criterio vocale globale (i criteri vocali predefiniti installati con il prodotto). Questo criterio si applica a tutti gli utenti di VoIP aziendale a cui non è assegnato esplicitamente un criterio a livello di sito o per utente.
    
- Identificare i criteri vocali a livello di sito che potrebbero essere necessari.
    
- Identificare qualsiasi criterio vocale per utente che potrebbe essere necessario.
    
- Decidere quali funzionalità di chiamata abilitare per ogni criterio vocale.
    
- Determinare i record di utilizzo PSTN da configurare per ogni criterio vocale.
    
### <a name="voice-policy-scope"></a>Ambito dei criteri vocali

L'ambito dei criteri vocali determina il livello gerarchico in cui è possibile applicare i criteri. In Skype for Business Server è possibile configurare i criteri vocali con i livelli di ambito seguenti (elencati tra i più specifici per i più generali).
  
- I **criteri vocali dell'utente** possono essere assegnati a singoli utenti, gruppi o oggetti contatto. Questo è il criterio di livello più basso. I criteri vocali dell'utente possono essere distribuiti per abilitare le funzionalità per determinati utenti o gruppi in un sito, ma non per altri nello stesso sito. Ad esempio, potresti voler disabilitare la chiamata a lunga distanza per alcuni dipendenti. Allo scopo di assegnare un criterio vocale, un oggetto contatto viene considerato come un singolo utente.
    
    > [!NOTE]
    > È consigliabile distribuire un criterio vocale utente per gli utenti di VoIP aziendale del sito succursale registrati con la distribuzione del sito centrale o gli utenti registrati in un Survivable Branch Appliance. 
  
- I **criteri vocali del sito** si applicano a un intero sito, eccetto per gli utenti, i gruppi o gli oggetti contatto assegnati a un criterio vocale per l'utente. Per definire un criterio vocale del sito, è necessario specificare il sito a cui si applicano i criteri. Se non viene assegnato un criterio vocale per l'utente, viene usato il criterio vocale del sito.
    
- Il criterio vocale **globale** è il criterio vocale predefinito che viene installato con il prodotto. È possibile modificare il criterio vocale globale per soddisfare le esigenze specifiche dell'organizzazione, ma non è possibile rinominarla o eliminarla. Questo criterio vocale si applica a tutti gli utenti di VoIP aziendale, ai gruppi e agli oggetti contatto nella distribuzione, a meno che non si configuri e assegni un criterio vocale con un ambito più specifico. Se si vuole disabilitare completamente questo criterio, assicurarsi che tutti i siti e gli utenti dispongano di criteri personalizzati assegnati.
    
### <a name="call-features"></a>Caratteristiche delle chiamate

È possibile abilitare o disabilitare le funzionalità di chiamata seguenti per ogni criterio vocale:
  
- L' **inoltro di chiamata** consente agli utenti di inoltrare le chiamate ad altri telefoni e dispositivi client. Abilitato per impostazione predefinita.
    
- La **delega** consente agli utenti di specificare ad altri utenti di inviare e ricevere chiamate per proprio conto. Abilitato per impostazione predefinita.
    
- Il **trasferimento** delle chiamate consente agli utenti di trasferire le chiamate ad altri utenti. Abilitato per impostazione predefinita.
    
- **Call Park** consente agli utenti di parcheggiare le chiamate e quindi prendere la chiamata da un altro telefono o client. Disabilitata per impostazione predefinita.
    
- La **chiamata simultanea** consente alle chiamate in arrivo di squillare su un altro telefono, ad esempio un cellulare o altri dispositivi endpoint. Abilitato per impostazione predefinita.
    
- La **chiamata del team** consente agli utenti di un team definito di rispondere alle chiamate per gli altri membri del team. Abilitato per impostazione predefinita.
    
- La reinstradazione **PSTN** consente alle chiamate effettuate dagli utenti a cui è assegnato questo criterio ad altri utenti aziendali di essere reinstradati nella rete PSTN (Public Switched Telephone Network) se la WAN è congestionata o non disponibile. Abilitato per impostazione predefinita.
    
- **L'override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni sui criteri di controllo ammissione chiamata per un determinato utente. Disabilitata per impostazione predefinita.
    
- La **traccia di chiamata** non consentita consente agli utenti di segnalare chiamate illecite tramite il client Skype for business e quindi contrassegna tali chiamate nei record dettagli chiamata. Disabilitata per impostazione predefinita.
    
- La funzione di **escape della segreteria telefonica** impedisce che le chiamate vengano immediatamente indirizzate al sistema di segreteria telefonica dell'utente quando è configurato lo squillo simultaneo e che il telefono sia disattivato, fuori batteria o fuori portata e sia basato su un valore timer. Questa impostazione Abilita e Disabilita il timer e imposta il valore del timer. La configurazione può essere configurata solo con Skype for Business Server Management Shell. Disabilitata per impostazione predefinita.
    
- L' **inoltro di chiamata e l'uso simultaneo di chiamate PSTN** consentono agli amministratori di specificare lo stesso utilizzo PSTN dei criteri vocali per l'inoltro di chiamata e lo squillo simultaneo, limitare l'inoltro di chiamata e lo squillo simultaneo all'interno di Skype for Solo per gli utenti aziendali o specificare un uso PSTN personalizzato diverso dall'uso PSTN del criterio vocale. L'impostazione predefinita consiste nell'usare lo stesso utilizzo PSTN del criterio vocale per l'inoltro di chiamata e lo squillo simultaneo.
    
### <a name="pstn-usage-records"></a>Record utilizzo PSTN

Ogni criterio vocale deve avere uno o più record di utilizzo PSTN associati. Gli usi PSTN possono essere associati a un criterio vocale allo scopo di effettuare chiamate simultanee e inoltro di chiamata. 
  
> [!NOTE]
> L'ordine di utilizzo PSTN è fondamentale perché in corrispondenza degli utenti alle route la funzionalità di routing in uscita confronta gli usi PSTN dall'alto verso il basso. Se il primo utilizzo corrisponde alla route di chiamata, viene usata tale route. In caso contrario, la funzionalità di routing in uscita analizza il successivo utilizzo PSTN nell'elenco e continua fino a quando non viene trovata una corrispondenza. In effetti, i successivi usi PSTN includono il backup se il primo nell'elenco non è disponibile. 
  
## <a name="pstn-usage-records"></a>Record utilizzo PSTN

La pianificazione dei record di utilizzo PSTN consiste principalmente nell'elencare tutte le autorizzazioni di chiamata attualmente in vigore nell'organizzazione, dall'amministratore delegato a lavoratori temporanei, consulenti e personale contingente. Questo processo offre anche l'opportunità di riesaminare le autorizzazioni di chiamata esistenti e di modificarle. È possibile creare record di utilizzo PSTN solo per le autorizzazioni di chiamata applicabili agli utenti di VoIP aziendale previsti, ma una soluzione migliore a lungo raggio può essere quella di creare record di utilizzo PSTN per tutte le autorizzazioni di chiamata, indipendentemente dal fatto che alcuni potrebbero non essere attualmente si applicano al gruppo di utenti che deve essere abilitato per VoIP aziendale. Se le autorizzazioni di chiamata cambiano o vengono aggiunti nuovi utenti con autorizzazioni di chiamata diverse, saranno già stati creati i record di utilizzo PSTN necessari.
  
La tabella seguente mostra una tipica tabella di utilizzo PSTN.
  
**Record utilizzo PSTN**

|**Attributo Phone**|**Descrizione**|
|:-----|:-----|
|Locale  <br/> |Chiamate locali  <br/> |
|Lunga distanza  <br/> |Chiamate interurbane  <br/> |
|Internazionale  <br/> |Chiamate internazionali  <br/> |
|Delhi  <br/> |Dipendenti a tempo pieno di Delhi  <br/> |
|Redmond  <br/> |Dipendenti a tempo pieno Redmond  <br/> |
|RedmondTemps  <br/> |Dipendenti temporanei Redmond  <br/> |
|Zurigo  <br/> |Dipendenti a tempo pieno di Zurigo  <br/> |
   
Da solo, i record di utilizzo PSTN non eseguono alcuna operazione. Affinché funzioni, è necessario associarle con le operazioni seguenti:
  
- Criteri vocali, assegnati agli utenti.
    
- Route, assegnate ai numeri di telefono.
    
## <a name="voice-routes"></a>Route vocali

Le route di chiamata specificano in che modo Skype for Business Server gestisce le chiamate in uscita poste dagli utenti VoIP aziendale. Quando un utente compone un numero, il server front-end normalizza la stringa di chiamata in formato E. 164, se necessario, e tenta di associarla a un URI SIP. Se il server non riesce a eseguire la corrispondenza, applica la logica di routing delle chiamate in uscita in base al numero. Il passaggio finale per definire la logica consiste nel creare una route di chiamata separata denominata per ogni set di numeri di telefono di destinazione elencati in ogni dial plan.
  
Prima di definire le route di chiamata in uscita, è necessario eseguire la procedura seguente:
  
- Distribuire uno o più trunk.
    
- Creare piani di chiamata in base alle esigenze per siti, singoli e oggetti contatto.
    
- Creare record di utilizzo PSTN (Public Switched Telephone Network).
    
Per abilitare il routing delle chiamate in uscita, è inoltre necessario creare e assegnare uno o più criteri vocali. Questa operazione può essere eseguita prima o dopo la definizione delle route di chiamata in uscita.
  
Per ogni route devi specificare:
  
- Nome con cui la route può essere facilmente identificata.
    
- Descrizione facoltativa nei casi in cui il nome da solo potrebbe non essere sufficiente per descrivere la route.
    
- Modello di corrispondenza delle espressioni regolari che identifica i numeri di telefono di destinazione a cui viene applicata la route, insieme alle eccezioni a cui non deve essere applicato il modello corrispondente.
    
- Uno o più trunk che si desidera assegnare alla route.
    
- I record di utilizzo PSTN che gli utenti devono avere per chiamare i numeri corrispondenti all'espressione regolare numero di telefono di destinazione.
    
Puoi specificare le route di chiamata nel pannello di controllo di Skype for Business Server. Queste route di chiamata popolano la tabella di routing del server, che Skype for Business Server usa per instradare le chiamate destinate alla rete PSTN.
  
### <a name="mn-trunk-support"></a>Supporto di M:N trunk

Skype for Business Server offre flessibilità per il modo in cui le chiamate vengono instradate alla rete PSTN. Una route vocale specifica un set di trunk alla rete PSTN che può essere usato per una determinata chiamata vocale. Un trunk associa un Mediation Server e un numero di porta con un gateway PSTN e un numero di porta in ascolto. Questa associazione logica consente a un Mediation Server di essere associato a più gateway e di avere più connessioni allo stesso gateway. Quando si definisce una route di chiamata, è necessario specificare i trunk associati alla route, ma non si specificano i server di mediazione associati alla route. Per creare Trunks definendo le relazioni tra Mediation Server e gateway PSTN, IP-PBX e Session Border Controller (SBCs), usare il generatore di topologie.
  
### <a name="least-cost-routing"></a>Routing con costi minimi

La possibilità di specificare i trunk a cui vengono instradati i vari numeri consente di determinare quali Route incorrono i costi più bassi e di implementarle di conseguenza. La regola generale nella selezione di Trunks consiste nel scegliere il trunk con il gateway più vicino alla posizione del numero di destinazione per ridurre al minimo le spese interurbane. Ad esempio, se ci si trova a New York e si chiama un numero a Roma, è necessario portare la chiamata tramite la rete IP verso il trunk con il gateway nell'ufficio di Roma, in modo da incorrere in una tariffa solo per una chiamata locale.
  
Per un esempio di come potrebbe essere usato il routing con costi minimi, tenere presente quanto segue: Fabrikam decide di consentire agli utenti tedeschi di chiamare i numeri statunitensi usando il trunk degli Stati Uniti. Fabrikam vuole anche configurare il sistema in modo che tutte le chiamate degli utenti di Skype for Business Server in Germania e nei paesi/aree geografiche adiacenti interrompano il trunk con il gateway in Germania. Questo routing consente di risparmiare denaro, perché una chiamata da Germania a Austria, ad esempio, è meno costosa di una chiamata dagli Stati Uniti in Austria.
  
### <a name="translating-outbound-dial-strings"></a>Traduzione di stringhe di chiamata in uscita

Skype for Business Server richiede la normalizzazione di tutte le stringhe di chiamata in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Per i trunk con gateway o PBX (Private Branch Exchange) che richiedono numeri tradotti in formati di chiamata locali, Skype for Business Server consente di creare una o più regole che aiutano a manipolare il numero chiamato (ad esempio, l'URI della richiesta) prima del routing al tronco. Ad esempio, è possibile scrivere una regola per rimuovere + 44 dalla testa di una stringa di chiamata e sostituirla con 0144.
  
Con Skype for Business Server è possibile creare una o più regole che aiutano a manipolare il numero chiamante prima di instradarlo al trunk.
  
Nella pianificazione dei trunk che associano gateway: coppie di porte con Mediation Server: coppie di porte, può essere utile raggruppare trunk con requisiti di chiamata locali simili e quindi ridurre il numero di regole di traduzione necessarie e il tempo necessario per scriverle.
  
### <a name="configuring-caller-id"></a>Configurazione dell'ID chiamante

Skype for Business Server offre un modo per modificare l'ID chiamante per le chiamate in uscita. Ad esempio, se un'organizzazione vuole mascherare le estensioni della chiamata diretta dei dipendenti e sostituirle con il numero generico aziendale o dipartimentale, un amministratore può farlo usando il pannello di controllo di Skype for Business Server per sopprimere l'ID chiamante e sostituirlo con un ID chiamante alternativo specificato. Per pianificare la logica di routing, valutare quali utenti, gruppi, siti è consigliabile usare, magari per tutti i dipendenti.
  
> [!NOTE]
> Per le chiamate che vengono reinstradate tramite la rete PSTN, l'ID chiamante generico verrà presentato al posto dell'ID chiamante originale. In questo modo, la chiamata al bypass non disturba o le impostazioni di privacy che il chiamato può configurare. 
  
### <a name="additional-routing-logic"></a>Logica di routing aggiuntiva

Per creare route di chiamata in uscita, è necessario tenere presenti i fattori seguenti che possono influire sulla logica di routing:
  
- Quando viene stabilita una chiamata su un contorno federato, viene usata la parte Domain dell'URI per instradare la chiamata all'organizzazione responsabile dell'applicazione della logica di routing in uscita.
    
- Se la parte relativa al dominio dell'URI della richiesta non contiene un dominio supportato per l'organizzazione, il componente di routing in uscita nel server non elabora la chiamata.
    
- Se un utente non è abilitato per VoIP aziendale, il server applica altre logiche di routing, a seconda delle esigenze.
    
- Se una chiamata viene indirizzata a un gateway completamente occupato (tutte le linee di trunk sono occupate), il gateway respinge la chiamata e la logica di routing in uscita reindirizza la chiamata alla route di costo inferiore successiva. Prestare questa considerazione, poiché un gateway dimensionato per un piccolo ufficio oltremare (ad esempio Zurigo) può effettivamente trasportare una quantità significativa di traffico non locale per le chiamate internazionali in Svizzera. Se il gateway non è dimensionato correttamente per il traffico aggiuntivo, le chiamate in Svizzera possono essere instradate tramite un gateway in Germania, con conseguente pagamento di pedaggio più ampio.
    

