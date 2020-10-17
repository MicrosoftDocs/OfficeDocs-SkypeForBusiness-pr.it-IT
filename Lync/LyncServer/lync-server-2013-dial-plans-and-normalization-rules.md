---
title: 'Lync Server 2013: dial plan e regole di normalizzazione'
description: 'Lync Server 2013: dial plan e regole di normalizzazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0341d0c5267a2272ff45bd93408b2bd14f0ceeaa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559742"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Dial plan e regole di normalizzazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Per dial plan si intende un set denominato di regole di normalizzazione che consente di convertire i numeri di telefono relativi a una località, a un utente o a un oggetto contatto specifico in un unico formato standard (E.164) ai fini dell'autorizzazione del telefono e del routing della chiamata.

Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi nei vari formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato. La stessa stringa di composizione può essere interpretata e convertita in modo diverso, a seconda della posizione da cui viene composto e della persona o dell'oggetto contatto che effettua la chiamata.

<div>

## <a name="dial-plan-scope"></a>Ambito del dial plan

L'*ambito* di un dial plan determina il livello gerarchico a cui è possibile applicare il dial plan. In Lync Server, a un utente può essere assegnato un dial plan specifico per utente. Se non viene assegnato un dial plan utente, viene applicato il dial plan del pool di registrazione. Se non è presente alcun dial plan del pool di registrazione, viene applicato il dial plan del sito. Infine, se non è presente alcun altro dial plan applicabile all'utente, viene applicato il dial plan globale.

I client ottengono i livelli di ambito del dial plan tramite le impostazioni di provisioning in-band fornite quando gli utenti accedono a Lync Server. In qualità di amministratore, è possibile gestire e assegnare i livelli di ambito del piano di chiamata utilizzando il pannello di controllo di Lync Server.

<div>


> [!NOTE]  
> Il dial plan del gateway PSTN (Public Switched Telephone Network) a livello di servizio viene applicato alle chiamate in arrivo da un determinato gateway.



</div>

I livelli di ambito del dial plan sono definiti come segue:

  - **Dial plan utente:** Può essere assegnato a singoli utenti, gruppi o oggetti contatto. Le applicazioni vocali possono cercare un dial plan per utente quando si riceve una chiamata con il contesto telefonico impostato su User-default. Ai fini dell'assegnazione di un dial plan, un oggetto contatto viene trattato come un singolo utente.

  - **Dial plan del pool:** Può essere creato a livello di servizio per qualsiasi gateway PSTN o registrar nella topologia. Per definire un dial plan pool, è necessario specificare un particolare servizio (gateway PSTN o pool di registrazione) a cui applicare il dial plan.

  - **Dial plan del sito:** Può essere creato per un intero sito, ad eccezione degli utenti, dei gruppi o degli oggetti contatto a cui è assegnato un dial plan di pool o un dial plan utente. Per definire un dial plan sito, è necessario specificare il sito a cui applicare il dial plan.

  - **Dial plan globale:** Il dial plan predefinito installato con il prodotto. È possibile modificare il dial plan globale, ma non eliminarlo. Questo dial plan si applica a tutti gli utenti, i gruppi e gli oggetti contatto di VoIP aziendale nella distribuzione, a meno che non si configuri e assegni un dial plan con un ambito più specifico.

</div>

<div>

## <a name="planning-for-dial-plans"></a>Pianificazione di dial plan

Per pianificare un dial plan, eseguire la procedura seguente:

  - Elencare tutte le impostazioni locali in cui l'organizzazione ha un ufficio.
    
    L'elenco deve essere aggiornato e completo. Dovrà essere rivisto con l'evolversi della società. In un'azienda di grandi dimensioni multinazionali con numerose filiali di piccole dimensioni, può essere un'attività che richiede molto tempo.

  - Identificare i modelli di numeri validi per ogni sito.
    
    La parte della pianificazione dei dial plan che richiede più tempo è l'identificazione dei formati di numeri validi per ogni sito. In alcuni casi, può essere possibile copiare negli altri dial plan le regole di normalizzazione scritte per un dial plan, in particolare se i siti corrispondenti si trovano nello stesso paese, nella stessa area geografica o anche nello stesso continente. In altri casi, possono essere sufficienti piccole modifiche dei numeri in un dial plan per utilizzarli in altri dial plan.

  - Sviluppare uno schema a livello di organizzazione per la denominazione dei dial plan.
    
    L'adozione di uno schema di denominazione standard assicura la coerenza all'interno dell'organizzazione e agevola la manutenzione e gli aggiornamenti.

  - Decidere se sono necessari più dial plan per una singola posizione.
    
    Se l'organizzazione gestisce un singolo dial plan su più posizioni, potrebbe essere comunque necessario creare un dial plan separato per gli utenti di VoIP aziendale che eseguono la migrazione da un sistema PBX (Private Branch Exchange) e che devono mantenere le proprie estensioni esistenti.

  - Decidere se i dial plan per utente sono obbligatori. Ad esempio, se si dispone di utenti in un sito di succursale registrato con il sito centrale o se si dispone di utenti registrati in un Survivable Branch Appliance, è possibile prendere in considerazione scenari di composizione speciali per tali utenti utilizzando i dial plan per utente e le regole di normalizzazione. Per informazioni dettagliate, vedere [requisiti di resilienza dei siti di succursale per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Determinare l'ambito del dial plan (come descritto in precedenza in questo argomento).

Per creare un dial plan, è necessario specificare i valori nei campi seguenti, in base alle esigenze, utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.

<div>

## <a name="name-and-simple-name"></a>Nome e nome semplice

Per i dial plan utente, è necessario specificare un nome descrittivo che identifichi gli utenti, i gruppi o gli oggetti contatto a cui verrà assegnato il piano di chiamata. Per i dial plan sito, il campo Nome è precompilato con il nome del sito e non può essere modificato. Per i dial plan del pool, il campo nome viene prepopolato con il gateway PSTN o con il nome di dominio completo (FQDN) del pool Front end e non può essere modificato.

Il *Nome semplice* del dial plan è precompilato con una stringa derivata dal nome del dial plan. Il campo nome semplice è modificabile, che consente di creare una convenzione di denominazione più descrittiva per i dial plan. Il valore *Nome semplice* non può essere vuoto e deve essere univoco. Una procedura consigliata consiste nello sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzare questa convenzione in modo coerente in tutti i siti e gli utenti.

</div>

<div>

## <a name="description"></a>Descrizione

Si consiglia di digitare il nome comune e riconoscibile della località geografica a cui si applica il dial plan corrispondente. Se ad esempio il nome del dial plan è Londra.Contoso.com, la descrizione consigliabile è Londra.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>Area conferenza telefonica con accesso esterno

Se si distribuisce la funzionalità di conferenza telefonica con accesso esterno, è necessario specificare un'area della conferenza telefonica con accesso esterno per associare i numeri di accesso relativi a un dial plan.

</div>

<div>

## <a name="external-access-prefix"></a>Prefisso accesso esterno

È possibile specificare un prefisso di accesso esterno composto da un massimo di quattro caratteri ( \# \* e 0-9) se gli utenti devono comporre una o più cifre iniziali aggiuntive (ad esempio, 9) per ottenere una linea esterna.

<div>


> [!NOTE]  
> Se si specifica un prefisso di accesso esterno, non è necessario creare una regola di normalizzazione aggiuntiva per regolare il prefisso.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>Regole di normalizzazione

Le regole di normalizzazione definiscono la modalità di routing di numeri di telefono espressi in formati diversi per la località specifica. La stessa stringa di numeri può essere interpretata e convertita in modo diverso, a seconda delle impostazioni locali da cui viene composto. Sono necessarie per il routing delle chiamate, perché gli utenti possono utilizzare vari formati quando immettono i numeri di telefono nei rispettivi elenchi contatti.

La normalizzazione dei numeri di telefono forniti dall'utente fornisce un formato coerente che facilita le attività seguenti:

  - Associare un numero composto al SIP-URI del destinatario previsto.

  - Applicare le regole di autorizzazione di composizione alla parte chiamante.

Di seguito sono riportati alcuni campi numerici che può essere necessario includere nelle regole di normalizzazione:

  - Dial plan

  - Codice paese

  - Indicativo di località

  - Lunghezza numero di interno

  - Prefisso sito

<div>

## <a name="creating-normalization-rules"></a>Creazione di regole di normalizzazione

Le regole di normalizzazione utilizzano le espressioni regolari di .NET Framework per specificare formati di corrispondenza numerica che il server utilizza per convertire le stringhe di composizione nel formato E.164 allo scopo di eseguire la ricerca inversa dei numeri. Per creare le regole di normalizzazione nel pannello di controllo di Lync Server, immettere manualmente le espressioni oppure immettendo le cifre iniziali e la lunghezza delle stringhe di composizione e consentendo al pannello di controllo di Lync Server di generare automaticamente l'espressione regolare corrispondente. In ogni caso, al termine è possibile immettere un numero di test per verificare che la regola di normalizzazione funzioni come previsto.

Per informazioni dettagliate sull'utilizzo di espressioni regolari di .NET Framework, vedere la sezione relativa alle espressioni regolari di .NET Framework all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>Regole di normalizzazione di esempio

Nella tabella seguente sono illustrati alcuni esempi di regole di normalizzazione scritte come espressioni regolari di .NET Framework. Si tratta di esempi puramente indicativi che non devono essere intesi come riferimenti obbligatori per la creazione di regole di normalizzazione.

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>Tabella 1. Regole di normalizzazione tramite espressioni regolari di .NET Framework

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
<th>Formato numero</th>
<th>Translation</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>Converte i numeri di interno a 4 cifre</p></td>
<td><p>^ (\d {4} ) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>0100 viene convertito in +14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Converte i numeri di interno a 5 cifre</p></td>
<td><p>^ 5 (\d {4} ) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>50100 viene convertito in +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Converte i numeri a 7 cifre in numeri locali di Redmond</p></td>
<td><p>^ (\d {7} ) $</p></td>
<td><p>+ 1425 $1</p></td>
<td><p>5550100 viene convertito in +14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Converte i numeri a 7 cifre in numeri locali di Dallas</p></td>
<td><p>^ (\d {7} ) $</p></td>
<td><p>+ 1972 $1</p></td>
<td><p>5550100 viene convertito in +19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Converte i numeri a 10 cifre in numeri degli Stati Uniti</p></td>
<td><p>^ (\d {10} ) $</p></td>
<td><p>+ 1 $1</p></td>
<td><p>2065550100 viene convertito in +12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Converte i numeri con prefissi interurbani in numeri degli Stati Uniti</p></td>
<td><p>^ 1 (\d {10} ) $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100 viene convertito in +2145550100</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>Converte i numeri con prefissi internazionali in numeri degli Stati Uniti</p></td>
<td><p>^ 011 (\d *) $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100 viene convertito in +91445550100</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>Converte il numero 0 nel numero dell'operatore di Redmond</p></td>
<td><p>^ $0</p></td>
<td><p>+ 14255550100</p></td>
<td><p>0 viene convertito in +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>Converte i numeri con prefisso on-net (6) e il codice sito di Redmond (222)</p></td>
<td><p>^ 6222 (\d {4} ) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>62220100 viene convertito in +14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Converte i numeri con prefisso on-net (6) e il codice sito di NY (333)</p></td>
<td><p>^ 6333 (\d {4} ) $</p></td>
<td><p>+ 1202555 $1</p></td>
<td><p>63330100 viene convertito in +12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Converte i numeri con prefisso on-net (6) e il codice sito di Dallas (444)</p></td>
<td><p>^ 6444 (\d {4} ) $</p></td>
<td><p>+ 1972555 $1</p></td>
<td><p>64440100 viene convertito in +19725550100</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente viene illustrato un esempio di dial plan per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione riportate nella tabella precedente.

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>Tabella 2. Dial plan di Redmond basato sulle regole di normalizzazione riportate nella tabella 1

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
> I nomi delle regole di normalizzazione illustrate nella tabella precedente non includono spazi, ma si tratta di una scelta. Il primo nome della tabella, ad esempio, potrebbe essere "5 digit extension" o "5-digit Extension" ed essere comunque valido.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

