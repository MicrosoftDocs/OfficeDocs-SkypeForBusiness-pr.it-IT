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
ms.openlocfilehash: 9e7e6fef4b882a7358a49a994c10829ad5c8a257
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>Abilitare il controllo delle chiamate remote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Il controllo delle chiamate remote consente agli utenti di controllare i propri telefoni PBX (Private Branch Exchange) tramite Lync Server 2013. Se è stato distribuito il controllo delle chiamate remote nell'ambiente legacy e si desidera eseguire la migrazione di Lync Server 2013, è necessario eseguire le attività seguenti:

1.  Installare un gateway SIP/CSTA e configurarlo per la comunicazione con il PBX. È necessario eseguire questo passaggio quando si distribuisce il pool pilota di Lync Server 2013.

2.  Dopo aver unito la topologia e aver eseguito la migrazione dei criteri e delle impostazioni, configurare Lync Server 2013 per instradare le richieste CSTA al gateway SIP/CSTA. Questo passaggio deve essere eseguito manualmente dopo la migrazione automatizzata. Per configurare il routing per le richieste CSTA, eseguire le operazioni seguenti:
    
      - Rimuovere le voci host autorizzate legacy (note come *voci del server attendibili* in Lync Server 2013). Se si esegue la migrazione degli utenti dalla distribuzione legacy, assicurarsi di rimuovere tutte le voci host autorizzate esistenti create per il gateway SIP/CSTA prima di configurare nuove voci dell'applicazione attendibili nel pool pilota di Lync Server 2013. Per informazioni dettagliate sulla rimozione delle voci host autorizzate legacy, vedere [Remove an Authorized host entry](remove-an-authorized-host-entry.md).
    
      - Configurare una route statica per il controllo delle chiamate remote. È possibile configurare una route statica per i singoli pool che si desidera supportino il controllo delle chiamate remote oppure una route statica globale in modo che ogni pool non configurato con una route statica a livello di pool utilizzi la route statica globale. Per informazioni dettagliate su come configurare la route statica, vedere [configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) nella documentazione relativa alla distribuzione.
    
      - Configurare una voce applicazione attendibile per il controllo delle chiamate remote in ogni pool per il quale si desidera il supporto per il controllo delle chiamate remote. Per informazioni dettagliate sulla configurazione di una voce di applicazione attendibile, vedere [Configure a Trusted Application Entry for Remote Call Control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) nella documentazione relativa alla distribuzione.

3.  Se è stato distribuito un gateway SIP/CSTA che utilizza il protocollo TCP (Transmission Control Protocol) per la connessione a Lync Server 2013, definire l'indirizzo IP del gateway in Generatore di topologie. Per informazioni dettagliate sulla definizione dell'indirizzo IP, vedere [define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) nella documentazione relativa alla distribuzione.

4.  Configurare gli utenti di Lync 2013 per il controllo delle chiamate remote abilitando il controllo delle chiamate remote e assegnando un URI (Uniform Resource Identifier) del server di linea e un URI di linea. Quando si esegue la migrazione degli utenti dalla distribuzione legacy a Lync Server 2013, le impostazioni del controllo delle chiamate remote vengono migrate insieme alle altre impostazioni utente.

5.  Se nella distribuzione legacy sono state personalizzate le regole di normalizzazione dei numeri di telefono della Rubrica, è necessario eseguire alcune attività manuali al termine della migrazione automatizzata di criteri e impostazioni per eseguire la migrazione delle regole di normalizzazione personalizzate. Se tali regole non sono state personalizzate, la migrazione della Rubrica viene eseguita insieme al resto della topologia. Per informazioni dettagliate sulla migrazione manuale delle regole di normalizzazione personalizzate, vedere [Migrate Address Book](migrate-address-book_1.md).

</div>

<span> </span>

</div>

</div>

</div>

