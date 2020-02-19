---
title: 'Lync Server 2013: account utente abilitati per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3545ba99f55e0fa11bcee09791d1a618b92c3d78
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>Account utente abilitati per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-04-18_

Negli argomenti di questa sezione vengono fornite procedure dettagliate per la configurazione delle impostazioni utente che è possibile eseguire utilizzando il pannello di controllo di Lync Server 2013.

<div>


> [!IMPORTANT]  
> Non è possibile utilizzare il pannello di controllo di Lync Server per gestire gli utenti membri del gruppo Domain Admins di Active Directory. Per gli utenti di Domain Admins, è possibile utilizzare solo il pannello di controllo di Lync Server per eseguire le operazioni di ricerca di sola lettura. Per eseguire operazioni di scrittura sugli utenti degli amministratori di dominio (ad esempio, abilitare o disabilitare il pannello di controllo di Lync Server, modificare le assegnazioni del pool o dei criteri, le impostazioni di telefonia, l'indirizzo SIP), è necessario utilizzare i cmdlet di Windows PowerShell durante l'accesso come utente Domain Admins. Per informazioni dettagliate sull'utilizzo dei cmdlet di Windows PowerShell per la gestione degli utenti, vedere <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.



</div>

Quando si esegue qualsiasi attività amministrativa di Lync Server 2013 che implica la ricerca di un utente o il filtro dei risultati di ricerca degli utenti, esistono proprietà utente che esistono come attributi in servizi di dominio Active Directory, ma non vengono replicate nel catalogo globale. fino alla distribuzione di Microsoft Exchange Server. Microsoft Exchange, non Lync Server, contrassegna gli attributi seguenti per la replica nel catalogo globale al momento dell'installazione:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Informazioni utente</th>
<th>Indirizzo e telefono</th>
<th>Organizzazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Iniziali</p></td>
<td><p>Indirizzo</p>
<p>Paese</p>
<p>Del cercapersone</p>
<p>Fax</p>
<p>Cellulare</p></td>
<td><p>Titolo</p>
<p>Company</p>
<p>Reparto</p>
<p>Ufficio</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Visualizzazione delle informazioni sugli account utente abilitati per Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Abilitazione e disabilitazione degli utenti per Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Gestione di VoIP aziendale per gli utenti in Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Modifica delle proprietà degli account utente in Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)

  - [Gestire i criteri di accesso esterno in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Cmdlet per la gestione degli utenti in Lync Server 2013](lync-server-2013-user-management-cmdlets.md)  


[Gestione degli utenti in Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

