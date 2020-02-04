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
ms.openlocfilehash: 0df93d8a8de73a3119e7ca9a1a7abd76e9157a17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>Pianificazione per le linee telefoniche private con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-11_

Lync Server 2013 introduce la possibilità di fornire agli utenti una seconda linea telefonica privata oltre alla propria linea telefonica principale. Le linee telefoniche private sono spesso assegnate a dirigenti e ad altri che desiderano un numero di telefono non in elenco a cui possono essere raggiunti direttamente.

Le linee telefoniche private possono essere configurate solo con Lync Server Management Shell. Non è possibile configurare le linee telefoniche private con il pannello di controllo di Lync Server. Le linee telefoniche private devono essere configurate solo nelle distribuzioni di Lync Server e non in distribuzioni miste.

<div>

## <a name="characteristics-of-private-telephone-lines"></a>Caratteristiche delle linee telefoniche private

Anche se il concetto di una seconda linea telefonica privata è fondamentalmente semplice, è importante comprendere le caratteristiche delle linee private e i modi in cui sono simili e diversi dalle linee telefoniche primarie degli utenti.

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>Caratteristiche generali delle linee telefoniche private

  - Un utente può avere una sola linea telefonica privata.

  - Un utente con una linea telefonica privata ha una sola cassetta postale vocale e riceve le notifiche delle chiamate perse in un singolo indirizzo di posta elettronica.

  - Un utente con una linea telefonica privata non ha un secondo indirizzo SIP e una seconda linea telefonica privata non fornisce a un utente una seconda presenza nella rete, ad esempio una seconda identità di messaggistica istantanea.

  - Le linee telefoniche private sono disponibili solo per le distribuzioni locali. Non sono disponibili con distribuzioni ospitate di Lync Server.

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Come le linee telefoniche private differiscono dalle linee telefoniche primarie

  - I numeri di telefono per le linee telefoniche private non vengono visualizzati nelle directory telefoniche o negli elenchi di contatti derivati da servizi di dominio Active Directory.

  - Nessuna delle caratteristiche seguenti è disponibile con una linea telefonica privata: inoltro di chiamata, chiamata del team, delega, anello del team, prelievo delle chiamate di gruppo e applicazione Response Group.

  - Le chiamate a una linea telefonica privata hanno un anello speciale e la notifica di sistema per la chiamata indica all'utente che la chiamata in arrivo si trova nella propria linea privata.

  - Le chiamate alla linea telefonica privata squillano sempre. Non seguono le regole "non disturbare".

  - Le linee telefoniche private sono solo in ingresso e non possono essere usate per effettuare chiamate in uscita. Quando un utente con una linea telefonica privata effettua una chiamata, la chiamata proviene dalla linea telefonica principale dell'utente e non nasconde il nome dell'utente o il numero di telefono principale dell'utente dalla persona chiamata.

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Come le linee telefoniche private sono simili alle linee telefoniche primarie

  - Le chiamate senza risposta a una linea telefonica privata vengono instradate alla stessa posta in arrivo della segreteria telefonica, se è abilitata la casella vocale.

  - Chiamare il pick-up e chiamare il lavoro pickup con le linee telefoniche private nello stesso modo che fanno con la linea telefonica principale dell'utente.

  - Quando è abilitata la chiamata simultanea sulla linea telefonica primaria di un utente, è abilitata anche nella linea telefonica privata.

  - Il numero di telefono di una linea telefonica privata viene registrato nel record dettagli chiamata nello stesso modo in cui è indicato il numero di telefono della linea telefonica principale di un utente, ma con l'indicazione che si tratta di un numero di telefono privato.

  - Dopo che un utente risponde a una chiamata su una linea telefonica privata, la chiamata viene trattata come una chiamata nella linea telefonica principale dell'utente. Ad esempio, se un utente che riceve una chiamata su una linea telefonica privata inoltra la chiamata o invita altre persone a una chiamata in conferenza, il nome dell'utente viene visualizzato in Lync 2013 e il numero di telefono della linea telefonica principale dell'utente viene visualizzato nell'ID chiamante.

  - Un utente può deviare una chiamata (reindirizza la chiamata a un'altra destinazione, ad esempio un cellulare o il telefono di casa, prima di rispondere) dalla linea telefonica privata nello stesso modo con una linea telefonica principale.
    
    <div>
    

    > [!NOTE]  
    > Quando una chiamata a una riga privata viene instradata a un numero di telefono alternativo, il numero di telefono della linea telefonica privata viene reso disponibile al numero di telefono alternativo e può essere visualizzato nei registri per il numero.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Le chiamate da una conferenza alla linea telefonica privata non avranno un'indicazione a <EM>linee private</EM> nella notifica del sistema in arrivo.

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>Amministrazione di linee telefoniche private

Oltre agli aspetti tecnici della creazione e della gestione di linee telefoniche private, è necessario stabilire le procedure amministrative. Ciò include la determinazione dei criteri per chi è idoneo per una linea privata, la creazione e la manutenzione di elenchi di persone e le relative linee telefoniche, eventualmente la creazione di una directory telefonica privata per i dirigenti, l'organizzazione di formazione per gli utenti e attività correlate.

<div>


> [!NOTE]  
> La linea telefonica privata viene archiviata in Active Directory come attributo msRTCSIP-PrivateLine per l'oggetto utente. Per impostazione predefinita, un membro del gruppo Authenticated Users ha accesso in lettura a questo attributo.



</div>

<div>

## <a name="assigning-telephone-numbers"></a>Assegnazione di numeri di telefono

Gli account per i nuovi utenti che hanno bisogno di linee telefoniche private vengono creati allo stesso modo degli account senza linee telefoniche private, usando il pannello di controllo di Lync Server o Lync Server Management Shell.

Utilizzare il cmdlet **Set-CsUser** in Lync Server Management Shell per assegnare un numero di telefono a una linea telefonica privata per un utente, ad esempio **Set-CsUser-Identity "SIP:Joe@contoso.com"-PrivateLine "Tel: + 14255551212"**.

I numeri di telefono per le linee telefoniche private possono avere una lunghezza compresa tra 3 e 15 numeri e devono essere preceduti dal prefisso "TEL:". Possono avere qualsiasi prefisso locale e qualsiasi codice di paese o area geografica purché l'organizzazione disponga di una chiamata diretta verso l'interno per il codice area e il codice paese/area geografica.

Per informazioni dettagliate sui cmdlet e Lync Server Management Shell, vedere la documentazione di [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>Linee telefoniche private in distribuzioni miste

Le linee telefoniche private devono essere configurate solo per le distribuzioni di Lync Server. In una distribuzione in cui sono presenti sia Lync Server che Office Communications Server 2007 o Office Communications Server 2007 R2 Server, quando un utente della versione precedente tenta di chiamare una linea telefonica privata, il routing della chiamata non riesce perché il server non può eseguire una ricerca in numero inverso su una linea telefonica privata.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

