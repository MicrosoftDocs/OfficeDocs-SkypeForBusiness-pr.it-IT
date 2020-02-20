---
title: 'Lync Server 2013: disabilitare un utente per VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586f0e699d0cb0cea09b423f25beffd3efe5afdf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="f840b-102">Disabilitare un utente per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f840b-102">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f840b-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f840b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f840b-104">Utilizzare la procedura seguente per disabilitare VoIP aziendale per un account utente abilitato per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f840b-104">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="f840b-105">Per disabilitare un account utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="f840b-105">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="f840b-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f840b-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f840b-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f840b-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f840b-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f840b-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f840b-109">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="f840b-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f840b-110">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="f840b-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="f840b-111">Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f840b-111">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="f840b-112">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f840b-112">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="f840b-113">Nella pagina **Modifica utente Lync Server**, in **Telefonia** fare clic su qualsiasi opzione, ad eccezione di **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="f840b-113">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f840b-114">Per impedire a un utente di effettuare chiamate audio o video utilizzando Lync, in <STRONG>telefonia</STRONG>fare clic su <STRONG>audio/video disabilitato</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f840b-114">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="f840b-115">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f840b-115">Click **Commit**.</span></span>

<span data-ttu-id="f840b-116">L'utente non è ora in grado di utilizzare la funzionalità VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f840b-116">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f840b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f840b-117">See Also</span></span>


[<span data-ttu-id="f840b-118">Abilitare gli utenti per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f840b-118">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="f840b-119">Gestione di VoIP aziendale per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f840b-119">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="f840b-120">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="f840b-120">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

