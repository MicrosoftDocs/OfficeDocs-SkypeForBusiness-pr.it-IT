---
title: "Lync Server 2013: configurazione dell'archivio contatti personali nei computer client"
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
ms.openlocfilehash: 77e6e48593bb3dc7a11375b13346ad59b2f40c0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="dc403-102">Configurazione dell'archivio contatti personali nei computer client per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc403-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc403-103">_**Argomento Ultima modifica:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="dc403-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="dc403-104">Se si sta integrando Microsoft Lync Server 2013 e Microsoft Exchange Server 2013, è consigliabile configurare l'archivio contatti personale in tutti i computer client che eseguono Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="dc403-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="dc403-105">In particolare, è consigliabile configurare Lync per l'uso di Exchange come archivio contatti personale e, allo stesso tempo, assicurarsi che gli utenti non siano in grado di ignorare tale decisione.</span><span class="sxs-lookup"><span data-stu-id="dc403-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="dc403-106">Questa operazione può essere eseguita creando e configurando un valore del registro di sistema in ogni computer client.</span><span class="sxs-lookup"><span data-stu-id="dc403-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="dc403-107">Tieni presente che questa operazione non è necessaria nei computer che eseguono Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dc403-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="dc403-108">Per configurare questo valore in un singolo computer, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="dc403-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="dc403-109">Nel computer client fare clic su **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="dc403-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="dc403-110">Nella finestra di dialogo **Esegui** Digitare regedit e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="dc403-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="dc403-111">In Editor del registro di **sistema\_espandere\_HKEY computer locale**, espandere **software**, espandere **criteri**, espandere **Microsoft**e quindi espandere **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="dc403-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="dc403-112">Fare clic con il pulsante destro del mouse su **Communicator**, scegliere **nuovo**e quindi fare clic su **valore DWORD (32 bit)**.</span><span class="sxs-lookup"><span data-stu-id="dc403-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="dc403-113">Dopo la creazione del nuovo valore, digitare **PersonalContactStoreOverride** e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="dc403-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="dc403-114">Verificare che il valore di PersonalContactStoreOverride sia impostato su 0 e quindi chiudere l'editor del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="dc403-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="dc403-115">Se è necessario apportare questa stessa modifica su più computer, è possibile creare un oggetto Criteri di gruppo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="dc403-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="dc403-116">Per informazioni dettagliate, vedere la documentazione relativa ai [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="dc403-116">For details, see the Group Policy documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

