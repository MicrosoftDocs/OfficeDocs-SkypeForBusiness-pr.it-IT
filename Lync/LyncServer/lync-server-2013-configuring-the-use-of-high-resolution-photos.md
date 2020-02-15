---
title: "Lync Server 2013: configurazione dell'utilizzo di foto ad alta risoluzione"
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
ms.openlocfilehash: d7d73970bd30aa72294369eac1d8206d19664230
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="cf233-102">Configurazione dell'utilizzo di foto ad alta risoluzione in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf233-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf233-103">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="cf233-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="cf233-104">Microsoft Lync Server 2010 ha offerto agli utenti la possibilità di visualizzare le foto dei propri contatti (e di rendere disponibili le proprie foto ad altri).</span><span class="sxs-lookup"><span data-stu-id="cf233-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="cf233-105">In genere, queste foto vengono archiviate come parte dell'attributo thumbnailPhoto dell'utente in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cf233-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="cf233-106">Ciò implica una seria limitazione alle dimensioni e alle risoluzioni delle foto: l'attributo thumbnailPhoto può contenere solo una fotografia di dimensioni massime pari a 48x48 pixel.</span><span class="sxs-lookup"><span data-stu-id="cf233-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="cf233-107">In Microsoft Lync Server 2013, tuttavia, le foto possono essere archiviate in una cassetta postale di Microsoft Exchange Server 2013 dell'utente. che consente di ridimensionare le foto fino a 648 pixel per 648 pixel.</span><span class="sxs-lookup"><span data-stu-id="cf233-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="cf233-108">Inoltre, Exchange 2013 può ridimensionare automaticamente queste foto per l'utilizzo in prodotti diversi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="cf233-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="cf233-109">Questo significa in genere tre diverse dimensioni e risoluzioni delle Foto:</span><span class="sxs-lookup"><span data-stu-id="cf233-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="cf233-110">48x48 pixel, le dimensioni usate per l'attributo thumbnailPhoto di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cf233-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="cf233-111">Se si carica una foto su Exchange 2013 Exchange creerà automaticamente una versione a 48 pixel per 48 pixel di quella foto e aggiornerà l'attributo thumbnailPhoto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cf233-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="cf233-112">Si noti, tuttavia, che l'inverso non è vero: se si aggiorna manualmente l'attributo thumbnailPhoto in Active Directory, la foto nella cassetta postale di Exchange 2013 dell'utente non verrà aggiornata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cf233-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="cf233-113">96 pixel per 96 pixel, per l'utilizzo in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cf233-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="cf233-114">648 pixel per 648 pixel per l'utilizzo in Lync 2013 e Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="cf233-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf233-p104">Se si dispone delle risorse, è consigliabile caricare foto nel formato 648x648 che offrono la risoluzione massima e la qualità ottimale dell'immagine in qualsiasi applicazione di Office 2013. Ogni foto JPEG di dimensioni pari a 648x648 e una profondità di 24 bit produce un file di dimensioni pari a circa 240 kilobyte. Ciò significa che sarà necessario circa 1 megabyte di spazio su disco per ogni 4 foto di utenti.</span><span class="sxs-lookup"><span data-stu-id="cf233-p104">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications. Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes. That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="cf233-118">Le foto ad alta risoluzione, a cui si accede utilizzando servizi Web Exchange, possono essere caricate dagli utenti che eseguono Outlook 2013 Web App. Gli utenti possono solo aggiornare la propria foto.</span><span class="sxs-lookup"><span data-stu-id="cf233-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="cf233-119">Gli amministratori, tuttavia, possono aggiornare la foto per qualsiasi utente utilizzando Exchange Management Shell e una serie di comandi di Windows PowerShell simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf233-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="cf233-120">Il primo comando nell'esempio precedente utilizza il cmdlet Get-Content per leggere il contenuto del file C:\\Photos\\kenmyer. jpg e archiviare i dati in una variabile denominata $Photo.</span><span class="sxs-lookup"><span data-stu-id="cf233-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="cf233-121">Nel secondo comando viene utilizzato il cmdlet Set-UserPhoto di Exchange per caricare la foto e allegarla all'account utente di Ken.</span><span class="sxs-lookup"><span data-stu-id="cf233-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf233-122">In questo esempio, il nome visualizzato di Active Directory di Ken Myer è utilizzato come identità dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="cf233-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="cf233-123">È anche possibile fare riferimento a un account utente mediante altri identificatori quali l'indirizzo SMTP dell'utente oppure il relativo nome dell'entità utente.</span><span class="sxs-lookup"><span data-stu-id="cf233-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="cf233-124"><A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> Per ulteriori informazioni, vedere la documentazione relativa al cmdlet Set-UserPhoto.</span><span class="sxs-lookup"><span data-stu-id="cf233-124">See the documentation for the Set-UserPhoto cmdlet at <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="cf233-p108">Il caricamento della foto non equivale ad assegnarla all'account utente di Ken Myer. Esso infatti produce semplicemente un'anteprima della foto da visualizzare nella pagina Opzioni di Outlook Web App. Per assegnare effettivamente la foto all'account utente, quest'ultimo deve fare clic su **Salva** nella pagina Opzioni oppure l'amministratore deve eseguire il terzo comando nell'esempio. Il terzo comando usa il parametro Save per assegnare la foto all'account utente di Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="cf233-p108">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="cf233-129">Per verificare che la nuova foto sia stata assegnata all'account utente, Ken è in grado di accedere a Lync 2013, selezionare **Opzioni**e quindi selezionare **immagine personale**.</span><span class="sxs-lookup"><span data-stu-id="cf233-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="cf233-130">La nuova foto aggiunta deve essere visualizzata come foto personale di Ken.</span><span class="sxs-lookup"><span data-stu-id="cf233-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="cf233-131">In alternativa, gli amministratori possono verificare la foto per qualsiasi utenti avviando Internet Explorer e passando a un URL analogo a questo:</span><span class="sxs-lookup"><span data-stu-id="cf233-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="cf233-132">Se l'amministratore può visualizzare la foto utilizzando Internet Explorer, ma l'utente non è in grado di visualizzare la propria foto in Lync 2013, indica in genere un problema di connettività con i servizi Web di Exchange o con il servizio di individuazione automatica di Exchange.</span><span class="sxs-lookup"><span data-stu-id="cf233-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="cf233-133">Si noti, inoltre, che non è necessaria alcuna configurazione aggiuntiva per rendere questa foto disponibile in Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cf233-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="cf233-134">Al contrario, la foto sarà immediatamente disponibile dopo che è stata caricata e il cmdlet Set-UserPhoto è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="cf233-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

