---
title: 'Lync Server 2013: distribuzione di Lync Server 2013 Standard Edition in un Lync Server 2013 Enterprise esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76d7183e60c09729758d7297fd3b6db2cd6622d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>Distribuzione di Lync Server 2013 Standard Edition in un Lync Server 2013 Enterprise esistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

La distribuzione di un server Standard Edition in una distribuzione Enterprise Edition esistente è simile alla distribuzione di ruoli del server aggiuntivi. Un server Standard Edition potrebbe essere distribuito in un altro sito, consentendo agli utenti di quel sito di essere ospitati sul server Standard Edition anziché sul pool Front end in una rete WAN (Wide Area Network). Le procedure per l'installazione del nuovo sito e dei nuovi server in quel sito sono già definite in altre sezioni della documentazione relativa alla [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) .

<div id="sectionSection0" class="section">

**Per definire un nuovo sito**

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  Nell'albero della console fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **nuovo sito centrale**.

3.  Nella pagina **Identificare il sito** assegnare un nome al sito e facoltativamente immettere una descrizione.

4.  Eseguire le procedure per definire il resto della topologia del sito. Per informazioni dettagliate, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Pubblicare la topologia aggiornata. Per ulteriori informazioni, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Configurare e installare un server Standard Edition.
    
    <div>
    

    > [!Caution]  
    > Se è stato distribuito un ambiente con un solo server Standard Edition, è stato avviato il processo di installazione dalla distribuzione guidata di Lync Server utilizzando il collegamento <STRONG>prepara primo server Standard Edition</STRONG> per installare i file di database iniziali nel nuovo server Standard Edition. Questo processo non viene seguito quando <STRONG>si</STRONG> installa un server Standard Edition in una distribuzione di Lync Server 2013 esistente.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

