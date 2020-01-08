---
title: 'Lync Server 2013: creare o modificare un intervallo orbit di Call Park'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04f759c0bb5c33991c961dbe4a2790c50df1f098
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>Creare o modificare un intervallo orbit di Call Park in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Usare una delle procedure seguenti per creare o modificare un intervallo di orbit del parcheggio di chiamata.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Per usare il pannello di controllo di Lync Server per creare o modificare un intervallo di numeri per le chiamate di parcheggio

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali** e quindi su **Call Park**.

4.  Nella pagina **Call Park** eseguire una delle operazioni seguenti:
    
      - Per creare un nuovo intervallo di Orbit, fare clic su **nuovo**. In **nome**Digitare un nome identificativo per l'intervallo di numeri.
        
        <div>
        

        > [!NOTE]  
        > Dopo aver eseguito il commit dell'intervallo di Orbit nel database, non è possibile modificare questo nome.

        
        </div>
    
      - Per modificare un intervallo di orbit esistente, digitare tutto o parte del nome dell'intervallo di Orbit nel campo di ricerca. Nell'elenco risultante di orbite fare clic sull'orbita desiderata, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Nel campo primo **intervallo di numeri** Digitare il numero di inizio dell'intervallo di estensioni per l'orbita del parcheggio di chiamata, quindi digitare il numero finale dell'intervallo nel secondo campo dell' **intervallo di numeri** .
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</P>
    > <LI>
    > <P>Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.</P>
    > <LI>
    > <P>L'intervallo di orbit deve essere univoco. Questo intervallo non può sovrapporsi ad altri intervalli.</P>
    > <LI>
    > <P>Se l'intervallo di Orbit inizia con il carattere * o #, l'intervallo deve essere maggiore di 100.</P>
    > <LI>
    > <P>Valori validi: deve corrispondere alla stringa di espressione regolare (\*[| #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Questo significa che il valore deve essere una stringa che inizia con il carattere * o # o un numero da 1 a 9 (il primo carattere non può essere uno zero). Se il primo carattere è * o #, il carattere seguente deve essere un numero da 1 a 9 (non può essere uno zero). I caratteri successivi possono essere qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000", "*92000", "* 95551212" e "915551212"). Se il primo carattere non è * o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".</P>
    > <LI>
    > <P>Non dovresti avere più di un totale di 50.000 orbite per ogni pool. Ogni intervallo orbit include in genere 100 o meno orbite, ma può essere molto più grande purché includa meno di 10.000 orbite. Anziché specificare un numero iniziale "7000000" e un numero finale "8000000", ad esempio, valutare la possibilità di specificare un numero iniziale "7000000" e un numero finale "7000100".</P></LI></UL>

    
    </div>

6.  In **FQDN del server di destinazione**, fare clic sul nome di dominio completo (FQDN) o sull'ID servizio del servizio applicazione che ospita l'applicazione Parcheggio di chiamata. Tutte le chiamate parcheggiate in numeri compresi nell'intervallo specificato dal numero di inizio e dal numero finale nell'intervallo di Orbit verranno indirizzate a questo server o pool.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Per usare Windows PowerShell per creare o modificare un intervallo di numeri per le chiamate di parcheggio

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  USA **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri orbitali. Usare **set-CsCallParkOrbit** per modificare un intervallo esistente di numeri di orbita.
    
    Nella riga di comando eseguire:
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    Ad esempio:
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    L'esempio seguente mostra come modificare i numeri in un intervallo di orbit esistente,
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

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

