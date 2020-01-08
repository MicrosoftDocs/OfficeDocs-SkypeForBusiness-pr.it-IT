---
title: 'Lync Server 2013: cercare utenti di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068fe07bf14894d22f929291514854360d6d0465
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Cercare gli utenti di Lync Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-14_

È possibile usare i risultati di una query di ricerca per configurare gli utenti per Lync Server 2013. È possibile cercare gli utenti per nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (SAM), indirizzo SIP o URI (Uniform Resource Identifier) linea.

È possibile cercare gli utenti usando il pannello di controllo di Lync Server o lo snap-in utenti e computer di Active Directory. La procedura seguente descrive come usare il pannello di controllo di Lync Server per cercare gli utenti.

<div>


> [!NOTE]  
> In un ambiente con una topologia di foresta centrale i risultati della ricerca potrebbero non essere precisi quando si cerca un utente tramite l'indirizzo di posta elettronica dell'utente. È invece possibile cercare gli utenti specificando un prefisso di indirizzo SIP, ad esempio SIP: Name, aggiungere un filtro di ricerca e selezionare un indirizzo SIP che contiene un indirizzo di posta elettronica parziale oppure usare il cmdlet <STRONG>Get-CSUser</STRONG> .



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>Per cercare uno o più utenti

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome dell'account SAM, indirizzo SIP o URI di linea dell'account utente che si desidera cercare e quindi fare clic su **trova**.

5.  Opzionale Specificare altri criteri di ricerca per restringere i risultati:
    
    1.  Fare clic sul pulsante Espandi freccia nell'angolo in alto a destra dello schermo sopra i **Risultati della ricerca**e quindi fare clic su **Aggiungi filtro**.
    
    2.  Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare una proprietà utente.
    
    3.  Nell'elenco **uguale a** fare clic su **uguale** a o **non uguale a**.
    
    4.  Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **trova**.

6.  I risultati della ricerca vengono visualizzati nei **Risultati della ricerca**. È possibile selezionare uno o tutti gli utenti nell'elenco ed eseguire attività di configurazione per gli utenti selezionati.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Visualizzazione di informazioni sugli account utente abilitati per Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Abilitazione e disabilitazione degli utenti per Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

