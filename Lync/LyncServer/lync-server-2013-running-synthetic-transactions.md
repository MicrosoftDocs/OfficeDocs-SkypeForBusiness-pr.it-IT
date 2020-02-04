---
title: 'Lync Server 2013: eseguire transazioni sintetiche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b77593ea062f83352592ebe32dbb81b99c1a9613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="1b197-102">Eseguire transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b197-102">Running synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b197-103">_**Argomento Ultima modifica:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="1b197-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="1b197-104">Le transazioni sintetiche vengono in genere eseguite in due modi.</span><span class="sxs-lookup"><span data-stu-id="1b197-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="1b197-105">Puoi usare i cmdlet CsHealthMonitoringConfiguration per configurare gli utenti di test per ogni pool di registrar.</span><span class="sxs-lookup"><span data-stu-id="1b197-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="1b197-106">Questi utenti di test sono una coppia di utenti preconfigurati per l'uso con le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="1b197-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="1b197-107">In genere si tratta di account di test e non di account che appartengono a utenti effettivi. Con gli utenti di test configurati per un pool, è possibile eseguire una transazione sintetica in tale pool senza dover specificare le identità (e fornire le credenziali per) degli account utente coinvolti nel test.</span><span class="sxs-lookup"><span data-stu-id="1b197-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="1b197-108">In alternativa, è possibile eseguire una transazione sintetica usando gli account utente effettivi.</span><span class="sxs-lookup"><span data-stu-id="1b197-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="1b197-109">Se ad esempio due utenti non possono scambiare messaggi istantanei, è possibile eseguire una transazione sintetica usando questi due account utente (invece di una coppia di account di test) e quindi provare a diagnosticare e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="1b197-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="1b197-110">Se si decide di eseguire una transazione sintetica con gli account utente effettivi, è necessario specificare i nomi di accesso e le password per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="1b197-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1b197-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b197-111">See Also</span></span>


[<span data-ttu-id="1b197-112">Configurazione degli utenti e delle impostazioni di configurazione di testing node di Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b197-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="1b197-113">Istruzioni per la configurazione speciale per le transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b197-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

