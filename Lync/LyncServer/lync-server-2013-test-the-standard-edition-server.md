---
title: 'Lync Server 2013: testare il server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f822297ed5a66189e42110167f70cf63e2d3d1db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519043"
---
# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="71e48-102">Testare il server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71e48-102">Test the Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71e48-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="71e48-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="71e48-104">Nella procedura seguente viene descritto come testare la distribuzione di un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="71e48-104">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="71e48-105">Per testare la distribuzione di un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="71e48-105">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="71e48-106">Utilizzare computer e utenti di Active Directory per aggiungere l'oggetto utente di Active Directory del ruolo di amministratore per la distribuzione di Lync Server 2013 (in cui è installato il pannello di controllo di Lync Server) nel gruppo **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="71e48-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="71e48-107">Se l'oggetto utente è connesso, disconnettersi e rieseguire l'accesso per registrare la nuova assegnazione al gruppo.</span><span class="sxs-lookup"><span data-stu-id="71e48-107">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71e48-108">L'account utente non può essere l'amministratore locale del server che esegue Lync Server 2013, Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="71e48-108">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="71e48-109">Se non si aggiungono gli utenti e i gruppi corretti al gruppo CSAdministrator, verrà visualizzato un messaggio di errore durante l'apertura del pannello di controllo di Lync Server 2013, in cui viene indicato che "non autorizzato: accesso negato a causa di un errore di autorizzazione del controllo di accesso basato sui ruoli (RBAC)".</span><span class="sxs-lookup"><span data-stu-id="71e48-109">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="71e48-110">Utilizzare l'account amministrativo per accedere al computer in cui è installato il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="71e48-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="71e48-111">Avviare il pannello di controllo di Lync Server e fornire le credenziali, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="71e48-111">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="71e48-112">Il pannello di controllo di Lync Server 2013 Visualizza le informazioni sulla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="71e48-112">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="71e48-113">Sulla barra di spostamento sinistra fare clic su **topologia**e quindi verificare che lo stato del servizio sia un'icona del computer con una freccia verde e che sia presente un segno di spunta verde accanto a ogni ruolo del server Lync Server distribuito e portato online.</span><span class="sxs-lookup"><span data-stu-id="71e48-113">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="71e48-114">Sulla barra di spostamento sinistra fare clic su **utenti**e quindi abilitare i due utenti per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71e48-114">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="71e48-115">Connettere un utente a un computer appartenente al dominio e l'altro utente a un altro computer nel dominio.</span><span class="sxs-lookup"><span data-stu-id="71e48-115">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="71e48-116">Installare Lync Server 2013 in ognuno dei due computer client e quindi verificare che entrambi gli utenti siano in grado di accedere a Lync Server 2013 e possano inviare messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="71e48-116">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71e48-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71e48-117">See Also</span></span>


[<span data-ttu-id="71e48-118">Distribuzione di client e dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71e48-118">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

