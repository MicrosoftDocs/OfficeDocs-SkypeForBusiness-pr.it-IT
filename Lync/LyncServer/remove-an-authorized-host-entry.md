---
title: Rimuovere una voce dell'host autorizzato
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 849617676305cc2d7308c0c8b1a48bef327f3c87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a>Rimuovere una voce dell'host autorizzato

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-26_

Questo argomento descrive come rimuovere una voce dell'host autorizzato legacy (nota come *voce di applicazione attendibile* in Lync Server 2013). Quando si esegue la migrazione del controllo delle chiamate remote a una distribuzione di Lync Server 2013, è necessario rimuovere le voci di host autorizzati esistenti per tutti i gateway SIP/CSTA nella distribuzione di Office Communications Server 2007 R2. È necessario usare gli strumenti di amministrazione inclusi in Office Communications Server 2007 R2 per rimuovere le voci esistenti dell'host autorizzato.

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a>Per rimuovere una voce ospitante autorizzata in una distribuzione di Office Communications Server 2007 R2

1.  Aprire la console di amministrazione di Office Communications Server 2007 R2.

2.  Espandere l'albero e fare clic con il pulsante destro del mouse sul pool in cui è stato creato l'host autorizzato.

3.  Fare clic su **Proprietà**e quindi su **Proprietà front-end**.

4.  Fare clic sulla scheda **autorizzazione host** .

5.  Selezionare un server e quindi fare clic su **Rimuovi**.

6.  In **Proprietà**fare clic su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

