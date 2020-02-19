---
title: Appartenenze a gruppi e requisiti per i diritti utente per Best Practices Analyzer
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2245cbbe32e8751948f32dc83dae7ca58f92091f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Appartenenze a gruppi e requisiti per i diritti utente per Best Practices Analyzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-21_

Per eseguire correttamente Best Practices Analyzer, è necessario che l'account utente utilizzato per accedere sia un membro del gruppo Administrators nel computer locale. Inoltre, per analizzare l'ambiente, è necessario che l'utente sia un membro dei gruppi seguenti:

  - **Domain Admins**   per enumerare le informazioni sui servizi di dominio Active Directory e per chiamare i provider di Strumentazione gestione Windows (WMI) sui controller di dominio e i server di catalogo globale.

  - **Amministratori**   necessari per ogni computer interno di Lync Server 2013 e per ogni server perimetrale per chiamare i provider di Strumentazione gestione Windows (WMI) e per accedere al registro di sistema.

  - **RTCUniversalReadOnlyAdmins**   di sola lettura completa o delegata per i diritti amministrativi di Lync Server 2013.

  - ****   Amministratore solo visualizzazione di Exchange solo amministratore di Exchange solo visualizzazione con delega nell'organizzazione di Microsoft Exchange.

Se l'account utente non dispone di diritti utente sufficienti, sono disponibili due opzioni:

  - Nel prompt dei comandi utilizzare il comando **runas** per eseguire lo strumento in un account che non dispone diritti utenti sufficienti. Di seguito viene illustrata la sintassi del comando:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Nella pagina **Connessione a Active Directory** impostare le credenziali per gli account che si prevede di utilizzare per eseguire lo strumento Best Practices Analyzer. Fare clic su **Mostra opzioni di accesso avanzate**. È possibile immettere tre account: uno per la connessione a servizi di dominio Active Directory, uno per la connessione ai server perimetrali di Lync Server 2013 e uno per la connessione ai server di Exchange. Se non si specifica nessuno dei tre account, verrà utilizzato l'account utente utilizzato per accedere ed eseguire lo strumento Best Practices Analyzer.

</div>

<span> </span>

</div>

</div>

</div>

