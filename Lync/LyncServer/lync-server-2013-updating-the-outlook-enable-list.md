---
title: "Lync Server 2013: aggiornamento dell'elenco di abilitazione di Outlook"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1f71d1ef0ebcb6bc5f8aee8875c013a24a4de0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Aggiornamento dell'elenco di abilitazione di Outlook in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-07_

È possibile verificare che il componente aggiuntivo per riunioni online per Microsoft Lync 2013 rimanga sempre abilitato per gli utenti creando un criterio che lo includa nell'elenco di gestione del componente aggiuntivo per Outlook. I criteri per l'elenco di gestione dei componenti aggiuntivi sono inclusi nei file dei modelli amministrativi di Office per la console di gestione di Criteri di gruppo. Crea una chiave del registro di sistema\\in\\HKCU\\software\\Policies\\Microsoft\\Office\\15,0\\Outlook15 resilienza AddIn. È possibile aggiungere un valore per UCAddin. dll a questa chiave e configurare il valore UCAddin. dll in modo che sia sempre abilitato e che gli utenti non possano disabilitarlo manualmente

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Per aggiungere UCAddin. dll all'elenco del componente aggiuntivo di Outlook

  - Per la chiave del registro di sistema di AddIn,\\che\\si\\trova\\in\\HKCU\\software\\Policies\\Microsoft Office 15,0 Outlook15 resilienza AddIn, aggiungere il seguente valore:
    
      - Tipo di registro =\_reg SZ
    
      - Nome = ucaddin.dll
    
      - Valore = 1 (specifica che il componente aggiuntivo è sempre abilitato e non può essere gestito dall'utente finale)

</div>

</div>

<span> </span>

</div>

</div>

</div>

