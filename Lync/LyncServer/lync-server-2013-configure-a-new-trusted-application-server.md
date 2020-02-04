---
title: 'Lync Server 2013: configurare un nuovo server applicazioni attendibile'
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
ms.openlocfilehash: dae7e02d7642fed5fea60235283eaa0d7d7e1e35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Configurare un nuovo server applicazioni attendibile in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK attendibile per Microsoft Lync Server 2013. Per informazioni dettagliate sulle applicazioni di UCMA, vedere "documentazione su Unified Communications Managed API 3,0 Core [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)SDK" at.

Per informazioni sulla configurazione di Microsoft Outlook Web Access (OWA) e Lync Server 2013, vedere la pagina relativa alla configurazione di Outlook Web App e Lync Server 2010 Integration nella documentazione di Microsoft Exchange Server 2013.

Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario essere connessi come utenti membri dei gruppi RTCUniversalServerAdmins e Domain Admins. È anche possibile delegare le autorizzazioni e i diritti di amministratore appropriati per l'aggiunta di ruoli del server. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione relativa alla distribuzione. Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.

<div>

## <a name="to-configure-a-trusted-application-server"></a>Per configurare un server applicazioni attendibile

1.  Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

3.  Selezionare **Scarica topologia da distribuzione esistente**e quindi fare clic su **OK**.

4.  Nella finestra di dialogo **Salva topologia con nome** fare clic sul file di generatore di topologia che si vuole usare e quindi fare clic su **Salva**.

5.  Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili**e quindi scegliere **nuovo pool di applicazioni attendibili**.

6.  Immettere il **nome di dominio completo del pool** di applicazioni attendibili, selezionare se si tratta di un server singolo o di più server e quindi fare clic su **Avanti**.

7.  Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool di front end di Lync Server 2013.

8.  Fare clic su **fine**.

9.  Selezionare il nodo superiore **Lync Server 2013**e quindi, nel menu **azioni** , fare clic su **Pubblica topologia**.
    
    Il **pool di applicazioni attendibili** deve essere stato creato correttamente e associato al pool Front-end corretto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

