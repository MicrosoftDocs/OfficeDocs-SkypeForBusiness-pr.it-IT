---
title: 'Lync Server 2013: esecuzione di transazioni sintetiche'
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
ms.openlocfilehash: 297e1ee6416fb534791a2459e10acaa87f86e205
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511093"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="617ae-102">Esecuzione di transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="617ae-102">Running synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="617ae-103">_**Ultimo argomento modificato:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="617ae-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="617ae-104">Le transazioni sintetiche vengono in genere eseguite in due modi.</span><span class="sxs-lookup"><span data-stu-id="617ae-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="617ae-105">È possibile utilizzare i cmdlet di CsHealthMonitoringConfiguration per configurare gli utenti di test per ogni pool di registrazione.</span><span class="sxs-lookup"><span data-stu-id="617ae-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="617ae-106">Questi utenti di test sono una coppia di utenti preconfigurati per l'utilizzo con transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="617ae-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="617ae-107">In genere si tratta di account di prova e non di account che appartengono a utenti effettivi. Con gli utenti di test configurati per un pool, è possibile eseguire una transazione sintetica su tale pool senza dover specificare le identità (e fornire le credenziali per) degli account utente coinvolti nel test.</span><span class="sxs-lookup"><span data-stu-id="617ae-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="617ae-108">In alternativa, è possibile eseguire una transazione sintetica utilizzando account utente effettivi.</span><span class="sxs-lookup"><span data-stu-id="617ae-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="617ae-109">Ad esempio, se due utenti non sono in grado di scambiare messaggi istantanei, è possibile eseguire una transazione sintetica utilizzando questi due account utente (invece di una coppia di account di test) e quindi provare a diagnosticare e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="617ae-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="617ae-110">Se si decide di eseguire una transazione sintetica utilizzando account utente effettivi, è necessario specificare i nomi di accesso e le password di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="617ae-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="617ae-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="617ae-111">See Also</span></span>


[<span data-ttu-id="617ae-112">Configurazione degli utenti e delle impostazioni di configurazione del nodo Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="617ae-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="617ae-113">Istruzioni di installazione speciali per le transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="617ae-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

