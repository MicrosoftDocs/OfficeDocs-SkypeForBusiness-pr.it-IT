---
title: "Lync Server 2013: configurazione dell'uso di foto ad alta risoluzione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cb82c047491a43f2a8682d3a6688f67e76af730
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="3bf5b-102">Configurazione dell'uso di foto ad alta risoluzione in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bf5b-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bf5b-103">_**Argomento Ultima modifica:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="3bf5b-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="3bf5b-104">Microsoft Lync Server 2010 ha fornito agli utenti la possibilità di visualizzare le foto dei loro contatti (e di rendere le proprie foto disponibili per gli altri).</span><span class="sxs-lookup"><span data-stu-id="3bf5b-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="3bf5b-105">In genere queste foto sono state archiviate come parte dell'attributo thumbnailPhoto dell'utente in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="3bf5b-106">Questo ha posto un grave limite alle dimensioni e alla risoluzione delle Foto: l'attributo thumbnailPhoto può contenere solo una fotografia con una dimensione massima di 48 pixel per 48 pixel.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="3bf5b-107">In Microsoft Lync Server 2013, tuttavia, le foto possono essere archiviate nella cassetta postale di Microsoft Exchange Server 2013 di un utente. che consente di ridimensionare le foto fino a 648 pixel per 648 pixel.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="3bf5b-108">Oltre a questo, Exchange 2013 può ridimensionare automaticamente queste foto per l'uso in prodotti diversi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="3bf5b-109">In genere significa tre diverse dimensioni e risoluzioni delle Foto:</span><span class="sxs-lookup"><span data-stu-id="3bf5b-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="3bf5b-110">48 pixel per 48 pixel, le dimensioni usate per l'attributo thumbnailPhoto di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="3bf5b-111">Se si carica una foto in Exchange 2013 Exchange creerà automaticamente una versione di 48 pixel per 48 pixel della foto e aggiornerà l'attributo thumbnailPhoto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="3bf5b-112">Si noti tuttavia che il contrario non è vero: se si aggiorna manualmente l'attributo thumbnailPhoto in Active Directory, la foto nella cassetta postale di Exchange 2013 dell'utente non verrà aggiornata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="3bf5b-113">96 pixel per 96 pixel, per l'uso in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="3bf5b-114">648 pixel per 648 pixel per l'uso in Lync 2013 e in Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3bf5b-115">Se si hanno le risorse, è consigliabile caricare le foto di 648x648; che offre la massima risoluzione e una qualità ottimale delle immagini in tutte le applicazioni di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-115">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="3bf5b-116">Ogni foto JPEG con una dimensione di 648x648 e una profondità di 24 bit genera una dimensione del file di circa 240 kilobyte.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-116">Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="3bf5b-117">Questo significa che avrai bisogno di circa 1 megabyte di spazio su disco per ogni 4 foto utente.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-117">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="3bf5b-118">Le foto ad alta risoluzione, a cui si accede usando i servizi Web di Exchange, possono essere caricate dagli utenti che usano Outlook 2013 Web App; agli utenti è consentito aggiornare solo la propria foto.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="3bf5b-119">Gli amministratori possono tuttavia aggiornare la foto per qualsiasi utente usando Exchange Management Shell e una serie di comandi di Windows PowerShell simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bf5b-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="3bf5b-120">Il primo comando nell'esempio precedente usa il cmdlet Get-Content per leggere il contenuto del file C:\\Photos\\kenmyer. jpg e archiviare i dati in una variabile denominata $Photo.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="3bf5b-121">Nel secondo comando viene usato il cmdlet Set-UserPhoto di Exchange per caricare la foto e allegare la foto all'account utente di Ken.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3bf5b-122">In questo esempio, il nome visualizzato in Active Directory di Ken è usato come identità dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="3bf5b-123">È anche possibile fare riferimento a un account utente usando altri identificatori, ad esempio l'indirizzo SMTP dell'utente o il nome dell'entità utente.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="3bf5b-124"><A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> Per altre informazioni, vedere la documentazione relativa al cmdlet Set-UserPhoto.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-124">See the documentation for the Set-UserPhoto cmdlet at <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="3bf5b-125">Il caricamento della foto non equivale all'assegnazione di tale foto all'account utente di Ken.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-125">Uploading the photo does not equate to assigning that photo to Ken Myer's user account.</span></span> <span data-ttu-id="3bf5b-126">Invece, il caricamento della foto restituisce semplicemente un'anteprima della foto da visualizzare nella pagina delle opzioni di Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-126">Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page.</span></span> <span data-ttu-id="3bf5b-127">Per assegnare effettivamente la foto all'account utente, l'utente deve fare clic su **Salva** nella pagina Opzioni oppure l'amministratore deve eseguire il terzo comando nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-127">To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example.</span></span> <span data-ttu-id="3bf5b-128">Questo terzo comando usa il parametro Save per assegnare la foto all'account utente di Ken requestro:</span><span class="sxs-lookup"><span data-stu-id="3bf5b-128">That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="3bf5b-129">Per verificare che la nuova foto sia stata assegnata all'account utente, Ken può accedere a Lync 2013, selezionare **Opzioni**e quindi selezionare **immagine personale**.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="3bf5b-130">La foto appena caricata deve essere visualizzata come foto personale di Ken.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="3bf5b-131">In alternativa, gli amministratori possono verificare la foto per qualsiasi utente avviando Internet Explorer e passando a un URL simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3bf5b-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="3bf5b-132">Se l'amministratore può visualizzare la foto con Internet Explorer, ma l'utente non può visualizzare la propria foto in Lync 2013, che in genere indica un problema di connettività con i servizi Web di Exchange o con il servizio di individuazione automatica di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="3bf5b-133">Tieni presente che non è richiesta alcuna configurazione aggiuntiva per rendere disponibile questa foto in Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="3bf5b-134">La foto sarà invece immediatamente disponibile dopo che è stata caricata e il cmdlet Set-UserPhoto è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

