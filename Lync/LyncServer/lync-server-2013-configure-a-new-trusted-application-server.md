---
title: 'Lync Server 2013: configurare un nuovo server applicazioni attendibile'
description: 'Lync Server 2013: configurare un nuovo server applicazioni attendibile.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3cc13c747c5755297b01ae36f27f06d19591acc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552122"
---
# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Configurare un nuovo server applicazioni attendibile in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK che è considerato attendibile da Microsoft Lync Server 2013. Per informazioni dettagliate sulle applicazioni di UCMA, vedere la documentazione relativa a Unified Communications Managed API 3,0 Core SDK [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320) .

Per informazioni sulla configurazione di Microsoft Outlook Web Access (OWA) e Lync Server 2013, vedere la sezione relativa alla configurazione di Outlook Web App e Lync Server 2010 Integration nella documentazione relativa a Microsoft Exchange Server 2013.

Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario avere eseguito l'accesso come membro dei gruppi RTCUniversalServerAdmins e Domain Admins. È inoltre possibile delegare le autorizzazioni e i diritti di amministratore appropriati per l'aggiunta di ruoli del server. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione relativa alla distribuzione. Per poter apportare altre modifiche relative alla configurazione, è necessario appartenere solo al gruppo RTCUniversalServerAdmins..

<div>

## <a name="to-configure-a-trusted-application-server"></a>Per configurare un server applicazioni attendibili

1.  Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

3.  Selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.

4.  Nella finestra di dialogo **Salva topologia con nome** fare clic sul file del generatore di topologie che si desidera utilizzare e quindi fare clic su **Salva**.

5.  Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili**e quindi scegliere **nuovo pool di applicazioni attendibili**.

6.  Immettere il valore di **FQDN pool** per il pool di applicazioni attendibili, specificare se sarà un pool a server singolo o a più server e quindi fare clic su **Avanti**.

7.  Nell'elenco nella pagina **selezionare l'hop successivo** selezionare il pool Front End di Lync Server 2013.

8.  Fare clic su **Fine**.

9.  Selezionare il nodo principale **Lync Server 2013**e quindi fare clic su **Pubblica topologia**dal menu **azioni** .
    
    È necessario che il **pool di applicazioni attendibili** sia stato creato correttamente e sia associato al pool Front end corretto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

