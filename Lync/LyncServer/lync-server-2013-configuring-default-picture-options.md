---
title: 'Lync Server 2013: configurazione delle opzioni predefinite per le immagini'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e551d069da9a3afb7a884c28096dd97ab3702539
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a>Configurazione delle opzioni per le immagini predefinite in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-22_

Per impostazione predefinita, le immagini degli utenti vengono visualizzate automaticamente. Se gli utenti desiderano nascondere le proprie immagini, possono selezionare l'opzione **Nascondi immagine personale** nel client Lync. Tuttavia, questa impostazione viene ignorata da altre applicazioni di Office.

Se la possibilità di visualizzare immagini anche quando è disattivata dall'utente è un problema, è possibile modificare le impostazioni di visualizzazione dell'immagine di Lync a livello globale o per un sito o un servizio in modo che le immagini degli utenti non vengano visualizzate per impostazione predefinita. Usa il cmdlet Lync Server Management Shell seguente in modo che le immagini dell'utente non vengano visualizzate, a meno che non selezioni esplicitamente l'opzione **Mostra immagine personale** nel client:

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

Per altre informazioni su questo cmdlet, vedere [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) nella documentazione di Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

