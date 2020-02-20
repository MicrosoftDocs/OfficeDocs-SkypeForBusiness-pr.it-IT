---
title: 'Lync Server 2013: distribuzione di Lync Server 2013 Standard Edition in un Lync Server 2013 Enterprise esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76d7183e60c09729758d7297fd3b6db2cd6622d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="e2d64-102">Distribuzione di Lync Server 2013 Standard Edition in un Lync Server 2013 Enterprise esistente</span><span class="sxs-lookup"><span data-stu-id="e2d64-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2d64-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e2d64-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e2d64-104">La distribuzione di un server Standard Edition in una distribuzione Enterprise Edition esistente è simile alla distribuzione di ruoli del server aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e2d64-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="e2d64-105">Un server Standard Edition potrebbe essere distribuito in un altro sito, consentendo agli utenti di quel sito di essere ospitati sul server Standard Edition anziché sul pool Front end in una rete WAN (Wide Area Network).</span><span class="sxs-lookup"><span data-stu-id="e2d64-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="e2d64-106">Le procedure per l'installazione del nuovo sito e dei nuovi server in quel sito sono già definite in altre sezioni della documentazione relativa alla [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) .</span><span class="sxs-lookup"><span data-stu-id="e2d64-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="e2d64-107">**Per definire un nuovo sito**</span><span class="sxs-lookup"><span data-stu-id="e2d64-107">**To define a new site**</span></span>

1.  <span data-ttu-id="e2d64-108">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="e2d64-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e2d64-109">Nell'albero della console fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **nuovo sito centrale**.</span><span class="sxs-lookup"><span data-stu-id="e2d64-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="e2d64-110">Nella pagina **Identificare il sito** assegnare un nome al sito e facoltativamente immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="e2d64-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="e2d64-111">Eseguire le procedure per definire il resto della topologia del sito.</span><span class="sxs-lookup"><span data-stu-id="e2d64-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="e2d64-112">Per informazioni dettagliate, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="e2d64-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="e2d64-113">Pubblicare la topologia aggiornata.</span><span class="sxs-lookup"><span data-stu-id="e2d64-113">Publish the updated topology.</span></span> <span data-ttu-id="e2d64-114">Per ulteriori informazioni, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="e2d64-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="e2d64-115">Configurare e installare un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e2d64-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="e2d64-116">Se è stato distribuito un ambiente con un solo server Standard Edition, è stato avviato il processo di installazione dalla distribuzione guidata di Lync Server utilizzando il collegamento <STRONG>prepara primo server Standard Edition</STRONG> per installare i file di database iniziali nel nuovo server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e2d64-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="e2d64-117">Questo processo non viene seguito quando <STRONG>si</STRONG> installa un server Standard Edition in una distribuzione di Lync Server 2013 esistente.</span><span class="sxs-lookup"><span data-stu-id="e2d64-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

