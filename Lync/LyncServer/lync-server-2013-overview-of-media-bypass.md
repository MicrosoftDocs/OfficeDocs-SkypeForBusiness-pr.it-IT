---
title: 'Lync Server 2013: Panoramica del bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84c70cae521deebecf30e7c8ec6505b18e9842fa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Panoramica del bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Il bypass multimediale è utile quando si vuole ridurre al minimo il numero di server di mediazione distribuiti. In genere, un pool di Mediation Server verrà distribuito in un sito centrale e controllerà i gateway nei siti di succursale. L'abilitazione del bypass multimediale consente alle chiamate PSTN (Public Switched Telephone Network) dei client in siti di succursale di scorrere direttamente attraverso i gateway in questi siti. Le route delle chiamate in uscita di Lync Server 2013 e i criteri VoIP aziendale devono essere configurati correttamente in modo che le chiamate PSTN da client in un sito di succursale vengano indirizzate al gateway appropriato.

Le reti Wi-Fi in genere avvertono più perdita di pacchetti rispetto alle reti cablate. Il ripristino da questa perdita di pacchetti non è in genere un elemento che può essere ospitato da gateway. Per questo motivo, ti consigliamo di valutare la qualità di una rete Wi-Fi prima di determinare se l'esclusione deve essere abilitata per una subnet wireless. C'è un compromesso nella riduzione della latenza rispetto al recupero dalla perdita di pacchetti da considerare anche. RTAudio, un codec disponibile per le chiamate che non ignorano il Mediation Server, è più adatto per la gestione della perdita di pacchetti.

Una volta posizionata la struttura VoIP aziendale, la pianificazione per il bypass multimediale è semplice.

  - Se si ha una topologia centralizzata senza collegamenti WAN a siti di succursale, è possibile abilitare il bypass multimediale globale, perché il controllo ottimizzato non è necessario.

  - Se si dispone di una topologia distribuita costituita da una o più aree di rete e dai siti di filiale affiliati, determinare le operazioni seguenti:
    
      - Se i peer di Mediation Server sono in grado di supportare le funzionalità necessarie per il bypass multimediale.
    
      - I siti di ogni area di rete sono ben connessi.
    
      - Quale combinazione di bypass multimediale e controllo di ammissione di chiamata è appropriata per la rete.

Quando si Abilita il bypass multimediale, viene generato automaticamente un ID di bypass univoco per un'area di rete e per tutti i siti di rete senza vincoli di larghezza di banda all'interno dell'area geografica. I siti con vincoli di larghezza di banda nell'area geografica e i siti connessi all'area geografica con collegamenti WAN con vincoli di larghezza di banda sono assegnati ad ognuno un ID di bypass univoco.

Quando un utente effettua una chiamata alla rete PSTN, il Mediation Server confronta l'ID di bypass della subnet client con l'ID di bypass della subnet del gateway. Se i due ID di bypass corrispondono, per la chiamata viene usato il bypass multimediale. Se gli ID di bypass non corrispondono, il supporto per la chiamata deve fluire attraverso il Mediation Server.

Quando un utente riceve una chiamata dalla rete PSTN, il client dell'utente confronta il proprio ID di esclusione con quello del gateway PSTN. Se i due ID di bypass corrispondono, il flusso multimediale passa direttamente dal gateway al client, bypassando il Mediation Server.

Solo i client e i dispositivi Lync 2010 o superiore supportano le interazioni media bypass con un Mediation Server.

<div>


> [!IMPORTANT]  
> Oltre a consentire il bypass multimediale a livello globale, è necessario abilitare individualmente il bypass multimediale in ogni trunk PSTN. Se il bypass è abilitato globalmente, ma non è abilitato per un trunk PSTN specifico, il bypass multimediale non verrà richiamato per le chiamate che coinvolgono il trunk PSTN. Inoltre, quando il bypass multimediale è impostato per l' <STRONG>uso di informazioni sul sito e sull'area geografica</STRONG>, è necessario associare tutte le subnet instradabili ai siti in cui si trovano. Se sono presenti subnet instradabili all'interno di un sito per cui il bypass non è desiderato, queste subnet devono essere raggruppate all'interno di un nuovo sito prima di abilitare il bypass multimediale. In questo modo si assicurerà che alle subnet non instradabili sia assegnato un ID di bypass diverso.



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modalità di bypass multimediale in Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Requisiti tecnici per il bypass multimediale in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

