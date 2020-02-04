---
title: Modificare le route vocali per usare il nuovo server di mediazione Lync Server 2013
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
ms.openlocfilehash: 40f9bed4262adcabdb23e5b5b85e7de43292d18b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>Modificare le route vocali per usare il nuovo server di mediazione Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Questa procedura modifica le route vocali per l'uso di Lync Server 2013 Mediation Server, invece dell'legacy Office Communications Server 2007 R2 Mediation Server.

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>Per modificare le route vocali in uso del nuovo Mediation Server

1.  Pannello di controllo di Lync Server 2013

2.  Nel riquadro sinistro selezionare **routing vocale** e quindi **Route**.

3.  Fare clic su **nuovo** per creare una nuova route vocale.

4.  Compilare i campi seguenti:
    
      - **Nome**: digitare un nome descrittivo della route vocale. Per questo documento useremo **W15PSTNRoute**.
    
      - **Descrizione**: digitare una breve descrizione della route vocale.

5.  Ignorare tutte le sezioni rimanenti fino a raggiungere i **gateway associati**. Fare clic su **Aggiungi**. Selezionare il nuovo gateway predefinito e fare clic su **OK**.

6.  In **usi PSTN associati**fare clic su **Seleziona**.

7.  Nella pagina **Seleziona record utilizzo PSTN** selezionare un nome di record e quindi fare clic su **OK**.

8.  Nella pagina **nuova route vocale** fare clic su **OK** per creare la **Route vocale**.

9.  Nella pagina **routing vocale** selezionare **Route**.

10. Passare la route appena creata all'inizio dell'elenco e quindi selezionare **commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

