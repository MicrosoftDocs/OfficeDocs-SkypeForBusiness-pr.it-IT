---
title: 'Lync Server 2013: creare un nuovo filtro per il trasferimento di file per un sito specifico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bec5e9e33850fc1da53d370f70b948b7ec6b3f27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a><span data-ttu-id="bdfdc-102">Creare un nuovo filtro trasferimento file in Lync Server 2013 per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="bdfdc-102">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdfdc-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="bdfdc-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="bdfdc-104">Oltre alla modifica del filtro trasferimento file globale, è possibile configurare filtri di trasferimento file personalizzati per siti specifici all'interno della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-104">In addition to modifying the global file transfer filter, you can configure custom file transfer filters for specific sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="bdfdc-105">Per informazioni dettagliate sul filtro per il trasferimento di file, vedere [Configuring file transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="bdfdc-105">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a><span data-ttu-id="bdfdc-106">Per creare un filtro di trasferimento di file per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="bdfdc-106">To create a file transfer filter for a specific site</span></span>

1.  <span data-ttu-id="bdfdc-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bdfdc-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bdfdc-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bdfdc-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bdfdc-110">Sulla barra di spostamento sinistra fare clic su **Messaggistica istantanea e presenza** e quindi su **Filtro file**.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-110">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="bdfdc-111">Nella pagina **Filtro file** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-111">On the **File Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="bdfdc-112">Nella finestra di dialogo **Seleziona un sito** fare clic sul sito per il quale si desidera creare il filtro di trasferimento file e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-112">In the **Select a Site** dialog box, click the site for which you want to create the file transfer filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="bdfdc-113">In **Crea nuovo filtro file** fare clic sulla casella di controllo **Abilita filtro file**.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-113">In **New File Filter**, click the **Enable file filter** check box.</span></span>

7.  <span data-ttu-id="bdfdc-114">Nella casella di riepilogo a discesa **Trasferimento di file** fare clic su **Blocca tutto** o su **Blocca tipi di file specifici**.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-114">In **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

8.  <span data-ttu-id="bdfdc-115">Se si è fatto clic su **Blocca tutto**, andare al passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-115">If you clicked **Block All**, skip to step 10.</span></span>

9.  <span data-ttu-id="bdfdc-116">Se si è fatto clic su **Blocca tipi di file specifici**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bdfdc-116">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="bdfdc-117">Fare clic su **Seleziona** per modificare l'elenco predefinito di estensioni di file da bloccare.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-117">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="bdfdc-118">Nella finestra di dialogo **Seleziona estensioni di file** selezionare i tipi di file da bloccare o consentire aggiungendone o rimuovendone le estensioni dalle categorie in **Estensioni di file**.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-118">In the **Select File Type** dialog box, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="bdfdc-119">Se l'estensione di un tipo di file da bloccare non viene visualizzata, digitarla nella casella di testo in **Aggiungi estensioni di file all'elenco** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-119">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="bdfdc-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-120">Click **OK**.</span></span>

10. <span data-ttu-id="bdfdc-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="bdfdc-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bdfdc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdfdc-122">See Also</span></span>


[<span data-ttu-id="bdfdc-123">Configurazione del filtro per il trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdfdc-123">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="bdfdc-124">Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="bdfdc-124">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="bdfdc-125">Modificare il filtro di trasferimento file predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdfdc-125">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="bdfdc-126">Modificare il filtro URL predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdfdc-126">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

