---
title: Configurare i record DNS per la distribuzione del pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc89481d26c964d7b436e45f708e5fa9f4a6afc4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurare i record DNS per la distribuzione del pool pilota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-29_

Prima di distribuire il pool pilota di Lync Server 2013, è necessario aggiornare le voci dell'host DNS A per il pool pilota. Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.

**Per configurare i record A dell'host DNS**

1.  Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.

2.  Nell'albero della console per il dominio espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Lync Server 2013.

3.  Scegliere **Nuovo host (A o AAAA)**.

4.  Fare clic su **nome**, digitare il nome host per il pool di Lync Server 2013 (il nome di dominio viene assunto dall'area in cui è definito il record e non è necessario immetterlo come parte del record a).

5.  Fare clic su **indirizzo IP**, digitare l'indirizzo IP per il pool Front end.

6.  Fare clic su **Aggiungi host** e quindi su **OK**.

7.  Al termine, scegliere **Fine**.

</div>

<span> </span>

</div>

</div>

</div>

