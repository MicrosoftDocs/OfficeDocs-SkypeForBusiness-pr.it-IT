---
title: "Lync Server 2013: aggiungere e abilitare l'account utente per Lync Server"
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
ms.openlocfilehash: a04a798a69279ebef6c4917938ead2fd88a49805
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="28750-102">Aggiungere e abilitare l'account utente per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28750-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28750-103">_**Argomento Ultima modifica:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="28750-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="28750-104">Dopo l'abilitazione di un account utente in utenti e computer di Active Directory, è possibile usare il pannello di controllo di Lync Server per creare e abilitare nuovi account utente di Lync Server 2013 aggiungendo un utente di Active Directory a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28750-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="28750-105">Per aggiungere e abilitare un nuovo utente di Lync Server</span><span class="sxs-lookup"><span data-stu-id="28750-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="28750-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="28750-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="28750-107">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28750-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="28750-108">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="28750-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="28750-109">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="28750-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="28750-110">Fare clic su **Abilita utenti**.</span><span class="sxs-lookup"><span data-stu-id="28750-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="28750-111">Nella finestra di dialogo **nuovo utente di Lync Server** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="28750-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="28750-112">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome, il nome visualizzato, il nome, il cognome, il nome dell'account SAM (Security Accounts Manager), l'indirizzo di posta elettronica, il nome dell'entità utente (UPN) o il numero di telefono dell'account utente di Active Directory desiderato e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="28750-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="28750-113">Nella tabella selezionare l'account che si vuole aggiungere a Lync Server e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="28750-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="28750-114">Assegnare l'utente a un pool, specificare eventuali dettagli aggiuntivi e assegnare i criteri all'utente desiderato e quindi fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="28750-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28750-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28750-115">See Also</span></span>


[<span data-ttu-id="28750-116">Disabilitare o riattivare l'account utente per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28750-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="28750-117">Rimuovere un account utente da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28750-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="28750-118">Abilitazione e disabilitazione degli utenti per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28750-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

