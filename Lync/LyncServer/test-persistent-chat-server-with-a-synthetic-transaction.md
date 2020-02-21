---
title: Testare il server Chat persistente con una transazione sintetica
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Test Persistent Chat Server with a synthetic transaction
ms:assetid: 414e43f3-0074-4ecf-a232-398de972cb24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204837(v=OCS.15)
ms:contentKeyID: 48183968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d960e2c719c6ac0cac1ba20c702deb81b7deb4d1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-persistent-chat-server-with-a-synthetic-transaction"></a><span data-ttu-id="dde7b-102">Testare il server Chat persistente con una transazione sintetica</span><span class="sxs-lookup"><span data-stu-id="dde7b-102">Test Persistent Chat Server with a synthetic transaction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dde7b-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="dde7b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="dde7b-104">Per testare il server Chat persistente per l'invio e la ricezione di messaggi in una chat room tra due utenti</span><span class="sxs-lookup"><span data-stu-id="dde7b-104">To test Persistent Chat Server for sending and receiving messages in a chat room between two users</span></span>

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-ReceiverSipAddress <String>] [-RegistrarPort <Int32>] [-SenderSipAddress <String>] -TargetFqdn <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] 
        [-OutVerboseVariable <String>] [<CommonParameters>]

<span data-ttu-id="dde7b-105">oppure</span><span class="sxs-lookup"><span data-stu-id="dde7b-105">or</span></span>

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] -ReceiverCredential <PSCredential> -ReceiverSipAddress <String> [-RegistrarPort 
        <Int32>] -SenderCredential <PSCredential> -SenderSipAddress <String> [-TargetFqdn <String>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [<CommonParameters>]

<span data-ttu-id="dde7b-106">oppure</span><span class="sxs-lookup"><span data-stu-id="dde7b-106">or</span></span>

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable 
        <String>] [<CommonParameters>]

</div>

<span> </span>

</div>

</div>

</div>

