---
title: Modificare le route vocali per l'utilizzo del nuovo Lync Server 2013 Mediation Server
description: Modificare le route vocali per l'utilizzo del nuovo Lync Server 2013 Mediation Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef58ba61512b5de31a74b79e554dbb3f94b67d99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545742"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>Modificare le route vocali per l'utilizzo del nuovo Lync Server 2013 Mediation Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

Questa procedura consente di modificare le route vocali per l'utilizzo di Lync Server 2013 Mediation Server, invece del Mediation Server di Office Communications Server 2007 R2 legacy.

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>Per modificare le route vocali per l'utilizzo del nuovo Mediation Server

1.  Pannello di controllo di Lync Server 2013

2.  Nel riquadro sinistro selezionare **Routing vocale** e quindi **Route**.

3.  Fare clic su **Nuovo** per creare una nuova route vocale.

4.  Completare i campi seguenti:
    
      - **Nome**: digitare un nome descrittivo per la route vocale. Per questo documento verrà utilizzato il nome **W15PSTNRoute**.
    
      - **Descrizione**: digitare una breve descrizione della route vocale.

5.  Ignorare tutte le altre sezioni fino a **Gateway associati**. Fare clic su **Aggiungi**. Selezionare il nuovo gateway predefinito e fare clic su **OK**.

6.  In **Utilizzi PSTN associati** fare clic su **Seleziona**

7.  Nella pagina **Seleziona record utilizzo PSTN** selezionare un nome di record e quindi fare clic su **OK**.

8.  Nella pagina **Nuova route vocale** fare clic su **OK** per creare la **Route vocale**.

9.  Nella pagina **Routing vocale** selezionare **Route**.

10. Spostare la nuova route creata all'inizio dell'elenco e quindi selezionare **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

