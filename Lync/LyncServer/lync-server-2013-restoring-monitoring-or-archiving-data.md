---
title: "Lync Server 2013: ripristinare il monitoraggio o l'archiviazione dei dati"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 803cb6050d4230653a13f1e3e66c2a092911c509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="aa6b4-102">Ripristinare il monitoraggio o l'archiviazione dei dati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa6b4-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa6b4-103">_**Argomento Ultima modifica:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="aa6b4-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="aa6b4-104">Non è necessario ripristinare i dati di monitoraggio e archiviazione per ottenere l'accesso e l'uso di Lync Server dopo un errore.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="aa6b4-105">Tuttavia, se il monitoraggio e l'archiviazione dei dati è fondamentale per l'organizzazione, sarà necessario ripristinare i dati dopo la ricreazione dei database.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="aa6b4-106">La procedura seguente descrive come usare SQL Server Management Studio per ripristinare i dati di archiviazione o monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="aa6b4-107">Per ripristinare il monitoraggio o l'archiviazione dei dati da un file di backup</span><span class="sxs-lookup"><span data-stu-id="aa6b4-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="aa6b4-108">Accedere al server che si sta ripristinando come membro del gruppo Administrators nel computer locale o in un gruppo con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="aa6b4-109">Aprire SQL Server Management Studio: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2012** o **Microsoft SQL Server 2008 R2**e quindi fare clic su **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="aa6b4-110">In **Connetti al server**connettersi all'istanza di SQL Server specificando almeno il nome del server e le informazioni di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="aa6b4-111">In **Esplora oggetti**fare clic con il pulsante destro del mouse su **database**e quindi scegliere **Ripristina database**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="aa6b4-112">In **Seleziona una pagina**fare clic su **generale**e quindi in **database** selezionare il nome del database nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="aa6b4-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="aa6b4-113">Per un database di archiviazione, selezionare **LcsLog**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="aa6b4-114">Per un database di registrazione dei dettagli delle chiamate (CDR) selezionare **LcsCDR**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="aa6b4-115">Per un database di qualità dell'esperienza (QoE), selezionare **QoEMetrics**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="aa6b4-116">Fare clic su **da dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-116">Click **From device**.</span></span>

7.  <span data-ttu-id="aa6b4-117">In **selezionare i set di backup da ripristinare**, fare clic sul file di backup e quindi su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="aa6b4-118">In **Seleziona una pagina**fare clic su **Opzioni**, verificare che il percorso del file di dati e il percorso del log si trovino nella cartella corretta e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="aa6b4-119">Per verificare che gli elenchi di controllo di accesso (ACL) siano corretti</span><span class="sxs-lookup"><span data-stu-id="aa6b4-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="aa6b4-120">Espandere **database**, espandere il database di archiviazione o monitoraggio, espandere **sicurezza**e quindi espandere **utenti**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="aa6b4-121">Verificare che il gruppo di domini RTCComponentUniversalServices esista come utente.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="aa6b4-122">Se RTCComponentUniversalServices non è presente in **utenti**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa6b4-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="aa6b4-123">Fare clic con il pulsante destro del mouse su **utenti**e quindi scegliere **nuovo utente**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="aa6b4-124">In **nome account di accesso**Digitare il nome del gruppo mancante, RTCComponentUniversalServices.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="aa6b4-125">In **appartenenza a ruoli del database**selezionare l'autorizzazione **ServerRole** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa6b4-126">Non è necessario riavviare il servizio archiviazione o monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

