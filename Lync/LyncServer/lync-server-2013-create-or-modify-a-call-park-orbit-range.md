---
title: 'Lync Server 2013: creare o modificare un intervallo di codici orbit del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddf119e62d7e7c8ecd71fc8c121a4a623440d6f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Per creare o modificare un intervallo orbit del parcheggio di chiamata, usare una delle procedure seguenti.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Per utilizzare il pannello di controllo di Lync Server per creare o modificare un intervallo di numeri per il parcheggio delle chiamate

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Funzionalità vocali** e quindi su **Parcheggio di chiamata**.

4.  Nella pagina **Parcheggio di chiamata** effettuare una delle operazioni seguenti:
    
      - Per creare un nuovo intervallo orbit, fare clic su **Nuovo**. In **Nome** digitare un nome per identificare l'intervallo di numeri.
        
        <div>
        

        > [!NOTE]  
        > Dopo l'esecuzione del commit dell'intervallo orbit nel database non sarà possibile modificare il nome.

        
        </div>
    
      - Per modificare un intervallo orbit esistente, digitarne il nome, per intero o in parte, nel campo di ricerca. Nell'elenco dei codici orbit risultante fare clic sul codice desiderato, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  Nel primo campo **Intervallo numeri** digitare il numero iniziale dell'intervallo di estensioni per i codici orbit di parcheggio di chiamata e nel secondo campo **Intervallo numeri** digitare il numero finale dell'intervallo.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale.</P>
    > <LI>
    > <P>Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.</P>
    > <LI>
    > <P>L'intervallo di codici orbit deve essere univoco. Tale intervallo non può sovrapporsi ad altri intervalli.</P>
    > <LI>
    > <P>Se l'intervallo di codici orbit inizia con il carattere * oppure #, l'intervallo deve essere superiore a 100.</P>
    > <LI>
    > <P>Valori validi: deve corrispondere alla stringa di espressione regolare (\*[| #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). In pratica, il valore deve essere una stringa che inizia con il carattere * o # oppure con un numero da 1 a 9 (il primo carattere non può essere uno zero). Se il primo carattere è * o #, il carattere successivo deve essere un numero da 1 a 9 (non può essere uno zero). I caratteri successivi possono essere qualsiasi numero compreso tra 0 e 9 fino a sette caratteri aggiuntivi, ad esempio "#6000", "*92000", "* 95551212" e "915551212". Se il primo carattere non è * o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".</P>
    > <LI>
    > <P>In totale non vi possono essere più di 50.000 codici orbit per ogni pool. Ogni intervallo di codici orbit in genere comprende al massimo 100 codici orbit, ma può essere anche molto più esteso, purché non superi i 10.000 codici orbit. Ad esempio, anziché specificare "7000000" come numero iniziale e "8000000" come numero finale, considerare la possibilità di specificare "7000000" e "7000100" rispettivamente come numero iniziale e numero finale.</P></LI></UL>

    
    </div>

6.  In **FQDN del server di destinazione** fare clic sul nome di dominio completo (FQDN) o sull'ID del servizio dell'applicazione che ospita l'applicazione Parcheggio di chiamata. Tutte le chiamate parcheggiate nei numeri dell'intervallo specificato dal numero iniziale e dal numero finale dell'intervallo di codici orbit saranno instradate a tale server o pool.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Per utilizzare Windows PowerShell per creare o modificare un intervallo di numeri per il parcheggio delle chiamate

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Usare **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri orbit. Usare **Set-CsCallParkOrbit** per modificare un intervallo di numeri orbit esistente.
    
    Nella riga di comando digitare il comando seguente:
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    Ad esempio:
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    L'esempio seguente mostra come modificare i numeri di un intervallo orbit esistente.
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

