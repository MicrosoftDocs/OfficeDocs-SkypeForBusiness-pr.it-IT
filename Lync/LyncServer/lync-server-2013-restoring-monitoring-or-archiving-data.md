---
title: 'Lync Server 2013: ripristino dei dati di monitoraggio o archiviazione'
description: 'Lync Server 2013: ripristino dei dati di monitoraggio o archiviazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 169a5da2d606b97c7cd3f59d6cbae3d4c584e6e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575517"
---
# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="5eee3-103">Ripristino dei dati di monitoraggio o archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5eee3-103">Restoring monitoring or archiving data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5eee3-104">_**Ultimo argomento modificato:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="5eee3-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="5eee3-105">Il ripristino dei dati di monitoraggio e archiviazione non è necessario per ottenere Lync Server attivo e in esecuzione dopo un errore.</span><span class="sxs-lookup"><span data-stu-id="5eee3-105">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="5eee3-106">Tuttavia, se il monitoraggio e l'archiviazione dei dati sono fondamentali per l'organizzazione, sarà necessario ripristinare i dati dopo aver ricreato i database.</span><span class="sxs-lookup"><span data-stu-id="5eee3-106">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="5eee3-107">Nella procedura seguente viene descritto come utilizzare SQL Server Management Studio per ripristinare i dati di archiviazione o di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="5eee3-107">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="5eee3-108">Per ripristinare i dati di monitoraggio o archiviazione da un file di backup</span><span class="sxs-lookup"><span data-stu-id="5eee3-108">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="5eee3-109">Accedere al server che si sta ripristinando come membro del gruppo Administrators nel computer locale o di un gruppo con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="5eee3-109">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="5eee3-110">Aprire SQL Server Management Studio: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2012** o **Microsoft SQL Server 2008 R2**e quindi fare clic su **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-110">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="5eee3-111">In **Connetti al server**, connettersi all'istanza di SQL Server specificando almeno il nome del server e le informazioni di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5eee3-111">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="5eee3-112">In **Esplora oggetti**fare clic con il pulsante destro del mouse su **database**e quindi scegliere **Ripristina database**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-112">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="5eee3-113">In **Seleziona una pagina**, fare clic su **generale**e quindi in **database** selezionare il nome del database come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5eee3-113">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="5eee3-114">Per un database di archiviazione, selezionare **LcsLog**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-114">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="5eee3-115">Per un database di registrazione dettagli chiamata, selezionare **LcsCDR**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-115">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="5eee3-116">Per un database QoE (Quality of Experience), selezionare **QoEMetrics**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-116">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="5eee3-117">Fare clic su **da dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-117">Click **From device**.</span></span>

7.  <span data-ttu-id="5eee3-118">In **selezionare i set di backup da ripristinare**, fare clic sul file di backup, quindi fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-118">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="5eee3-119">In **Seleziona una pagina**fare clic su **Opzioni**, verificare che il percorso del file di dati e il percorso del registro siano presenti nella cartella corretta e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-119">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="5eee3-120">Per assicurarsi che gli elenchi di controllo di accesso (ACL, Access Control List) siano corretti</span><span class="sxs-lookup"><span data-stu-id="5eee3-120">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="5eee3-121">Espandere **database**, espandere il database di archiviazione o di monitoraggio, espandere **sicurezza**e quindi espandere **utenti**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-121">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="5eee3-122">Verificare che il gruppo di dominio RTCComponentUniversalServices esista come utente.</span><span class="sxs-lookup"><span data-stu-id="5eee3-122">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="5eee3-123">Se RTCComponentUniversalServices non esiste in **utenti**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5eee3-123">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="5eee3-124">Fare clic con il pulsante destro del mouse su **Utenti** e quindi scegliere **Nuovo utente**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-124">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="5eee3-125">In **nome account di accesso**Digitare il nome del gruppo mancante, RTCComponentUniversalServices.</span><span class="sxs-lookup"><span data-stu-id="5eee3-125">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="5eee3-126">In **appartenenza a ruoli del database**selezionare l'autorizzazione **ServerRole** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5eee3-126">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5eee3-127">Non è necessario riavviare il servizio di archiviazione o di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="5eee3-127">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

