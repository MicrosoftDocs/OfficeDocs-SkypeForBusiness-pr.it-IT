---
title: Distribuire client di Lync Server 2013
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
ms.openlocfilehash: ffc6ee3831968c34bcdb501fcdf543626546e2c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="0111f-102">Distribuire client di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0111f-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0111f-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0111f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0111f-104">Dopo aver eseguito la migrazione degli utenti a Lync Server 2013, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0111f-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="0111f-105">Usare il filtro della versione client nel nuovo server Lync Server 2013 per consentire l'accesso solo ai client con gli aggiornamenti più recenti installati.</span><span class="sxs-lookup"><span data-stu-id="0111f-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="0111f-106">Se necessario, configurare le impostazioni dei criteri di gruppo necessarie per l'avvio automatico del client.</span><span class="sxs-lookup"><span data-stu-id="0111f-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="0111f-107">Per informazioni dettagliate, vedere [configurazione dei criteri di avvio del client in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0111f-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="0111f-108">La configurazione di queste impostazioni è necessaria solo se si vogliono modificare i criteri di avvio dei client esistenti o se si vogliono impostare nuovi criteri di avvio del client.</span><span class="sxs-lookup"><span data-stu-id="0111f-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="0111f-109">Se non si prevede di configurare i criteri di avvio del client oppure se si vuole che i criteri di avvio del client legacy rimangano in vigore, non è necessario eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="0111f-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="0111f-110">Configurare altri criteri utente e client per utenti o gruppi di utenti specifici utilizzando il pannello di controllo di Lync Server 2013, Lync Server 2013 Management Shell o entrambi.</span><span class="sxs-lookup"><span data-stu-id="0111f-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="0111f-111">Per informazioni dettagliate, vedere [impostazioni nuove e modificate per Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0111f-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="0111f-112">Distribuire la versione più recente dei client di Lync Server 2013 insieme agli aggiornamenti cumulativi più recenti.</span><span class="sxs-lookup"><span data-stu-id="0111f-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="0111f-113">Per informazioni dettagliate, vedere [distribuzione di client e dispositivi in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0111f-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="0111f-114">Opzionale Se l'organizzazione richiede la modalità di privacy avanzata della presenza di Lync Server 2013, una volta completata la migrazione, definire una regola di criteri di versione client per impedire l'accesso alle versioni precedenti del client.</span><span class="sxs-lookup"><span data-stu-id="0111f-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="0111f-115">Abilitare quindi la modalità di privacy avanzata della presenza.</span><span class="sxs-lookup"><span data-stu-id="0111f-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0111f-116">Non abilitare la modalità di privacy avanzata della presenza di Lync 2013 finché ogni utente di un pool di server specifico non ha installato le versioni client più recenti.</span><span class="sxs-lookup"><span data-stu-id="0111f-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

