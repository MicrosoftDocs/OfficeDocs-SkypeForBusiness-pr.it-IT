---
title: 'Lync Server 2013: aggiunta di un collegamento personalizzato ai messaggi di errore di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 619bdaaa1a1c3b7723f2df9c74e106321bdb054c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521453"
---
# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Aggiunta di un collegamento personalizzato ai messaggi di errore di Lync in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

Personalizzare i messaggi di errore di Lync 2013 aggiungendo un collegamento alla propria risoluzione dei problemi o informazioni sul supporto tecnico. A tale scopo, utilizzare i cmdlet **New-CsClientPolicy** o **Set-CsClientPolicy**di   Lync Server Management Shell con il parametro CustomLinkInErrorMessages. Il testo del collegamento personalizzato è "fare clic qui per gli argomenti di supporto dall'amministratore" e non può essere personalizzato.

Ad esempio, il comando seguente fa in modo che il collegamento personalizzato venga visualizzato nell'area della nota a piè di pagina di ogni messaggio di errore di Lync 2013 e imposta la destinazione del collegamento su http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Utilizzare **Grant-CSClientPolicy** per assegnare il nuovo criterio agli utenti. Per informazioni dettagliate, vedere **New-CsClientPolicy** e **Grant-CsClientPolicy** nella documentazione di Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

