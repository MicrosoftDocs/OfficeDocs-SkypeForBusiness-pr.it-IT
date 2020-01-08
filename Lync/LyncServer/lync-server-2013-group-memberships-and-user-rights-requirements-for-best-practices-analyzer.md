---
title: Requisiti per i membri e i diritti utente per l'analizzatore delle procedure consigliate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c60f6256cead59b16f443994143d40bdbc00393
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Requisiti per i diritti utente e le appartenenze ai gruppi per Best Practices Analyzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-21_

Per eseguire correttamente l'analizzatore delle procedure consigliate, l'account utente che si usa per accedere deve essere un membro del gruppo Administrators nel computer locale. Inoltre, per analizzare l'ambiente, l'account utente deve essere un membro dei gruppi seguenti:

  - **Domain Admins**   per enumerare le informazioni sui servizi di dominio Active Directory e per chiamare i provider di Strumentazione gestione Windows (WMI) nei controller di dominio e nei server di catalogo globale.

  - **Amministratori**   necessari per ogni computer interno di Lync Server 2013 e ogni Edge Server per chiamare i provider di Strumentazione gestione Windows (WMI) e per accedere al registro di sistema.

  - **RTCUniversalReadOnlyAdmins**   di sola lettura completa o delegata per i diritti amministrativi di Lync Server 2013.

  - **Exchange**   solo l'amministratore completo o delegato di Exchange solo visualizzazione amministratore nell'organizzazione di Microsoft Exchange.

Se l'account utente non dispone di diritti utente sufficienti, sono disponibili due opzioni:

  - Al prompt dei comandi usare il comando **RunAs** per eseguire lo strumento in un account che dispone di diritti utente sufficienti. La sintassi è la seguente:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Nella pagina **Connetti a Active Directory** impostare le credenziali per gli account che si prevede di usare per l'esecuzione di Best Practices Analyzer. Fare clic su **Mostra opzioni di accesso avanzato**. È possibile immettere tre account: uno per la connessione a servizi di dominio Active Directory, uno per la connessione a server Edge di Lync Server 2013 e uno per la connessione ai server di Exchange. Se non specifichi uno di questi account, viene usato l'account utente usato per accedere ed eseguire Best Practices Analyzer.

</div>

<span> </span>

</div>

</div>

</div>

