---
title: Abilitare il controllo delle chiamate remote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190f4e56a291ce48b5cd18b2dcd3e1b3461e3d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>Abilitare il controllo delle chiamate remote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Il controllo delle chiamate remote consente agli utenti di controllare i telefoni PBX (Private Branch Exchange) desktop tramite Lync Server 2013. Se il controllo delle chiamate remote è stato distribuito nell'ambiente legacy e si vuole eseguire la migrazione di Lync Server 2013, è necessario svolgere le attività seguenti:

1.  Installare un gateway SIP/CSTA e configurarlo per comunicare con il PBX. È necessario eseguire questo passaggio quando si distribuisce il pool di piloti di Lync Server 2013.

2.  Dopo l'Unione della topologia e la migrazione dei criteri e delle impostazioni, configurare Lync Server 2013 per instradare le richieste CSTA al gateway SIP/CSTA. Questo passaggio è un passaggio manuale che segue la migrazione automatica. Per configurare il routing per le richieste CSTA, eseguire le operazioni seguenti:
    
      - Rimuovere le voci di host autorizzati legacy (note come *voci del server attendibili* in Lync Server 2013). Se si esegue la migrazione di utenti dalla distribuzione legacy, assicurarsi di rimuovere tutte le voci di host autorizzati esistenti create per il gateway SIP/CSTA prima di configurare le nuove voci dell'applicazione attendibile nel pool di piloti di Lync Server 2013. Per informazioni dettagliate su come rimuovere le voci legacy dell'host autorizzato, vedere [rimuovere una voce ospitante autorizzata](remove-an-authorized-host-entry.md).
    
      - Configurare una route statica per il controllo delle chiamate remote. È possibile configurare una route statica per i singoli pool che si desidera supportare il controllo delle chiamate remote oppure una route statica globale in modo che ogni pool non configurato con una route statica a livello di pool usi la route statica globale. Per informazioni dettagliate su come configurare la route statica, vedere [configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) nella documentazione relativa alla distribuzione.
    
      - Configurare una voce di applicazione attendibile per il controllo delle chiamate remote in ogni pool per il quale si vuole supportare il controllo delle chiamate remote. Per informazioni dettagliate su come configurare una voce di applicazione attendibile, vedere [configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) nella documentazione relativa alla distribuzione.

3.  Se è stato distribuito un gateway SIP/CSTA che usa TCP (Transmission Control Protocol) per connettersi a Lync Server 2013, definire l'indirizzo IP del gateway in Generatore di topologia. Per informazioni dettagliate sulla definizione dell'indirizzo IP, vedere [definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) nella documentazione relativa alla distribuzione.

4.  Configurare gli utenti di Lync 2013 per il controllo delle chiamate remote abilitando il controllo delle chiamate remote e assegnando un URI (Uniform Resource Identifier) del server di linea e un URI di linea. Quando si esegue la migrazione degli utenti dalla distribuzione legacy a Lync Server 2013, vengono migrate le impostazioni del controllo delle chiamate remote insieme alle altre impostazioni utente.

5.  Se si personalizzano le regole di normalizzazione dei numeri di telefono della Rubrica nella distribuzione legacy, è necessario eseguire alcune attività manuali dopo il completamento della migrazione automatica di criteri e impostazioni per eseguire la migrazione delle regole di normalizzazione personalizzate. Se non sono state personalizzate regole di normalizzazione, la Rubrica viene migrata insieme al resto della topologia. Per informazioni dettagliate sulla migrazione manuale di regole di normalizzazione personalizzate, vedere [eseguire la migrazione della rubrica](migrate-address-book_1.md).

</div>

<span> </span>

</div>

</div>

</div>

