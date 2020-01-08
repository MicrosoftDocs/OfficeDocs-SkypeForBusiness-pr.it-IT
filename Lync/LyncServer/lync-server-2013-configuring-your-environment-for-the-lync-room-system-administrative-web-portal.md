---
title: "Lync Server 2013: Configurazione dell'ambiente per il portale Web di amministrazione di Lync Room System"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ef7596e65c44f871da8c26a0526a389dde72a45
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Configurazione dell'ambiente di Lync Server 2013 per il portale Web di amministrazione di Lync Room System

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-22_

Per usare il portale Web amministrativo di Lync room System (LRS), sarà necessario installare o configurare i prerequisiti seguenti.

<div>


> [!IMPORTANT]  
> Se il server è configurato con l'autenticazione Kerberos e NTLM e LRS è in esecuzione in un computer non collegato al dominio, l'autenticazione Kerberos non riesce e l'utente non vedrà lo stato di LRS nel portale amministrativo. Per risolvere il problema, configurare il server con l'autenticazione NTLM o sia con autenticazione NTLM che TLS-DSK (senza Kerberos) oppure aggiungere il computer LRS al dominio.



</div>

1.  Installare gli aggiornamenti cumulativi di Lync Server 2013:2013 luglio nella topologia di Lync Server.
    
    Per ottenere l'aggiornamento o vedere cosa è incluso, vedere [aggiornamenti per Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Creare un utente di Active Directory abilitato per SIP.
    
    Il portale Web amministrativo di LRS usa queste credenziali per eseguire query su informazioni da Lync Server. Il nome utente consigliato è LRSApp.

3.  Creare un gruppo di sicurezza di Active Directory con il nome LRSSupportAdminGroup.
    
    Creare il gruppo con ambito gruppo come globale e tipo di gruppo come sicurezza. Gli utenti abilitati per SIP aggiunti a questo gruppo saranno autorizzati a visualizzare l'elenco delle sale ed eseguire determinati comandi, ad esempio la raccolta di registri.

4.  Creare un gruppo di sicurezza di Active Directory con il nome LRSFullAccessAdminGroup.
    
    Creare il gruppo con ambito gruppo come globale e tipo di gruppo come sicurezza. gli utenti abilitati per SIP aggiunti a questo gruppo sono autorizzati a usare tutte le funzionalità del portale di amministrazione.
    
     
    
    ![Elenco di gruppi di amministratori con il ruolo gruppo](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "di sicurezza di gruppi di amministratori con il ruolo gruppo di sicurezza")  
    
     

5.  Aggiungi LRSFullAccessAdminGroup come membro di LRSSupportAdminGroup.
    
    Pagina membri ![Proprietà LRSSupportAdminGroup]pagina membri proprietà(images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup")  
    
     

6.  Creare un utente abilitato per SIP Active Directory con il nome LRSSupport. Aggiungere l'utente a LRSSupportAdminGroup.
    
    Pagina membri ![Proprietà LRSSupportAdminGroup]pagina membri proprietà(images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup")  
    
     

7.  Installare ASP.NET MVC 4 per Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1, disponibile nell'area download Microsoft [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).

</div>

<span> </span>

</div>

</div>

</div>

