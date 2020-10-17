---
title: "Lync Server 2013: configurazione dell'ambiente per il portale Web amministrativo di Lync room System"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea3269b9594df0597220648313ec79acfa329cf9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502103"
---
# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Configurazione dell'ambiente Lync Server 2013 per il portale Web amministrativo di Lync room System

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-22_

Per utilizzare il portale Web amministrativo di Lync room System (LRS), sarà necessario installare o configurare i prerequisiti seguenti.

<div>


> [!IMPORTANT]  
> Se il server è configurato con l'autenticazione Kerberos e NTLM e LRS è in esecuzione in un computer che non è stato aggiunto al dominio, l'autenticazione Kerberos avrà esito negativo e l'utente non visualizzerà lo stato di LRS nel portale amministrativo. Per risolvere il problema, configurare il server con l'autenticazione NTLM o sia l'autenticazione NTLM che TLS-DSK (senza Kerberos) oppure aggiungere il computer LRS al dominio.



</div>

1.  Installare gli aggiornamenti cumulativi di Lync Server 2013: luglio 2013 nella topologia di Lync Server.
    
    Per ottenere l'aggiornamento o vedere cosa è incluso in esso, vedere [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Creare un utente di Active Directory abilitato per SIP.
    
    Il portale Web amministrativo di LRS utilizza queste credenziali per eseguire query sulle informazioni di Lync Server. Il nome utente consigliato è LRSApp.

3.  Creare un gruppo di sicurezza di Active Directory con nome LRSSupportAdminGroup.
    
    Creare il gruppo con ambito gruppo come globale e come tipo di gruppo come protezione. Gli utenti abilitati per SIP che sono stati aggiunti a questo gruppo saranno autorizzati a visualizzare l'elenco delle sale ed eseguire alcuni comandi, ad esempio la raccolta di registri.

4.  Creare un gruppo di sicurezza di Active Directory con nome LRSFullAccessAdminGroup.
    
    Creare il gruppo con ambito gruppo come globale e come tipo di gruppo come protezione. gli utenti abilitati per SIP aggiunti a questo gruppo sono autorizzati a utilizzare tutte le funzionalità del portale di amministrazione.
    
     
    
    ![Elenco dei gruppi di amministratori con il ruolo di gruppo di sicurezza](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Elenco dei gruppi di amministratori con il ruolo di gruppo di sicurezza")  
    
     

5.  Aggiungere LRSFullAccessAdminGroup come membro di LRSSupportAdminGroup.
    
    ![Pagina membri proprietà LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Pagina membri proprietà LRSSupportAdminGroup")  
    
     

6.  Creare un utente di Active Directory SIP abilitato con nome LRSSupport. Aggiungere l'utente a LRSSupportAdminGroup.
    
    ![Pagina membri proprietà LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Pagina membri proprietà LRSSupportAdminGroup")  
    
     

7.  Installare ASP.NET MVC 4 per Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1, disponibile nell'area download Microsoft all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967) .

</div>

<span> </span>

</div>

</div>

</div>

