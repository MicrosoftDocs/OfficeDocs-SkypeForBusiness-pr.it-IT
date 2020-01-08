---
title: Configurare i record DNS per la distribuzione del pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c9bc007eda604ce4894497db4a6ef334315d28
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40980608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurare i record DNS per la distribuzione del pool pilota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-24_

Prima di distribuire il pool di piloti di Lync Server 2013, è necessario aggiornare le voci dell'host DNS per il pool di piloti. Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio al minimo come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.

**Per configurare i record dell'host DNS**

1.  Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.

2.  Nell'albero della console per il dominio espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Lync Server 2013.

3.  Fare clic su **nuovo host (A o AAAA)**.

4.  Fare clic su **nome**, digitare il nome host per il pool (il nome di dominio viene considerato dalla zona in cui è definito il record e non deve essere immesso come parte del record a).

5.  Fare clic su **indirizzo IP**, digitare l'indirizzo IP per il pool Front-end.

6.  Fare clic su **Aggiungi host**e quindi su **OK**.

7.  Al termine, fare clic su **fine**.

</div>

<span> </span>

</div>

</div>

</div>

