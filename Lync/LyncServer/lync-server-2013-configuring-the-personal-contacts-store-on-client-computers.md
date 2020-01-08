---
title: "Lync Server 2013: configurazione dell'archivio contatti personali nei computer client"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4f9b7bbb50b5e63e87904d29a01715fcdcac8c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Configurazione dell'archivio contatti personali nei computer client per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-05_

Se si sta integrando Microsoft Lync Server 2013 e Microsoft Exchange Server 2013, è consigliabile configurare l'archivio contatti personale in tutti i computer client che eseguono Microsoft Lync 2010. In particolare, è consigliabile configurare Lync per l'uso di Exchange come archivio contatti personale e, allo stesso tempo, assicurarsi che gli utenti non siano in grado di ignorare tale decisione. Questa operazione può essere eseguita creando e configurando un valore del registro di sistema in ogni computer client.

Tieni presente che questa operazione non è necessaria nei computer che eseguono Lync 2013.

Per configurare questo valore in un singolo computer, eseguire la procedura seguente:

1.  Nel computer client fare clic su **Start** e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare regedit e quindi premere INVIO.

3.  In Editor del registro di **sistema\_espandere\_HKEY computer locale**, espandere **software**, espandere **criteri**, espandere **Microsoft**e quindi espandere **Communicator**.

4.  Fare clic con il pulsante destro del mouse su **Communicator**, scegliere **nuovo**e quindi fare clic su **valore DWORD (32 bit)**.

5.  Dopo la creazione del nuovo valore, digitare **PersonalContactStoreOverride** e quindi premere INVIO per rinominare il valore.

6.  Verificare che il valore di PersonalContactStoreOverride sia impostato su 0 e quindi chiudere l'editor del registro di sistema.

Se è necessario apportare questa stessa modifica su più computer, è possibile creare un oggetto Criteri di gruppo personalizzato. Per informazioni dettagliate, vedere la documentazione relativa ai [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)criteri di gruppo.

</div>

<span> </span>

</div>

</div>

</div>

