---
title: 'Lync Server 2013: cercare gli utenti di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 665d8bbb0f3409de62565c25dfdb494fd140d636
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Cercare gli utenti di Lync Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-14_

È possibile utilizzare i risultati di una query di ricerca per configurare gli utenti per Lync Server 2013. È possibile ricercare utenti in base al nome visualizzato, al nome, al cognome, al nome dell'account SAM (Security Accounts Manager), all'indirizzo SIP o all'URI (Uniform Resource Identifier) della linea.

È possibile cercare gli utenti utilizzando il pannello di controllo di Lync Server o lo snap-in utenti e computer di Active Directory. Nella procedura seguente viene descritto come utilizzare il pannello di controllo di Lync Server per cercare gli utenti.

<div>


> [!NOTE]  
> In un ambiente con una topologia a foresta centralizzata, i risultati della ricerca potrebbero non essere esatti quando si cerca un utente dall'indirizzo di posta elettronica dell'utente. In alternativa, è possibile cercare gli utenti specificando un prefisso di indirizzo SIP, ad esempio SIP: nome, aggiungere un filtro di ricerca e selezionare un indirizzo SIP contenente un indirizzo di posta elettronica parziale oppure utilizzare il cmdlet <STRONG>Get-CSUser</STRONG> .



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>Per ricercare uno o più utenti

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Utenti**.

4.  Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account SAM, l'indirizzo SIP o l'URI linea dell'account utente da ricercare e quindi fare clic su **Trova**.

5.  (Facoltativo) Specificare ulteriori criteri di ricerca per circoscrivere i risultati:
    
    1.  Fare clic sul pulsante freccia di espansione nell'angolo in alto a destra della schermata al di sopra di **Risultati della ricerca** e quindi fare clic su **Aggiungi filtro**.
    
    2.  Digitare la proprietà utente oppure selezionarla facendo clic sulla freccia nell'elenco a discesa.
    
    3.  Nell'elenco **Uguale a** selezionare **Uguale a** o **Diverso da**.
    
    4.  Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **Trova**.

6.  I risultati della ricerca verranno visualizzati al di sotto di **Risultati della ricerca**. È possibile selezionare uno o tutti gli utenti dell'elenco ed eseguire attività di configurazione sugli utenti selezionati.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Visualizzazione delle informazioni sugli account utente abilitati per Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Abilitazione e disabilitazione degli utenti per Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

