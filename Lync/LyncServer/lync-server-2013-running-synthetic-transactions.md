---
title: 'Lync Server 2013: esecuzione di transazioni sintetiche'
description: 'Lync Server 2013: esecuzione di transazioni sintetiche.'
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
ms.openlocfilehash: 26b0c26024f361dac196319eaf849c1847033cc9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569352"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="f969d-103">Esecuzione di transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f969d-103">Running synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f969d-104">_**Ultimo argomento modificato:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="f969d-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="f969d-105">Le transazioni sintetiche vengono in genere eseguite in due modi.</span><span class="sxs-lookup"><span data-stu-id="f969d-105">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="f969d-106">È possibile utilizzare i cmdlet di CsHealthMonitoringConfiguration per configurare gli utenti di test per ogni pool di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f969d-106">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="f969d-107">Questi utenti di test sono una coppia di utenti preconfigurati per l'utilizzo con transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="f969d-107">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="f969d-108">In genere si tratta di account di prova e non di account che appartengono a utenti effettivi. Con gli utenti di test configurati per un pool, è possibile eseguire una transazione sintetica su tale pool senza dover specificare le identità (e fornire le credenziali per) degli account utente coinvolti nel test.</span><span class="sxs-lookup"><span data-stu-id="f969d-108">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="f969d-109">In alternativa, è possibile eseguire una transazione sintetica utilizzando account utente effettivi.</span><span class="sxs-lookup"><span data-stu-id="f969d-109">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="f969d-110">Ad esempio, se due utenti non sono in grado di scambiare messaggi istantanei, è possibile eseguire una transazione sintetica utilizzando questi due account utente (invece di una coppia di account di test) e quindi provare a diagnosticare e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="f969d-110">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="f969d-111">Se si decide di eseguire una transazione sintetica utilizzando account utente effettivi, è necessario specificare i nomi di accesso e le password di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="f969d-111">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f969d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f969d-112">See Also</span></span>


[<span data-ttu-id="f969d-113">Configurazione degli utenti e delle impostazioni di configurazione del nodo Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f969d-113">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="f969d-114">Istruzioni di installazione speciali per le transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f969d-114">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

