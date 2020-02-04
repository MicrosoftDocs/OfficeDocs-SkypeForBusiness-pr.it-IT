---
title: 'Lync Server 2013: Rimozione delle autorizzazioni degli utenti autenticati'
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
ms.openlocfilehash: 63b9761f96156fdc4dea124d4438cdb8685add26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="85dc5-102">Rimozione delle autorizzazioni degli utenti autenticati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85dc5-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85dc5-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="85dc5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="85dc5-104">In un ambiente Active Directory bloccato le voci di controllo di accesso utente autenticate (ACE) vengono rimosse dai contenitori predefiniti di Active Directory, inclusi gli utenti, la configurazione o il sistema e le unità organizzative (OU) in cui l'utente e il computer gli oggetti vengono archiviati.</span><span class="sxs-lookup"><span data-stu-id="85dc5-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="85dc5-105">La rimozione degli ACE utente autenticati impedisce l'accesso in lettura alle informazioni di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85dc5-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="85dc5-106">Tuttavia, la rimozione delle voci ACE crea problemi per Lync Server 2013 perché dipende dalle autorizzazioni di lettura per questi contenitori per consentire agli utenti di eseguire la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="85dc5-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="85dc5-107">In questa situazione, l'appartenenza al gruppo Domain Admins, necessaria per eseguire la preparazione del dominio, l'attivazione del server e la creazione di pool, non concede più l'accesso in lettura alle informazioni di Active Directory archiviate nei contenitori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="85dc5-107">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers.</span></span> <span data-ttu-id="85dc5-108">È necessario concedere manualmente le autorizzazioni di accesso in lettura per diversi contenitori nel dominio radice della foresta per verificare che la procedura di preparazione della foresta prerequisito sia stata completata.</span><span class="sxs-lookup"><span data-stu-id="85dc5-108">You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="85dc5-109">Per consentire a un utente di eseguire la preparazione del dominio, l'attivazione del server o la creazione di pool in qualsiasi dominio radice non forestale, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85dc5-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="85dc5-110">Usare un account membro del gruppo amministratori organizzazione per eseguire la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="85dc5-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="85dc5-111">Usare un account membro del gruppo Domain Admins e concedere a questo account le autorizzazioni di accesso in lettura per ognuno dei contenitori seguenti nel dominio radice della foresta:</span><span class="sxs-lookup"><span data-stu-id="85dc5-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="85dc5-112">Dominio</span><span class="sxs-lookup"><span data-stu-id="85dc5-112">Domain</span></span>
    
      - <span data-ttu-id="85dc5-113">Configurazione o sistema</span><span class="sxs-lookup"><span data-stu-id="85dc5-113">Configuration or System</span></span>

<span data-ttu-id="85dc5-114">Se non si vuole usare un account membro del gruppo amministratori organizzazione per eseguire la preparazione del dominio o altre attività di configurazione, concedere esplicitamente all'account che si vuole usare l'accesso in lettura nei contenitori rilevanti nella radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="85dc5-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="85dc5-115">Per concedere agli utenti autorizzazioni di accesso in lettura per i contenitori nel dominio radice della foresta</span><span class="sxs-lookup"><span data-stu-id="85dc5-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="85dc5-116">Accedere al computer collegato al dominio radice della foresta con un account membro del gruppo Domain Admins per il dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="85dc5-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="85dc5-117">Eseguire Adsiedit. msc per il dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="85dc5-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="85dc5-118">Se gli ACE utente autenticati sono stati rimossi dal dominio, dalla configurazione o dal contenitore di sistema, è necessario concedere le autorizzazioni di sola lettura al contenitore, come descritto nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="85dc5-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="85dc5-119">Fare clic con il pulsante destro del mouse sul contenitore e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="85dc5-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="85dc5-120">Fare clic sulla scheda **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="85dc5-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="85dc5-121">Fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="85dc5-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="85dc5-122">Nella scheda **autorizzazioni** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="85dc5-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="85dc5-123">Digitare il nome dell'utente o del gruppo che riceve le autorizzazioni usando il formato seguente `domain\account name`: e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="85dc5-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="85dc5-124">Nella scheda **oggetti** , in **si applica a**, fare clic su **solo questo oggetto**.</span><span class="sxs-lookup"><span data-stu-id="85dc5-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="85dc5-125">In **autorizzazioni**selezionare la seguente opzione Consenti ACE facendo clic sul **contenuto** **Consenti** colonna: elenco, **Leggi tutte le proprietà**e **autorizzazioni di lettura**.</span><span class="sxs-lookup"><span data-stu-id="85dc5-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="85dc5-126">Fare clic due volte su **OK** .</span><span class="sxs-lookup"><span data-stu-id="85dc5-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="85dc5-127">Ripetere questi passaggi per uno dei contenitori pertinenti elencati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="85dc5-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

