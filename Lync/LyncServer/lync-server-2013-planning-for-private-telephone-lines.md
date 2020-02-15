---
title: 'Lync Server 2013: pianificazione per le linee telefoniche private'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0369ea671860b29c8cf7f7e1d9e0b894770c6d6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>Pianificazione per le linee telefoniche private con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-11_

Lync Server 2013 introduce la possibilità di fornire agli utenti una seconda linea telefonica privata, oltre alla linea telefonica principale. Le linee telefoniche private sono spesso assegnate ai dirigenti e ad altri utenti che desiderano un numero di telefono non in elenco a cui possono essere raggiunti direttamente.

Le linee telefoniche private possono essere configurate solo con Lync Server Management Shell. Non è possibile configurare le linee telefoniche private con il pannello di controllo di Lync Server. Le linee telefoniche private devono essere configurate solo nelle distribuzioni di Lync Server e non nelle distribuzioni miste.

<div>

## <a name="characteristics-of-private-telephone-lines"></a>Caratteristiche delle linee telefoniche private

Anche se il concetto di una seconda linea telefonica privata è fondamentalmente semplice, è importante comprendere le caratteristiche delle linee private e i modi in cui sono simili e diverse dalle linee telefoniche principali degli utenti.

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>Caratteristiche generali delle linee telefoniche private

  - Un utente può disporre di una sola linea telefonica privata.

  - Un utente con una linea telefonica privata ha solo una segreteria telefonica e riceve le notifiche di chiamata senza risposta a un singolo indirizzo di posta elettronica.

  - Un utente con una linea telefonica privata non ha un secondo indirizzo SIP e una seconda linea telefonica privata non fornisce a un utente una seconda presenza sulla rete (ad esempio, una seconda identità di messaggistica istantanea).

  - Le linee telefoniche private sono disponibili solo per le distribuzioni locali. Non sono disponibili con le distribuzioni ospitate di Lync Server.

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Il modo in cui le linee telefoniche private differiscono dalle linee telefoniche principali

  - I numeri di telefono per le linee telefoniche private non sono visualizzati negli elenchi telefonici o contatti derivati da servizi di dominio Active Directory.

  - Nessuna delle caratteristiche seguenti è disponibile con una linea telefonica privata: inoltro di chiamata, chiamata del team, delega, anello del team, prelievo di chiamate di gruppo e applicazione Response Group.

  - Le chiamate a una linea telefonica privata hanno un anello speciale e la notifica di sistema per la chiamata comunica all'utente che la chiamata in arrivo è sulla sua linea privata.

  - Le chiamate alla linea telefonica privata squillano sempre. Non seguono le regole "non disturbare".

  - Le linee telefoniche private sono solo in ingresso e non possono essere utilizzate per effettuare chiamate in uscita. Quando un utente con una linea telefonica privata effettua una chiamata, la chiamata proviene dalla linea telefonica principale dell'utente e non nasconde il nome dell'utente o il numero di telefono principale dell'utente dalla persona chiamata.

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Come le linee telefoniche private sono simili alle linee telefoniche principali

  - Le chiamate senza risposta a una linea telefonica privata vengono instradate alla stessa posta in arrivo della segreteria telefonica del telefono primario (se la segreteria telefonica è abilitata).

  - Il parcheggio di chiamata e il lavoro di prelievo delle chiamate con linee telefoniche private sono esattamente identici a quelli della linea telefonica principale dell'utente.

  - Quando la suoneria simultanea è abilitata sulla linea telefonica principale di un utente, è abilitata anche sulla linea telefonica privata.

  - Il numero di telefono di una linea telefonica privata viene registrato nel record dettagli chiamata allo stesso modo in cui si trova il numero di telefono della linea telefonica principale di un utente, ma con l'indicazione che si tratta di un numero di telefono privato.

  - Dopo che un utente ha risposto a una chiamata su una linea telefonica privata, la chiamata viene trattata come una chiamata sulla linea telefonica principale dell'utente. Ad esempio, se un utente che riceve una chiamata su una linea telefonica privata inoltra la chiamata o invita altre persone a una chiamata in conferenza, il nome dell'utente viene visualizzato in Lync 2013 e il numero di telefono della linea telefonica principale dell'utente viene visualizzato in ID chiamante.

  - Un utente può deviare una chiamata (reindirizzare la chiamata a un'altra destinazione, ad esempio un telefono cellulare o un telefono di casa, prima di rispondere) dalla linea telefonica privata nello stesso modo in cui viene utilizzata una linea telefonica principale.
    
    <div>
    

    > [!NOTE]  
    > Quando una chiamata a una linea privata viene instradata a un numero di telefono alternativo, il numero di telefono della linea telefonica privata viene messo a disposizione del numero di telefono alternativo e può essere visualizzato nei registri per tale numero.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Le chiamate provenienti da una conferenza alla linea telefonica privata non avranno un'indicazione di <EM>riga privata</EM> nella notifica del sistema in ingresso.

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>Amministrazione di linee telefoniche private

Oltre agli aspetti tecnici relativi alla creazione e alla gestione delle linee telefoniche private, è necessario stabilire le procedure amministrative. Ciò include la determinazione dei criteri per l'OMS nell'organizzazione è idoneo per una linea privata, la creazione e la gestione di elenchi di persone e le loro linee telefoniche, creando eventualmente una directory telefonica privata per i dirigenti, organizzando la formazione degli utenti e attività correlate.

<div>


> [!NOTE]  
> La linea telefonica privata viene memorizzata in Active Directory come attributo msRTCSIP-PrivateLine nell'oggetto User. Per impostazione predefinita, tutti i membri del gruppo Authenticated Users dispongono dell'accesso in lettura a questo attributo.



</div>

<div>

## <a name="assigning-telephone-numbers"></a>Assegnazione dei numeri di telefono

Gli account per i nuovi utenti che hanno bisogno di linee telefoniche private vengono creati allo stesso modo degli account senza linee telefoniche private, utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.

Utilizzare il cmdlet **Set-CsUser** in Lync Server Management Shell per assegnare un numero di telefono a una linea telefonica privata per un utente, ad esempio **Set-CsUser-Identity "SIP:Joe@contoso.com"-PrivateLine "Tel: + 14255551212"**.

I numeri di telefono per le linee telefoniche private possono avere una lunghezza compresa tra 3 e 15 numeri e devono essere preceduti dal prefisso "TEL:". Gli utenti possono disporre di qualsiasi codice di area e di qualsiasi codice di paese, purché l'organizzazione disponga di una composizione diretta verso l'interno per il codice area e per il codice paese.

Per informazioni dettagliate sui cmdlet e Lync Server Management Shell, vedere la documentazione di [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>Linee telefoniche private nelle distribuzioni miste

Le linee telefoniche private devono essere configurate solo per le distribuzioni di Lync Server. In una distribuzione in cui sono presenti server Lync Server e Office Communications Server 2007 o Office Communications Server 2007 R2, quando un utente nella versione precedente tenta di chiamare una linea telefonica privata, il routing della chiamata ha esito negativo perché il server non è in grado di eseguire una ricerca con numeri inversi su una linea telefonica privata.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

