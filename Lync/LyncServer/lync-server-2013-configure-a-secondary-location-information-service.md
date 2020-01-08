---
title: 'Lync Server 2013: configurare un servizio informazioni posizione secondario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8219aa234330120e6462a600b9c2c27b4b11c100
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Configurare un servizio di informazioni sulla posizione secondaria in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-30_

Lync Server 2013 offre un'interfaccia di servizio Web che può essere usata per puntare il servizio informazioni sulla posizione in un database di origine della posizione secondaria (SLS). L'interfaccia del servizio Web che si connette al database SLS deve essere conforme al WSDL del servizio informazioni sulla posizione. Se sono configurati sia il database della posizione che il database della posizione secondaria, il servizio informazioni sulla posizione esegue prima di tutto il database della posizione e, se non viene trovata alcuna corrispondenza, Invia la richiesta di posizione dal client al database SLS. Se la posizione esiste nella SLS, il servizio informazioni sulla posizione restituirà la posizione al client.

Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per il cmdlet seguente:

  - **Set-CsWebServiceConfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>Per configurare il database delle posizioni secondarie

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet seguente per configurare l'URL per la posizione del database della posizione secondaria.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

