---
title: "Lync Server 2013: problemi con il test dell'ambiente"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65803ff396a9615787291de2d728fe63f3350d0b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="d35cb-102">Problemi con il test dell'ambiente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d35cb-102">Issues with the environment test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d35cb-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d35cb-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d35cb-104">Analizzatore procedure consigliate consente di verificare che l'ambiente Lync Server 2013 sia una configurazione supportata.</span><span class="sxs-lookup"><span data-stu-id="d35cb-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="d35cb-105">Come parte del controllo Active Directory Domain Services, Best Practices Analyzer esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d35cb-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="d35cb-106">Verifica la preparazione dello schema e della foresta dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d35cb-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="d35cb-107">Identifica il numero di siti e domini di servizi di dominio Active Directory nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d35cb-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="d35cb-108">Controlla i livelli di foresta e di dominio.</span><span class="sxs-lookup"><span data-stu-id="d35cb-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="d35cb-109">Controlla la versione del controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="d35cb-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="d35cb-110">Identifica il contesto dei nomi di dominio, configurazione e schema.</span><span class="sxs-lookup"><span data-stu-id="d35cb-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="d35cb-111">Identifica il numero di utenti abilitati.</span><span class="sxs-lookup"><span data-stu-id="d35cb-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="d35cb-112">Controlla la posizione in cui sono archiviate le impostazioni dei servizi di dominio Active Directory globale.</span><span class="sxs-lookup"><span data-stu-id="d35cb-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="d35cb-113">Controlla i punti di connessione del servizio (convergenza) per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d35cb-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="d35cb-114">Identifica la versione del database.</span><span class="sxs-lookup"><span data-stu-id="d35cb-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="d35cb-115">Risoluzione dei problemi relativi all'ambiente</span><span class="sxs-lookup"><span data-stu-id="d35cb-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="d35cb-116">Se il test dell'ambiente ha riscontrato problemi con l'ambiente, questi problemi sono probabilmente causati da problemi relativi alla configurazione di Active Directory o al livello di software in uso in server specifici.</span><span class="sxs-lookup"><span data-stu-id="d35cb-116">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers.</span></span> <span data-ttu-id="d35cb-117">Ad esempio, se Best Practices Analyzer identifica tutti i controller di dominio nell'ambiente in cui è in esecuzione Windows Server 2000, emetterà un avviso e sarà necessario aggiornare questi controller di dominio a una versione supportata di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="d35cb-117">For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

