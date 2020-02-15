---
title: 'Lync Server 2013: sono state rimosse le autorizzazioni per gli utenti autenticati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd54da7201889e9ca2ab8d2c40a84ad082fa1686
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="a302f-102">Le autorizzazioni degli utenti autenticati sono state rimosse in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a302f-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a302f-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a302f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a302f-104">In un ambiente Active Directory bloccato le voci di controllo di accesso degli utenti autenticati vengono rimosse dai contenitori predefiniti di Active Directory, tra cui il contenitore degli utenti, della configurazione o di sistema, e dalle unità organizzative in cui sono archiviati gli oggetti utente e computer.</span><span class="sxs-lookup"><span data-stu-id="a302f-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="a302f-105">La rimozione delle voci di controllo di accesso degli utenti autenticati impedisce l'accesso in lettura alle informazioni di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a302f-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="a302f-106">Tuttavia, la rimozione di Ace crea problemi per Lync Server 2013 perché dipende dalle autorizzazioni di lettura per questi contenitori per consentire agli utenti di eseguire la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="a302f-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="a302f-p102">In questa situazione l'appartenenza al gruppo Domain Admins, necessaria per la preparazione del dominio, per l'attivazione del server e per la creazione del pool, non concede più l'accesso in lettura alle informazioni di Active Directory archiviate nei contenitori predefiniti. È pertanto necessario concedere manualmente le autorizzazioni di accesso in lettura per diversi contenitori nel dominio radice della foresta per verificare il corretto completamento della procedura di preparazione della foresta, che costituisce un prerequisito.</span><span class="sxs-lookup"><span data-stu-id="a302f-p102">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers. You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="a302f-109">Per consentire a un utente di eseguire la preparazione del dominio, l'attivazione del server o la creazione del pool in un qualsiasi dominio diverso dal dominio radice della foresta, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a302f-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="a302f-110">Utilizzare un account membro del gruppo Enterprise Admins per eseguire la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="a302f-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="a302f-111">Utilizzare un account membro del gruppo Domain Admins e concedere a tale account le autorizzazioni di accesso in lettura per ciascuno dei contenitori seguenti nel dominio radice della foresta:</span><span class="sxs-lookup"><span data-stu-id="a302f-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="a302f-112">Dominio</span><span class="sxs-lookup"><span data-stu-id="a302f-112">Domain</span></span>
    
      - <span data-ttu-id="a302f-113">Contenitore di sistema o della configurazione</span><span class="sxs-lookup"><span data-stu-id="a302f-113">Configuration or System</span></span>

<span data-ttu-id="a302f-114">Se non si desidera utilizzare un account membro del gruppo Enterprise Admins per eseguire la preparazione del dominio o altre attività di impostazione, è possibile concedere in modo esplicito l'accesso in lettura per i contenitori appropriati nel dominio radice della foresta all'account che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a302f-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="a302f-115">Per assegnare agli utenti le autorizzazioni di accesso in lettura sui contenitori nel dominio radice della foresta</span><span class="sxs-lookup"><span data-stu-id="a302f-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="a302f-116">Accedere al computer appartenente al dominio radice della foresta utilizzando un account membro del gruppo Domain Admins per il dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="a302f-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="a302f-117">Eseguire adsiedit.msc per il dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="a302f-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="a302f-118">Se le voci di controllo di accesso degli utenti autenticati sono state rimosse dal contenitore di sistema, del dominio o della configurazione, è necessario concedere autorizzazioni di sola lettura per il contenitore, come descritto nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="a302f-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="a302f-119">Fare clic con il pulsante destro del mouse sul contenitore e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a302f-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="a302f-120">Fare clic sulla scheda **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="a302f-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="a302f-121">Fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="a302f-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="a302f-122">Nella scheda **Autorizzazioni**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a302f-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="a302f-123">Digitare il nome dell'utente o del gruppo che riceve le autorizzazioni utilizzando il formato seguente `domain\account name`: e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a302f-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="a302f-124">Nella scheda **Oggetti** fare clic su **Solo l'oggetto specificato** nell'elenco **Si applica a**.</span><span class="sxs-lookup"><span data-stu-id="a302f-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="a302f-125">In **Autorizzazioni** fare clic sulla colonna **Consenti** per le seguenti voci di controllo di accesso: **Elenca contenuto**, **Leggi tutte le proprietà** e **Autorizzazioni di lettura**.</span><span class="sxs-lookup"><span data-stu-id="a302f-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="a302f-126">Fare due volte clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a302f-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="a302f-127">Ripetere queste operazioni per ognuno dei contenitori rilevanti indicati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="a302f-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

