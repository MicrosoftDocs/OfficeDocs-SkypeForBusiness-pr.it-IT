---
title: 'Lync Server 2013: Servizio Web aggiornamento dispositivi'
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
ms.openlocfilehash: 8c2c9f7068943deabb90e5a87d95f35fecfbc30c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="8519b-102">Servizio Web aggiornamento dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8519b-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8519b-103">_**Argomento Ultima modifica:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8519b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8519b-104">Lync Server include il servizio Web Update per dispositivi, che viene installato automaticamente come parte del ruolo Servizi Web.</span><span class="sxs-lookup"><span data-stu-id="8519b-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="8519b-105">Questo servizio consente di scaricare gli aggiornamenti da Microsoft, testarli e quindi distribuire gli aggiornamenti ai telefoni IP nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8519b-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="8519b-106">È anche possibile usare il servizio Web Update per ripristinare i dispositivi alle versioni precedenti del software.</span><span class="sxs-lookup"><span data-stu-id="8519b-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="8519b-107">Questa sezione fornisce informazioni dettagliate su come gestire il servizio Web Update del dispositivo e gli aggiornamenti distribuiti tramite i registri di aggiornamento dei dispositivi, le regole (Lync Phone Edition USA *le regole* per associare gli aggiornamenti della versione del firmware con i dispositivi hardware) e le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8519b-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="8519b-108">Per informazioni dettagliate sul processo e le funzionalità del servizio Web Update per dispositivi, vedere [aggiornare i dispositivi](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) nella raccolta TechNet di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8519b-108">For details about the Device Update Web service process and features, see [Updating Devices](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="8519b-109">Si noti che il servizio Web Update per dispositivi, come tutti i componenti di Lync Phone Edition, funziona allo stesso modo con Lync Server 2013 come avviene con Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8519b-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8519b-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8519b-110">In This Section</span></span>

  - [<span data-ttu-id="8519b-111">Registri e file di aggiornamento dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8519b-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="8519b-112">Regole di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8519b-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="8519b-113">Impostazioni di configurazione di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8519b-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="8519b-114">Visualizzare gli aggiornamenti software per i dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8519b-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8519b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8519b-115">See Also</span></span>


<span data-ttu-id="8519b-116">[Strumenti e servizi per la gestione e la risoluzione dei problemi](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8519b-116">[Tools and Services for Managing and Troubleshooting Devices](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

