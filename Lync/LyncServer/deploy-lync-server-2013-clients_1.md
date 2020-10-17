---
title: Distribuire i client di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d42b410765b4cf8b7a52221f76ba532347ee3ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503003"
---
# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="87f88-102">Distribuire i client di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87f88-102">Deploy Lync Server 2013 clients</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87f88-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="87f88-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="87f88-104">Dopo aver eseguito la migrazione degli utenti a Lync Server 2013, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="87f88-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="87f88-105">Utilizzare il filtro versione client nel nuovo server Lync Server 2013 per consentire l'accesso solo ai client con gli aggiornamenti più recenti installati.</span><span class="sxs-lookup"><span data-stu-id="87f88-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="87f88-106">Se necessario, configurare le impostazioni dei Criteri di gruppo necessarie per l'avvio automatico dei client.</span><span class="sxs-lookup"><span data-stu-id="87f88-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="87f88-107">Per informazioni dettagliate, vedere [Configuring Client bootstrap Policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="87f88-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="87f88-108">La configurazione di queste impostazioni è necessaria solo se si desidera modificare i criteri esistenti di avvio automatico dei client oppure impostare nuovi criteri.</span><span class="sxs-lookup"><span data-stu-id="87f88-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="87f88-109">Se non si intende configurare i criteri di avvio automatico dei client o si desidera rimangano effettivi i criteri legacy, non sarà necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="87f88-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="87f88-110">Configurare gli altri criteri utente e client per utenti o gruppi di utenti specifici utilizzando il pannello di controllo di Lync Server 2013, Lync Server 2013 Management Shell o entrambi.</span><span class="sxs-lookup"><span data-stu-id="87f88-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="87f88-111">Per ulteriori informazioni, vedere [impostazioni nuove e modificate per Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="87f88-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="87f88-112">Distribuire la versione più recente dei client di Lync Server 2013 insieme agli aggiornamenti cumulativi più recenti.</span><span class="sxs-lookup"><span data-stu-id="87f88-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="87f88-113">Per informazioni dettagliate, vedere [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="87f88-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="87f88-114">Optional Se nell'organizzazione è necessaria la modalità privacy di Lync Server 2013 Enhanced Presence, una volta completata la migrazione, definire una regola di criteri di versione client per impedire l'accesso alle versioni precedenti dei client.</span><span class="sxs-lookup"><span data-stu-id="87f88-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="87f88-115">Quindi, abilitare la modalità privacy della presenza avanzata.</span><span class="sxs-lookup"><span data-stu-id="87f88-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="87f88-116">Non abilitare la modalità privacy di Lync 2013 Enhanced Presence finché ogni utente su un determinato pool di server non dispone delle versioni client più recenti installate.</span><span class="sxs-lookup"><span data-stu-id="87f88-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

