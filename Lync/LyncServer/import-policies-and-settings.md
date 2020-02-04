---
title: Importare criteri e impostazioni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f8023f917e3da6757ce27ede44a63cf0ab1a08d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a><span data-ttu-id="81dd2-102">Importare criteri e impostazioni</span><span class="sxs-lookup"><span data-stu-id="81dd2-102">Import policies and settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81dd2-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="81dd2-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="81dd2-104">Dopo aver merge le informazioni sulla topologia di Office Communications Server 2007 R2 con il pool di piloti di Lync Server 2013, è necessario eseguire un cmdlet Lync Server 2013 Management Shell per eseguire la migrazione dei criteri e delle impostazioni di configurazione di Office Communications Server 2007 R2 al pool di piloti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81dd2-104">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="81dd2-105">Il cmdlet **Import-CsLegacyConfiguration** importa i criteri, le route vocali, i dial plan, gli URL di Communicator Web Access e i numeri di accesso per le chiamate in ingresso in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81dd2-105">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="81dd2-106">Per eseguire la migrazione di criteri e impostazioni</span><span class="sxs-lookup"><span data-stu-id="81dd2-106">To migrate policies and settings</span></span>

1.  <span data-ttu-id="81dd2-107">Nel server front-end di Lync Server 2013 Avviare Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="81dd2-107">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="81dd2-108">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="81dd2-108">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="81dd2-109">Dopo aver importato i criteri, usare la procedura seguente per visualizzare i criteri importati nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="81dd2-109">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="81dd2-110">Per visualizzare i criteri importati</span><span class="sxs-lookup"><span data-stu-id="81dd2-110">To view imported policies</span></span>

1.  <span data-ttu-id="81dd2-111">Aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81dd2-111">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="81dd2-112">Fare clic su **routing vocale** e visualizzare i criteri importati.</span><span class="sxs-lookup"><span data-stu-id="81dd2-112">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="81dd2-113">Fare clic su servizi di **conferenza** e visualizzare i criteri importati.</span><span class="sxs-lookup"><span data-stu-id="81dd2-113">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="81dd2-114">Fare clic su **Federazione e accesso esterno** e visualizzare i criteri importati.</span><span class="sxs-lookup"><span data-stu-id="81dd2-114">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="81dd2-115">Fare clic su **monitoraggio e archiviazione** e visualizzare i criteri importati.</span><span class="sxs-lookup"><span data-stu-id="81dd2-115">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

