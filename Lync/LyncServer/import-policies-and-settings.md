---
title: Importare criteri e impostazioni
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1163a8abc54f60d55f1042d6d82552ca9f133a60
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523393"
---
# <a name="import-policies-and-settings"></a><span data-ttu-id="c5051-102">Importare criteri e impostazioni</span><span class="sxs-lookup"><span data-stu-id="c5051-102">Import policies and settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5051-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c5051-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c5051-104">Dopo aver unito le informazioni della topologia di Office Communications Server 2007 R2 con il pool pilota di Lync Server 2013, è necessario eseguire un cmdlet di Lync Server 2013 Management Shell per eseguire la migrazione dei criteri e delle impostazioni di configurazione di Office Communications Server 2007 R2 al pool pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5051-104">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="c5051-105">Il cmdlet **Import-CsLegacyConfiguration** Importa criteri, route vocali, dial plan, URL di Communicator Web Access e numeri di accesso esterno a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5051-105">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="c5051-106">Per eseguire la migrazione di criteri e impostazioni</span><span class="sxs-lookup"><span data-stu-id="c5051-106">To migrate policies and settings</span></span>

1.  <span data-ttu-id="c5051-107">Nel server front end di Lync Server 2013 Avviare Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c5051-107">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="c5051-108">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c5051-108">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="c5051-109">Dopo l'importazione dei criteri, utilizzare la procedura seguente per visualizzare i criteri importati nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5051-109">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="c5051-110">Per visualizzare i criteri importati</span><span class="sxs-lookup"><span data-stu-id="c5051-110">To view imported policies</span></span>

1.  <span data-ttu-id="c5051-111">Aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5051-111">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="c5051-112">Fare clic su **Routing vocale** e visualizzare i criteri importati.</span><span class="sxs-lookup"><span data-stu-id="c5051-112">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="c5051-113">Fare clic su **Servizio di conferenza** e visualizzare i criteri importati.</span><span class="sxs-lookup"><span data-stu-id="c5051-113">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="c5051-114">Fare clic su **Federazione e accesso esterno** e visualizzare i criteri importati.</span><span class="sxs-lookup"><span data-stu-id="c5051-114">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="c5051-115">Fare clic su **Monitoraggio e archiviazione** e visualizzare i criteri importati.</span><span class="sxs-lookup"><span data-stu-id="c5051-115">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

