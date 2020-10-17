---
title: "Lync Server 2013: aggiungere e abilitare l'account utente per Lync Server"
description: "Lync Server 2013: aggiungere e abilitare l'account utente per Lync Server."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f70ae2da122a0db3986a75677c1d29234fbe0e3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571812"
---
# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="54038-103">Aggiungere e abilitare l'account utente per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54038-103">Add and enable user account for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54038-104">_**Ultimo argomento modificato:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="54038-104">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="54038-105">Dopo aver abilitato un account utente in utenti e computer di Active Directory, è possibile utilizzare il pannello di controllo di Lync Server per creare e abilitare nuovi account utente di Lync Server 2013 aggiungendo un utente di Active Directory a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54038-105">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="54038-106">Per aggiungere e abilitare un nuovo utente di Lync Server</span><span class="sxs-lookup"><span data-stu-id="54038-106">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="54038-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="54038-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54038-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54038-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="54038-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54038-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="54038-110">Nella barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="54038-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="54038-111">Fare clic su **Abilita utenti**.</span><span class="sxs-lookup"><span data-stu-id="54038-111">Click **Enable users**.</span></span>

5.  <span data-ttu-id="54038-112">Nella finestra di dialogo **Nuovo utente di Lync Server** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="54038-112">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="54038-113">Nella casella **Ricerca utenti** digitare il nome intero o parziale, il nome visualizzato, il nome, il cognome, il nome account del sistema degli account di sicurezza (SAM), l'indirizzo di posta elettronica, il nome dell'entità utente o il numero di telefono dell'account utente di Active Directory desiderato e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="54038-113">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="54038-114">Nella tabella selezionare l'account che si desidera aggiungere a Lync Server e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="54038-114">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="54038-115">Assegnare l'utente a un pool, specificare eventuali dettagli aggiuntivi, assegnare i criteri all'utente desiderato e quindi fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="54038-115">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54038-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54038-116">See Also</span></span>


[<span data-ttu-id="54038-117">Disabilitare o riabilitare l'account utente per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54038-117">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="54038-118">Rimuovere un account utente da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54038-118">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="54038-119">Abilitazione e disabilitazione degli utenti per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54038-119">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

