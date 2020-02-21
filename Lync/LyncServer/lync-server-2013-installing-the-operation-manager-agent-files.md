---
title: "Lync Server 2013: installazione dei file dell'agente Operation Manager"
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
ms.openlocfilehash: 7e685abf7916c446bf9acf73e50f5633271b2942
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="58e80-102">Installazione dei file dell'agente Operation Manager in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58e80-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58e80-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="58e80-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="58e80-104">Per installare i file agente di Operations Manager nel computer, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="58e80-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="58e80-105">Nei supporti di installazione di System Center fare doppio clic su **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="58e80-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="58e80-106">Nell'installazione di System Center Operations Manager fare clic su **Installa agente Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="58e80-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="58e80-107">Nell'Installazione guidata di System Center, nella pagina iniziale dell'installazione di\*\*\*\* System Center Operations Manager fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="58e80-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="58e80-108">Nella pagina **Cartella di destinazione** selezionare la cartella in cui verranno installati i file dell'agente Operations Manager e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="58e80-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="58e80-109">Nella pagina **Configurazione gruppo di gestione** selezionare **Specifica informazioni gruppi di gestione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="58e80-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="58e80-p101">Nella pagina **Configurazione gruppo di gestione** digitare il nome del gruppo di gestione di Operations Manager nella casella **Nome gruppo di gestione** e quindi digitare il nome host del server Operations Manager (ad esempio, atl-scom-001) nella casella **Server di gestione**. Se è stato modificato il numero di porta utilizzato da Operations Manager, digitare il nuovo numero di porta nella casella della porta del server di gestione. In caso contrario lasciare il valore predefinito per la porta 5723 e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="58e80-p101">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box. If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box. Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="58e80-113">Nella pagina **Account azione agente** selezionare **Sistema locale** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="58e80-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="58e80-114">Nella pagina **Microsoft Update** selezionare **Non utilizzare Microsoft Update** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="58e80-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="58e80-115">Nella pagina **Pronto per l'installazione** fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="58e80-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="58e80-116">Nella pagina **Completamento dell'Installazione guidata di System Center Operations Manager** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="58e80-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="58e80-117">Fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="58e80-117">Click **Exit**.</span></span>

<span data-ttu-id="58e80-118">Se si utilizza System Center 2007 R2, per verificare che l'agente sia stato creato, fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, fare clic su **System Center Operations Manager 2007 R2** e quindi su **Shell di Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="58e80-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="58e80-119">Nella shell di Operations Manager, digitare il comando di Windows PowerShell seguente e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="58e80-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="58e80-120">Sullo schermo verrà visualizzato un elenco di tutti gli agenti di Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="58e80-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="58e80-121">Se si utilizza System Center 2012, eseguire questo comando dalla shell di Operations 2012 Manager:</span><span class="sxs-lookup"><span data-stu-id="58e80-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

