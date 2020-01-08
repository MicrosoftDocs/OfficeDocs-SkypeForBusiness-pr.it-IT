---
title: 'Lync Server 2013: Criteri vocali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca1e72a1b62a224898d98aec7fcef9bc62ddf8bc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a>Criteri vocali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

I *criteri vocali* di Lync Server definiscono gli elementi seguenti per ogni utente, sito o organizzazione a cui è assegnato il criterio:

  - Un set di funzionalità di chiamata che possono essere abilitate o disabilitate per determinare la funzionalità VoIP aziendale disponibile per gli utenti.

  - Un set di record di utilizzo PSTN (Public Switched Telephone Network) che definiscono i tipi di chiamate autorizzate.

<div>

## <a name="planning-for-voice-policies"></a>Pianificazione per i criteri vocali

La procedura seguente consente di pianificare i criteri vocali necessari per la distribuzione di VoIP aziendale:

  - Determinare come configurare il criterio vocale globale (i criteri vocali predefiniti installati con il prodotto). Questo criterio si applica a tutti gli utenti di VoIP aziendale a cui non è assegnato esplicitamente un criterio a livello di sito o per utente.

  - Identificare i criteri vocali a livello di sito che potrebbero essere necessari.

  - Identificare qualsiasi criterio vocale per utente che potrebbe essere necessario.

  - Decidere quali funzionalità di chiamata abilitare per ogni criterio vocale.

  - Determinare i record di utilizzo PSTN da configurare per ogni criterio vocale.

<div>

## <a name="voice-policy-scope"></a>Ambito dei criteri vocali

L' *ambito dei criteri vocali* determina il livello gerarchico in cui è possibile applicare i criteri. In Lync Server è possibile configurare i criteri vocali con i livelli di ambito seguenti (elencati tra i più specifici per i più generali).

  - I **criteri vocali dell'utente** possono essere assegnati a singoli utenti, gruppi o oggetti contatto. Questo è il criterio di livello più basso. I criteri vocali dell'utente possono essere distribuiti per abilitare le funzionalità per determinati utenti o gruppi in un sito, ma non per altri nello stesso sito. Ad esempio, potresti voler disabilitare la chiamata a lunga distanza per alcuni dipendenti. Allo scopo di assegnare un criterio vocale, un oggetto contatto viene considerato come un singolo utente.
    
    <div>
    

    > [!NOTE]  
    > È consigliabile distribuire un criterio vocale utente per gli utenti di VoIP aziendale del sito succursale registrati con la distribuzione del sito centrale o gli utenti registrati in un Survivable Branch Appliance.

    
    </div>

  - I **criteri vocali del sito** si applicano a un intero sito, eccetto per gli utenti, i gruppi o gli oggetti contatto assegnati a un criterio vocale per l'utente. Per definire un criterio vocale del sito, è necessario specificare il sito a cui si applicano i criteri. Se non viene assegnato un criterio vocale per l'utente, viene usato il criterio vocale del sito.

  - Il criterio vocale **globale** è il criterio vocale predefinito che viene installato con il prodotto. È possibile modificare il criterio vocale globale per soddisfare le esigenze specifiche dell'organizzazione, ma non è possibile rinominarla o eliminarla. Questo criterio vocale si applica a tutti gli utenti di VoIP aziendale, ai gruppi e agli oggetti contatto nella distribuzione, a meno che non si configuri e assegni un criterio vocale con un ambito più specifico. Se si vuole disabilitare completamente questo criterio, assicurarsi che tutti i siti e gli utenti dispongano di criteri personalizzati assegnati.

</div>

<div>

## <a name="call-features"></a>Caratteristiche delle chiamate

È possibile abilitare o disabilitare le funzionalità di chiamata seguenti per ogni criterio vocale:

  - L' **inoltro di chiamata** consente agli utenti di inoltrare le chiamate ad altri telefoni e dispositivi client. Abilitato per impostazione predefinita.

  - La **delega** consente agli utenti di specificare ad altri utenti di inviare e ricevere chiamate per proprio conto. Abilitato per impostazione predefinita.

  - Il **trasferimento** delle chiamate consente agli utenti di trasferire le chiamate ad altri utenti. Abilitato per impostazione predefinita.

  - **Call Park** consente agli utenti di parcheggiare le chiamate e quindi prendere la chiamata da un altro telefono o client. Disabilitata per impostazione predefinita.

  - La **chiamata simultanea** consente alle chiamate in arrivo di squillare su un altro telefono, ad esempio un cellulare o altri dispositivi endpoint. Abilitato per impostazione predefinita.

  - La **chiamata del team** consente agli utenti di un team definito di rispondere alle chiamate per gli altri membri del team. Abilitato per impostazione predefinita.

  - La **reinstradazione PSTN** consente alle chiamate effettuate dagli utenti a cui è assegnato questo criterio ad altri utenti aziendali di essere reinstradati nella rete PSTN (Public Switched Telephone Network) se la WAN è congestionata o non disponibile. Abilitato per impostazione predefinita.

  - **L'override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni sui criteri di controllo ammissione chiamata per un determinato utente. Disabilitata per impostazione predefinita.

  - La **traccia di chiamata** non consentita consente agli utenti di segnalare chiamate illecite tramite il client Lync e quindi contrassegna tali chiamate nei record dettagli chiamata. Disabilitata per impostazione predefinita.

  - La funzione di **escape della segreteria telefonica** impedisce che le chiamate vengano immediatamente indirizzate al sistema di segreteria telefonica dell'utente quando è configurato lo squillo simultaneo e che il telefono sia disattivato, fuori batteria o fuori portata e sia basato su un valore timer. Questa impostazione Abilita e Disabilita il timer e imposta il valore del timer. Può essere configurato solo tramite Lync Server Management Shell. Disabilitata per impostazione predefinita.

  - L' **inoltro di chiamata e l'uso simultaneo di chiamate PSTN** consentono agli amministratori di specificare lo stesso utilizzo PSTN dei criteri vocali per l'inoltro di chiamata e la suoneria simultanea, limitano l'inoltro di chiamata e lo squillo simultaneo agli utenti interni di Lync o specificano un uso PSTN personalizzato diverso dall'uso PSTN del criterio vocale. L'impostazione predefinita consiste nell'usare lo stesso utilizzo PSTN del criterio vocale per l'inoltro di chiamata e lo squillo simultaneo.

</div>

<div>

## <a name="pstn-usage-records"></a>Record utilizzo PSTN

Ogni criterio vocale deve avere uno o più record di utilizzo PSTN associati. Gli usi PSTN possono essere associati a un criterio vocale allo scopo di effettuare chiamate simultanee e inoltro di chiamata. Per informazioni dettagliate sulla pianificazione dei record di utilizzo PSTN, vedere [record sull'utilizzo PSTN in Lync Server 2013](lync-server-2013-pstn-usage-records.md).

<div>


> [!NOTE]  
> L'ordine di utilizzo PSTN è fondamentale perché in corrispondenza degli utenti alle route la funzionalità di routing in uscita confronta gli usi PSTN dall'alto verso il basso. Se il primo utilizzo corrisponde alla route di chiamata, viene usata tale route. In caso contrario, la funzionalità di routing in uscita analizza il successivo utilizzo PSTN nell'elenco e continua fino a quando non viene trovata una corrispondenza. In effetti, i successivi usi PSTN includono il backup se il primo nell'elenco non è disponibile.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

