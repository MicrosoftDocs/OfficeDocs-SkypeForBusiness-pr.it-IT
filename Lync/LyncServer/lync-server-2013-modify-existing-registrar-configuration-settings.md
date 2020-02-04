---
title: 'Lync Server 2013: modificare le impostazioni di configurazione del registrar esistenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe12f85f7ea8501f478d570612ad52cd350fdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a>Modificare le impostazioni di configurazione del registrar esistenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

È possibile usare il registrar per configurare i protocolli di autenticazione del server proxy. Per informazioni sui protocolli disponibili, vedere [creare impostazioni di configurazione del registrar in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

<div>


> [!NOTE]  
> È consigliabile abilitare sia Kerberos che NTLM quando un server supporta l'autenticazione sia per i client remoti che per quelli aziendali. Il server perimetrale e i server interni comunicano per garantire che solo l'autenticazione NTLM venga offerta ai client remoti. Se in questi server è abilitato solo Kerberos, non è possibile eseguire l'autenticazione degli utenti remoti. Se gli utenti aziendali eseguono l'autenticazione anche sul server, viene usato Kerberos.



</div>

Seguire questa procedura per modificare un registrar esistente.

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a>Per modificare le impostazioni di configurazione del registrar esistenti

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.

4.  Nella pagina **registrar** fare clic su un servizio, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica registrar**selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:
    
      - **Abilitare l'autenticazione Kerberos per consentire** ai server del pool di emettere problemi con l'autenticazione Kerberos.
    
      - **Abilitare l'autenticazione NTLM per consentire** ai server del pool di emettere problemi con NTLM.
    
      - **Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

