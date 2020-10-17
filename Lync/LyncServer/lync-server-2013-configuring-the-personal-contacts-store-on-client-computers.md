---
title: "Lync Server 2013: configurazione dell'archivio dei contatti personali sui computer client"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6020182c0083ecadcb65c07fa71be213f9458f0f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532343"
---
# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Configurazione dell'archivio dei contatti personali sui computer client per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

Se si esegue l'integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013, è consigliabile configurare l'archivio dei contatti personali su tutti i computer client che eseguono Microsoft Lync 2010. In particolare, è consigliabile configurare Lync per l'utilizzo di Exchange come archivio dei contatti personali e, al tempo stesso, garantire che gli utenti non siano in grado di ignorare tale decisione. A tale scopo, è possibile creare e configurare un valore del registro di sistema in ogni computer client.

Tenere presente che non è necessario nei computer che eseguono Lync 2013.

Per configurare questo valore in un singolo computer, eseguire la procedura seguente:

1.  Nel computer client fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui** digitare regedit e quindi premere INVIO.

3.  In Editor del registro di sistema espandere **HKEY \_ \_ computer locale**, espandere **software**, espandere **criteri**, espandere **Microsoft**e quindi **Communicator**.

4.  Fare clic con il pulsante destro del mouse su **Communicator**, scegliere **nuovo**e quindi fare clic su **valore DWORD (32 bit)**.

5.  Dopo aver creato il nuovo valore, digitare **PersonalContactStoreOverride** e quindi premere INVIO per rinominare il valore.

6.  Verificare che il valore di PersonalContactStoreOverride sia impostato su 0 e quindi chiudere l'editor del Registro di sistema.

Se si desidera eseguire le stesse modifiche in più computer è possibile creare un oggetto Criteri di gruppo personalizzato. Per informazioni dettagliate, vedere la documentazione relativa ai criteri di gruppo all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543) .

</div>

<span> </span>

</div>

</div>

</div>

