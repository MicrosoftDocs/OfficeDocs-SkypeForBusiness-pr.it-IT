---
title: 'Lync Server 2013: modificare il filtro di trasferimento file predefinito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="02dae-102">Modificare il filtro di trasferimento file predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02dae-102">Modify the default file transfer filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02dae-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="02dae-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="02dae-104">Lync Server 2013 offre un filtro di trasferimento di file globale che blocca i tipi specifici di file durante le attività correlate ai file seguenti nella distribuzione di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="02dae-104">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="02dae-105">Richieste di trasferimento di file durante le conversazioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="02dae-105">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="02dae-106">Caricamento e download di file durante l'uso della funzionalità stampati nel client Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="02dae-106">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="02dae-107">Riproduzione multimediale durante le conferenze</span><span class="sxs-lookup"><span data-stu-id="02dae-107">Multimedia playback during conferences</span></span>

<span data-ttu-id="02dae-108">A seconda dei tipi di file che si desidera bloccare o consentire, è possibile usare il pannello di controllo di Lync Server per modificare il filtro globale.</span><span class="sxs-lookup"><span data-stu-id="02dae-108">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="02dae-109">Per informazioni dettagliate sul filtro per il trasferimento di file, vedere [configurazione del trasferimento di file e filtro URL per la messaggistica istantanea in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="02dae-109">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="02dae-110">Per modificare il filtro di trasferimento file predefinito</span><span class="sxs-lookup"><span data-stu-id="02dae-110">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="02dae-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="02dae-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02dae-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02dae-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="02dae-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="02dae-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="02dae-114">Sulla barra di spostamento sinistra fare clic su **messaggistica istantanea e presenza** e quindi su **filtro file**.</span><span class="sxs-lookup"><span data-stu-id="02dae-114">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="02dae-115">Nella pagina **filtro file** fare doppio clic sul filtro **globale** .</span><span class="sxs-lookup"><span data-stu-id="02dae-115">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="02dae-116">In **Modifica filtro file**selezionare la casella di controllo **Attiva filtro file** .</span><span class="sxs-lookup"><span data-stu-id="02dae-116">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="02dae-117">Nella casella di riepilogo a discesa **trasferimento file** fare clic su **blocca tutto** o **Blocca tipi di file specifici**.</span><span class="sxs-lookup"><span data-stu-id="02dae-117">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="02dae-118">Se si è fatto clic su **blocca tutto**, passare al passaggio 9.</span><span class="sxs-lookup"><span data-stu-id="02dae-118">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="02dae-119">Se si è fatto clic su **Blocca tipi di file specifici**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02dae-119">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="02dae-120">Fare clic su **Seleziona** per modificare l'elenco predefinito delle estensioni del tipo di file che si vuole bloccare.</span><span class="sxs-lookup"><span data-stu-id="02dae-120">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="02dae-121">In **Seleziona tipo di file**selezionare i tipi di file che si desidera bloccare o consentire aggiungendo o rimuovendo le relative estensioni dalle categorie in **estensioni di tipi di file**.</span><span class="sxs-lookup"><span data-stu-id="02dae-121">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="02dae-122">Se non si vede l'estensione per un tipo di file che si vuole bloccare, digitare l'estensione nella casella di testo in **Aggiungi estensioni di file all'elenco**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="02dae-122">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="02dae-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="02dae-123">Click **OK**.</span></span>

9.  <span data-ttu-id="02dae-124">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="02dae-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02dae-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02dae-125">See Also</span></span>


[<span data-ttu-id="02dae-126">Configurazione del filtro del trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02dae-126">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="02dae-127">Creare un nuovo filtro per il trasferimento di file in Lync Server 2013 per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="02dae-127">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="02dae-128">Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni ISTANTANEe</span><span class="sxs-lookup"><span data-stu-id="02dae-128">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="02dae-129">Modificare il filtro URL predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02dae-129">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

