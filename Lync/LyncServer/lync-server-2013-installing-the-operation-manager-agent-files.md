---
title: "Lync Server 2013: installare i file dell'agente di Operation Manager"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f75e9b6f8c3f7eb7151cf0d67a62f5e2a03a65f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="09d60-102">Installazione dei file dell'agente di Operation Manager in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09d60-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09d60-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="09d60-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="09d60-104">Per installare i file dell'agente di Operations Manager nel computer, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="09d60-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="09d60-105">Nel supporto di configurazione di System Center fare doppio clic su **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="09d60-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="09d60-106">Nella configurazione di System Center Operation Manager fare clic su **Installa agente Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="09d60-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="09d60-107">In configurazione guidata di System Center, nella pagina **Introduzione alla configurazione guidata di System Center Operations Manager** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="09d60-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="09d60-108">Nella pagina **cartella di destinazione** selezionare la cartella in cui verranno installati i file dell'agente di Operations Manager e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="09d60-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="09d60-109">Nella pagina **Configurazione gruppo di gestione** selezionare **specifica informazioni gruppo di gestione**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="09d60-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="09d60-110">Nella pagina **Configurazione gruppo di gestione** Digitare il nome del gruppo gestione Operations Manager nella casella **nome gruppo di gestione** e quindi digitare il nome host del server Operations Manager, ad esempio ATL-SCOM-001, nella casella **server di gestione** .</span><span class="sxs-lookup"><span data-stu-id="09d60-110">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="09d60-111">Se è stato modificato il numero di porta usato da Operations Manager, digitare il nuovo numero di porta nella casella porta del server di gestione.</span><span class="sxs-lookup"><span data-stu-id="09d60-111">If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box.</span></span> <span data-ttu-id="09d60-112">In caso contrario, lascia la porta al valore predefinito di 5723 e fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="09d60-112">Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="09d60-113">Nella pagina **account azione agente** selezionare **sistema locale**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="09d60-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="09d60-114">Nella pagina **Microsoft Update** selezionare **non si vuole usare Microsoft Update**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="09d60-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="09d60-115">Nella pagina **pronto per l'installazione** fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="09d60-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="09d60-116">Nella pagina **completamento della configurazione guidata di System Center Operations Manager** fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="09d60-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="09d60-117">Fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="09d60-117">Click **Exit**.</span></span>

<span data-ttu-id="09d60-118">Se si usa System Center 2007 R2, è possibile verificare che l'agente sia stato creato facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, scegliendo **System Center Operations Manager 2007 R2**e quindi facendo clic su **Operations Manager Shell**.</span><span class="sxs-lookup"><span data-stu-id="09d60-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="09d60-119">In Operations Manager Shell digitare il comando di Windows PowerShell seguente e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="09d60-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="09d60-120">Un elenco di tutti gli agenti di Operations Manager verrà visualizzato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="09d60-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="09d60-121">Se si usa System Center 2012, eseguire questo comando dalla shell Operations 2012 Manager:</span><span class="sxs-lookup"><span data-stu-id="09d60-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

