---
title: 'Lync Server 2013: impostazioni di criteri di gruppo per Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba88fdce88280597e9e621c13267de2b9b76d0fb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="9246e-102">Impostazioni di criteri di gruppo per Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9246e-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9246e-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9246e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9246e-104">Nelle versioni precedenti di Lync e Office Communicator, era disponibile un modello amministrativo Communicator. adm autonomo per la configurazione delle impostazioni dei criteri di gruppo client.</span><span class="sxs-lookup"><span data-stu-id="9246e-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="9246e-105">Per Lync 2013, sono inclusi i nuovi file dei modelli amministrativi (file con estensione ADMX e ADML) insieme al modello amministrativo di criteri di gruppo di Office.</span><span class="sxs-lookup"><span data-stu-id="9246e-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="9246e-106">La disponibilità dei file di Lync 2013. admx e ADML consente di scaricare modelli e gestire in modo centralizzato le impostazioni di criteri di gruppo per tutti i programmi e i Language Pack di Office.</span><span class="sxs-lookup"><span data-stu-id="9246e-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="9246e-107">Per informazioni dettagliate, vedere "file dei modelli amministrativi di Office 2013 (ADMX, ADML)" nella documentazione di <http://go.microsoft.com/fwlink/p/?linkid=267516>Office 2013 all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="9246e-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="9246e-108">Criteri di avvio automatico del client</span><span class="sxs-lookup"><span data-stu-id="9246e-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="9246e-109">Sono disponibili diversi criteri di avvio automatico del client che è consigliabile configurare prima che gli utenti accedano al server per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="9246e-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="9246e-110">Poiché questi criteri hanno effetto prima che il client esegua l'accesso e inizi a ricevere impostazioni di provisioning di tipo in-band dal server, è possibile utilizzare Criteri di gruppo per configurarli.</span><span class="sxs-lookup"><span data-stu-id="9246e-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="9246e-111">Per ulteriori informazioni, vedere [configurazione dei criteri di avvio del client in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9246e-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

