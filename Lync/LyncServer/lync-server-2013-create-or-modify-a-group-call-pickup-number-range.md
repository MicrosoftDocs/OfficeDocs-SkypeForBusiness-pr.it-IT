---
title: 'Lync Server 2013: creare o modificare un intervallo di numeri di raccolta delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a82f9cdc02052bf08dba3e9529871eff2b01211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Creare o modificare un intervallo di numeri di prelievo delle chiamate di gruppo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Usare la procedura seguente per creare o modificare un intervallo di numeri del gruppo di raccolta chiamate nella tabella Orbit di Call Park.

<div>


> [!NOTE]  
> È necessario usare Lync Server Management Shell per creare, modificare, rimuovere e visualizzare intervalli di numeri di prelievo delle chiamate di gruppo nella tabella Orbit di Call Park. Gli intervalli di numeri di raccolta delle chiamate di gruppo non sono disponibili nel pannello di controllo di Lync Server.



</div>

<div>


> [!IMPORTANT]  
> All'intervallo di numeri del gruppo pick-up delle chiamate deve essere assegnato un tipo di GroupPickup. Gli utenti sono abilitati per il ritiro delle chiamate di gruppo solo se il numero di gruppo assegnato è di tipo GroupPickup.



</div>

Gli intervalli di numeri del gruppo di raccolta chiamate devono essere conformi alle regole seguenti:

  - Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.

  - Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.

  - L'intervallo di numeri deve essere univoco e non può sovrapporsi ad altri intervalli.

  - Se l'intervallo di numeri inizia con il \* carattere \#o, l'intervallo deve essere maggiore di 100.

  - Valori validi: deve corrispondere alla stringa di espressione regolare\[\\\*|\#\](\[ ? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}). Questo significa che il valore deve essere una stringa che inizia con il \* carattere \# o un numero da 1 a 9 (il primo carattere non può essere uno zero). Se il primo carattere è \* o \#, il carattere seguente deve essere un numero da 1 a 9 (non può essere uno zero). I caratteri successivi possono essere qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi, ad esempio\#"6000",\*"92000",\*"95551212" e "915551212". Se il primo carattere non \* è o \#, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>Per creare o modificare l'intervallo di un gruppo di raccolta chiamate

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  USA **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri di gruppo di pick-up delle chiamate. Usare **set-CsCallParkOrbit** per modificare un intervallo esistente di numeri di prelievo delle chiamate.
    
    Nella riga di comando eseguire:
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Ad esempio:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    L'esempio seguente mostra come modificare un intervallo di numeri dalle orbite di Call Park per chiamare i gruppi di raccolta.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > Usa questo cmdlet per cambiare il tipo assegnato agli intervalli di numeri solo se hai inizialmente specificato il tipo non corretto e l'intervallo di gruppi non è ancora in uso. Se si cambia l'intervallo di numeri da CallPark a GroupPickup o viceversa e l'intervallo di numeri è già in uso, il pick-up di chiamata o di chiamata di gruppo smetterà di funzionare per l'intervallo di numeri. Se ad esempio si modifica un intervallo di numeri da CallPark a GroupPick, l'applicazione di parcheggio delle chiamate non può più usare l'intervallo di orbite per parcheggiare le chiamate.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminare un intervallo di Orbit di Call Park in Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

