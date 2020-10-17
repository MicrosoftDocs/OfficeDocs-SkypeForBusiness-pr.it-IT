---
title: 'Lync Server 2013: servizio Web aggiornamento dispositivi'
description: 'Lync Server 2013: servizio Web aggiornamento dispositivi.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45511d34ab99f295481472f2a3c14bf21da32ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565952"
---
# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="7aa0d-103">Servizio Web aggiornamento dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa0d-103">Device Update Web service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa0d-104">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="7aa0d-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="7aa0d-105">Lync Server include il servizio Web aggiornamento dispositivi, che viene installato automaticamente come parte del ruolo Servizi Web.</span><span class="sxs-lookup"><span data-stu-id="7aa0d-105">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="7aa0d-106">Questo servizio consente di scaricare gli aggiornamenti da Microsoft, testarli e quindi distribuire gli aggiornamenti ai telefoni IP all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7aa0d-106">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="7aa0d-107">È inoltre possibile utilizzare il servizio Web Aggiornamento dispositivi per ripristinare nei dispositivi le versioni del software precedenti.</span><span class="sxs-lookup"><span data-stu-id="7aa0d-107">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="7aa0d-108">In questa sezione vengono fornite informazioni dettagliate su come gestire il servizio Web aggiornamento dispositivi e gli aggiornamenti distribuiti mediante i registri di aggiornamento dei dispositivi, le regole (Lync Phone Edition utilizza *le regole* per associare gli aggiornamenti della versione del firmware con i dispositivi hardware) e le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7aa0d-108">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="7aa0d-109">Per informazioni dettagliate sul processo e sulle funzionalità del servizio Web aggiornamento dispositivi, vedere [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span><span class="sxs-lookup"><span data-stu-id="7aa0d-109">For details about the Device Update Web service process and features, see [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="7aa0d-110">Si noti che il servizio Web aggiornamento dispositivi, come tutti i componenti di Lync Phone Edition, è compatibile con Lync Server 2013 come accade con Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7aa0d-110">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7aa0d-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="7aa0d-111">In This Section</span></span>

  - [<span data-ttu-id="7aa0d-112">Registri e file degli aggiornamenti dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa0d-112">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="7aa0d-113">Regole di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa0d-113">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="7aa0d-114">Impostazioni di configurazione per l'aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa0d-114">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="7aa0d-115">Visualizzare gli aggiornamenti software per i dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa0d-115">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7aa0d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7aa0d-116">See Also</span></span>


<span data-ttu-id="7aa0d-117">[Strumenti e servizi per la gestione e la risoluzione dei problemi dei dispositivi](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7aa0d-117">[Tools and Services for Managing and Troubleshooting Devices](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

