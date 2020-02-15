---
title: 'Lync Server 2013: servizio Web aggiornamento dispositivi'
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
ms.openlocfilehash: 7213513657720cc08057cbf2d54d425b5d2a96f4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="21d39-102">Servizio Web aggiornamento dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d39-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d39-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="21d39-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="21d39-104">Lync Server include il servizio Web aggiornamento dispositivi, che viene installato automaticamente come parte del ruolo Servizi Web.</span><span class="sxs-lookup"><span data-stu-id="21d39-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="21d39-105">Questo servizio consente di scaricare gli aggiornamenti da Microsoft, testarli e quindi distribuire gli aggiornamenti ai telefoni IP all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21d39-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="21d39-106">È inoltre possibile utilizzare il servizio Web Aggiornamento dispositivi per ripristinare nei dispositivi le versioni del software precedenti.</span><span class="sxs-lookup"><span data-stu-id="21d39-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="21d39-107">In questa sezione vengono fornite informazioni dettagliate su come gestire il servizio Web aggiornamento dispositivi e gli aggiornamenti distribuiti mediante i registri di aggiornamento dei dispositivi, le regole (Lync Phone Edition utilizza *le regole* per associare gli aggiornamenti della versione del firmware con i dispositivi hardware) e le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="21d39-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="21d39-108">Per informazioni dettagliate sul processo e sulle funzionalità del servizio Web aggiornamento dispositivi, vedere [Updating Devices](http://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span><span class="sxs-lookup"><span data-stu-id="21d39-108">For details about the Device Update Web service process and features, see [Updating Devices](http://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="21d39-109">Si noti che il servizio Web aggiornamento dispositivi, come tutti i componenti di Lync Phone Edition, è compatibile con Lync Server 2013 come accade con Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="21d39-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="21d39-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="21d39-110">In This Section</span></span>

  - [<span data-ttu-id="21d39-111">Registri e file degli aggiornamenti dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d39-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="21d39-112">Regole di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d39-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="21d39-113">Impostazioni di configurazione per l'aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d39-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="21d39-114">Visualizzare gli aggiornamenti software per i dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d39-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21d39-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21d39-115">See Also</span></span>


<span data-ttu-id="21d39-116">[Strumenti e servizi per la gestione e la risoluzione dei problemi dei dispositivi](http://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="21d39-116">[Tools and Services for Managing and Troubleshooting Devices](http://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

