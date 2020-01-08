---
title: "Lync Server 2013: configurazione di ADFS 2,0 per supportare l'autenticazione del client"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12f7cad4b36eb96f7b36925aa91e6363b8cdd264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Configurazione di ADFS 2,0 per supportare l'autenticazione del client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-03_

Esistono due tipi di autenticazione possibili che possono essere configurati in modo da consentire AD FS 2,0 di supportare l'autenticazione tramite smart card:

  - Autenticazione basata su moduli (FBA)

  - Autenticazione del client di sicurezza dei livelli di trasporto

Usando l'autenticazione basata su moduli, puoi sviluppare una pagina Web che consente agli utenti di autenticarsi usando il loro nome utente/password o usando la loro smart card e il PIN. Questo argomento illustra come implementare l'autenticazione del client di sicurezza dei livelli di trasporto con ADFS 2,0. Per altre informazioni sui tipi di autenticazione di ADFS 2,0, vedere ADFS 2,0: come modificare il tipo di autenticazione locale [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).

<div>


**Per configurare ADFS 2,0 per supportare l'autenticazione del client**

1.  Accedere al computer ADFS 2,0 usando un account di amministratore di dominio.

2.  Avviare Esplora risorse.

3.  Passare a C:\\Inetpub\\ADFS\\ls

4.  Creare una copia di backup del file Web. config esistente.

5.  Aprire il file Web. config esistente tramite il blocco note.

6.  Nella barra dei menu selezionare **modifica** e quindi **trova**.

7.  Cercare ** \<localAuthenticationTypes\>**.
    
    Tieni presente che sono presenti quattro tipi di autenticazione, uno per riga.

8.  Posizionare la linea contenente il tipo di autenticazione TLSClient nella parte superiore dell'elenco nella sezione.

9.  Salvare e chiudere il file Web. config.

10. Avviare un prompt dei comandi con privilegi elevati.

11. Riavviare IIS eseguendo il comando seguente:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

