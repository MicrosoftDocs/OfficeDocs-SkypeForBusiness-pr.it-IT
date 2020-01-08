---
title: 'Lync Server 2013: dial plan e regole di normalizzazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Dial plan e regole di normalizzazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Un dial plan è un set denominato di regole di normalizzazione che converte i numeri di telefono per una posizione denominata, un singolo utente o un oggetto contatto in un unico formato standard (E. 164) per scopi di autorizzazione del telefono e routing delle chiamate.

Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi in diversi formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato. La stessa stringa di chiamata può essere interpretata e tradotta in modo diverso, a seconda della posizione in cui viene chiamata e della persona o dell'oggetto contatto che effettua la chiamata.

<div>

## <a name="dial-plan-scope"></a>Ambito di dial plan

L' *ambito* di un dial plan determina il livello gerarchico in cui è possibile applicare il dial plan. In Lync Server a un utente può essere assegnato un dial plan specifico per utente. Se non è stato assegnato un piano di chiamata, viene applicato il piano di chiamata del pool di registrar. Se non è presente un piano di chiamata per pool di registrar, viene applicato il dial plan del sito. Infine, se non è disponibile un altro dial plan per l'utente, viene applicato il dial plan globale.

I client ottengono i livelli di ambito dei dial plan tramite le impostazioni di provisioning in banda fornite quando gli utenti accedono a Lync Server. L'amministratore può gestire e assegnare livelli di ambito di dial plan tramite il pannello di controllo di Lync Server.

<div>


> [!NOTE]  
> Il dial plan di gateway PSTN (Public Switched Telephone Network) a livello di servizio viene applicato alle chiamate in arrivo da un determinato gateway.



</div>

I livelli di ambito dei dial plan sono definiti come segue:

  - **Dial plan utente:** Possono essere assegnati a singoli utenti, gruppi o oggetti contatto. Le applicazioni vocali possono cercare un dial plan per utente quando viene ricevuta una chiamata con il set di impostazioni del telefono-impostazione predefinita per l'utente. Ai fini dell'assegnazione di un dial plan, un oggetto contatto viene considerato come singolo utente.

  - **Dial plan per pool:** Può essere creato a livello di servizio per qualsiasi gateway o registrar PSTN nella topologia. Per definire un dial plan per pool, è necessario specificare il servizio specifico (gateway PSTN o pool di registrar) a cui si applica il dial plan.

  - **Dial plan di sito:** Può essere creato per un intero sito, fatta eccezione per gli utenti, i gruppi o gli oggetti contatto assegnati a un dial plan per pool o a un dial plan utente. Per definire un dial plan di sito, è necessario specificare il sito a cui si applica il dial plan.

  - **Dial plan globale:** Il dial plan predefinito installato con il prodotto. È possibile modificare il dial plan globale, ma non è possibile eliminarlo. Questo dial plan si applica a tutti gli utenti di VoIP aziendale, ai gruppi e agli oggetti contatto nella distribuzione, a meno che non si configuri e assegni un dial plan con un ambito più specifico.

</div>

<div>

## <a name="planning-for-dial-plans"></a>Pianificazione per i dial plan

Per pianificare un dial plan, eseguire le operazioni seguenti:

  - Elencare tutte le impostazioni locali in cui l'organizzazione ha un ufficio.
    
    L'elenco deve essere aggiornato e completo. Sarà necessario rivedere l'evoluzione dell'organizzazione aziendale. In un'azienda di grandi dimensioni multinazionali con numerose piccole filiali, può essere un'attività che richiede tempo.

  - Identificare i modelli di numero validi per ogni sito.
    
    La parte più lunga della pianificazione dei dial plan sta identificando i modelli di numero validi per ogni sito. In alcuni casi, è possibile copiare le regole di normalizzazione scritte per un dial plan ad altri piani di chiamata, in particolare se i siti corrispondenti si trovano all'interno dello stesso paese/area geografica o addirittura in un continente. In altri casi, le piccole modifiche ai numeri in un dial plan possono essere sufficienti per usarle in altri piani di chiamata.

  - Sviluppare uno schema a livello di organizzazione per la denominazione dei dial plan.
    
    L'adozione di uno schema di denominazione standard assicura la coerenza in tutta l'organizzazione e rende più semplici la manutenzione e gli aggiornamenti.

  - Decidere se è necessario disporre di più piani di chiamata per una singola posizione.
    
    Se l'organizzazione mantiene un singolo dial plan in più posizioni, potrebbe essere comunque necessario creare un dial plan separato per gli utenti di VoIP aziendale che eseguono la migrazione da un PBX (Private Branch Exchange) e che devono mantenere le proprie estensioni esistenti.

  - Decidere se i piani di chiamata per utente sono obbligatori. Se ad esempio sono presenti utenti in un sito di succursale registrati con il sito centrale o se si hanno utenti registrati in un Survivable Branch Appliance, è possibile prendere in considerazione scenari di Dialing speciali per tali utenti che usano i piani di chiamata per utente e le regole di normalizzazione . Per informazioni dettagliate, vedere [requisiti di resilienza dei siti secondari per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Determinare l'ambito di dial plan (come descritto in precedenza in questo argomento).

Per creare un dial plan, specificare i valori nei campi seguenti, in base alle esigenze, usando il pannello di controllo di Lync Server o Lync Server Management Shell.

<div>

## <a name="name-and-simple-name"></a>Nome e nome semplice

Per i piani di chiamata utente, devi specificare un nome descrittivo che identifichi gli utenti, i gruppi o gli oggetti contatto a cui verrà assegnato il dial plan. Per i piani di chiamata del sito, il campo nome viene precompilato con il nome del sito e non può essere modificato. Per i piani di chiamata in pool, il campo nome viene prepopolato con il gateway PSTN o con il nome di dominio completo (FQDN) del pool Front end e non può essere modificato.

Il *nome semplice* dial plan viene precompilato con una stringa derivata dal nome del dial plan. Il campo Nome semplice è modificabile, per creare una convenzione di denominazione più descrittiva per i piani di chiamata. Il valore *nome semplice* non può essere vuoto e deve essere univoco. L'approccio ideale è sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzare questa convenzione in modo coerente in tutte le sedi e per tutti gli utenti.

</div>

<div>

## <a name="description"></a>Descrizione

È consigliabile digitare il nome comune e riconoscibile della posizione geografica in cui si applica il piano di chiamata corrispondente. Ad esempio, se il nome del dial plan è London.Contoso.com, la descrizione consigliata sarà Londra.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>Area servizi di conferenza telefonica con accesso esterno

Se si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario specificare un'area per i servizi di conferenza telefonica con chiamata in ingresso per associare i numeri per i servizi di conferenza telefonica con dial plan.

</div>

<div>

## <a name="external-access-prefix"></a>Prefisso di accesso esterno

Se gli utenti devono chiamare una o più cifre iniziali aggiuntive (ad\#esempio \*9) per ottenere una linea esterna, è possibile specificare un prefisso di accesso esterno composto da un massimo di quattro caratteri (e 0-9).

<div>


> [!NOTE]  
> Se si specifica un prefisso di accesso esterno, non è necessario creare una regola di normalizzazione aggiuntiva per includere il prefisso.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>Regole di normalizzazione

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

<div>

## <a name="creating-normalization-rules"></a>Creazione di regole di normalizzazione

Le regole di normalizzazione usano le espressioni regolari .NET Framework per specificare modelli numerici di abbinamento che il server utilizza per tradurre le stringhe di composizione in formato E.164 allo scopo di eseguire la ricerca inversa. È possibile creare regole di normalizzazione nel pannello di controllo di Lync Server immettendo le espressioni manualmente oppure immettendo le cifre iniziali e la lunghezza delle stringhe di chiamata da corrispondere e lasciando che il pannello di controllo di Lync Server generi il corrispondente espressione regolare per l'utente. In entrambi i casi, al termine, è possibile immettere un numero di test per verificare che la regola di normalizzazione funzioni come previsto.

Per informazioni dettagliate sull'uso delle espressioni regolari di .NET Framework, vedere "espressioni regolari di [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).NET Framework".

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>Esempio di regole di normalizzazione

La tabella seguente mostra esempi di regole di normalizzazione scritte sotto forma di espressioni regolari .NET Framework. Si tratta solo di esempi, non di regole fisse di riferimento per la creazione di regole di normalizzazione.

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>Tabella 1. regole di normalizzazione con le espressioni regolari di .NET Framework

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome regola</th>
<th>Descrizione</th>
<th>Schema numerico</th>
<th>Conversione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>Converte le estensioni a 4 cifre</p></td>
<td><p>^ (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>0100 viene convertito in +14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Converte le estensioni a 5 cifre</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>50100 viene convertito in +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Converte i numeri a 7 cifre in numeri locali di Redmond</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1425$1</p></td>
<td><p>5550100 viene convertito in +14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Converte i numeri a 7 cifre in numeri locali di Dallas</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1972 $1</p></td>
<td><p>5550100 viene convertito in + 19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Converte i numeri a 10 cifre negli Stati Uniti</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+ 1 $1</p></td>
<td><p>2065550100 viene convertito in + 12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Converte i numeri con i prefissi a lunga distanza negli Stati Uniti</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100 viene convertito in + 2145550100</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>Converte i numeri con i prefissi internazionali negli Stati Uniti</p></td>
<td><p>^ 011 (\d *) $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100 viene convertito in + 91445550100</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>Converte 0 in operatore Redmond</p></td>
<td><p>^0$</p></td>
<td><p>+14255550100</p></td>
<td><p>0 viene convertito in +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>Converte i numeri con il prefisso on-net (6) e il codice del sito Redmond (222)</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>62220100 viene convertito in +14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Converte i numeri con il prefisso on-net (6) e il codice del sito NY (333)</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+ 1202555 $1</p></td>
<td><p>63330100 viene convertito in + 12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Converte i numeri con il prefisso on-net (6) e il codice del sito di Dallas (444)</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+ 1972555 $1</p></td>
<td><p>64440100 viene convertito in + 19725550100</p></td>
</tr>
</tbody>
</table>


La tabella seguente illustra un piano di chiamata di esempio per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione indicate nella tabella precedente.

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>Tabella 2. Dial plan Redmond basato sulle regole di normalizzazione visualizzate nella tabella 1

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond. FQDNforesta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtension</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingRedmond</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
</tr>
<tr class="even">
<td><p>IntlCallingUS</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> I nomi delle regole di normalizzazione mostrati nella tabella precedente non includono spazi, ma questa è solo una scelta. Il primo nome nella tabella, ad esempio, avrebbe potuto essere "5 digit extension" o "5-digit Extension" e sarebbe stato comunque valido.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

