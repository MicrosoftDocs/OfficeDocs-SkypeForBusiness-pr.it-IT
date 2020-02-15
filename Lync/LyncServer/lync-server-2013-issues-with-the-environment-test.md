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
ms.openlocfilehash: b7d077b22c147dd677a5db68636b2c68bfafcf23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="5667a-102">Problemi relativi al test dell'ambiente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5667a-102">Issues with the environment test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5667a-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5667a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5667a-104">Best Practices Analyzer consente di verificare che l'ambiente Lync Server 2013 sia una configurazione supportata.</span><span class="sxs-lookup"><span data-stu-id="5667a-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="5667a-105">Best Practices Analyzer fa parte dei controlli di Servizi di dominio Active Directory ed esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5667a-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="5667a-106">Verifica la preparazione della foresta e dello schema di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5667a-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="5667a-107">Identifica il numero di siti e domini di Servizi di dominio Active Directory nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5667a-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="5667a-108">Controlla i livelli di foresta e dominio.</span><span class="sxs-lookup"><span data-stu-id="5667a-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="5667a-109">Controlla la versione del controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="5667a-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="5667a-110">Identifica il dominio, la configurazione e il contesto di denominazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="5667a-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="5667a-111">Identifica il numero degli utenti abilitati.</span><span class="sxs-lookup"><span data-stu-id="5667a-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="5667a-112">Controlla dove sono archiviate le impostazioni globali di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5667a-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="5667a-113">Verifica la disposizione dei punti di connessione del servizio (SCP) per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5667a-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="5667a-114">Identifica la versione del database.</span><span class="sxs-lookup"><span data-stu-id="5667a-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="5667a-115">Risoluzione dei problemi con l'ambiente</span><span class="sxs-lookup"><span data-stu-id="5667a-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="5667a-p102">Se il test dell'ambiente rileva problemi con l'ambiente, questi potrebbero essere causati da problemi relativi alla configurazione di Active Directory o al livello di software in esecuzione in server specifici. Ad esempio, se Best Practices Analyzer identifica nell'ambiente dei controller di dominio in cui è in esecuzione Windows Server 2000, verrà visualizzato un avviso e sarà necessario aggiornare i controller di dominio alla versione supportata di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="5667a-p102">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers. For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

