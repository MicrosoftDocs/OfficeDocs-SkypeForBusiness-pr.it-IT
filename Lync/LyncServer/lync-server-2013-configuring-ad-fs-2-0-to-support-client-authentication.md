---
title: "Lync Server 2013: configurazione di ADFS 2,0 per il supporto dell'autenticazione client"
description: "Lync Server 2013: configurazione di ADFS 2,0 per il supporto dell'autenticazione client."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156eb6d7e8af85dec04601ab8f88c55181db20d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553252"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Configurazione di AD FS 2,0 per il supporto dell'autenticazione client in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-03_

Esistono due tipi di autenticazione possibili che possono essere configurati in modo da consentire ad FS 2,0 di supportare l'autenticazione tramite smart card:

  - Autenticazione basata su form (moduli)

  - Autenticazione del client di sicurezza layer di trasporto

Se si utilizza l'autenticazione basata su moduli, è possibile sviluppare una pagina Web che consenta agli utenti di autenticarsi usando il proprio nome utente/password o utilizzando la smart card e il PIN. Questo argomento è dedicato all'implementazione dell'autenticazione del client per la sicurezza del layer di trasporto con AD FS 2,0. Per ulteriori informazioni sui tipi di autenticazione AD FS 2,0, vedere AD FS 2,0: come modificare il tipo di autenticazione locale all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) .

<div>


**Per configurare ad FS 2,0 per il supporto dell'autenticazione client**

1.  Accedere al computer AD FS 2,0 utilizzando un account di amministratore di dominio.

2.  Avviare Esplora risorse.

3.  Passare a C: \\ Inetpub \\ ADFS \\ ls

4.  Creare una copia di backup del file di web.config esistente.

5.  Aprire il file web.config esistente utilizzando il blocco note.

6.  Dalla barra dei menu, selezionare **modifica** , quindi selezionare **trova**.

7.  Cerca **\<localAuthenticationTypes\>** .
    
    Tenere presente che sono presenti quattro tipi di autenticazione, uno per riga.

8.  Spostare la riga contenente il tipo di autenticazione di TLSClient nella parte superiore dell'elenco della sezione.

9.  Salvare e chiudere il file web.config.

10. Avviare un prompt dei comandi con privilegi elevati.

11. Riavviare IIS eseguendo il comando riportato di seguito:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

